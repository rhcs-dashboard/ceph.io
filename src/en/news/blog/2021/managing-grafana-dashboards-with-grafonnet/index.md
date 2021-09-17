---
title: "Managing Grafana Dashboards with Grafonnet"
date: "2021-09-17"
author: "Aashish Sharma"
---

The process of maintaing grafana dashboards or updating the dashboard JSON files can sometimes become a mess as the size of the JSON files becomes too large to debug it. In this blog you can find out how grafana dashboards can be managed as code using Grafonnet.

## About Grafonnet

In case you already know what [Grafonnet](https://github.com/grafana/grafonnet-lib) is, it would be easier for you to get going with grafonnet. For those who don’t know: Grafonnet is a [Jsonnet](https://jsonnet.org) library – with Jsonnet being a JSON extension to create files using abstractions such as variables, functions, conditionals and more.Grafonnet consists of different functions we can use to create the JSON objects required to compose Grafana dashboards or panels. the resulting JSON files are then imported into grafana.

## Creating a Dashboard with Grafonnet

The grafonnet library exposes functions we can use to define our Grafana dashboards. First, we need to [import](https://grafana.github.io/grafonnet-lib/getting-started/) Grafonnet. Grafana.libsonnet works as an entry point and exposes all required functions and interfaces from the library files.
The code below is the minimal code required to create a dashboard requiring only a title.

```
local grafana = import 'grafonnet/grafana.libsonnet';
local dashboard = grafana.dashboard;
 
dashboard.new(
  title='Demo dashboard'
)
```

The above code can be compiled with `$ jsonnet -o new.json new.jsonnet` and the resultant json file(new.json) can be imported into Grafana.

## Adding Template Variables

Grafonnet library provides the functions `addTemplate() and addTemplates()`, which either take a template object or an array of them.

```
local template = grafana.template;
 
dashboard.new(
  title='Demo Dashboard'
)
.addTemplate(
  template.new(
    name='service',
    datasource='LocalPrometheus',
    query='label_values(service)',
    allValues=null,
    current='all',
    refresh='load',
    includeAll=true,
    multi=true,
  )
)
```

## Adding Panels

Panel objects are being added similar to template variables, by using `addPanel() or addPanels()`. In addition to creating the panel objects, we specify their position by adding a `gridPos` attribute. Below is the additional code to above for adding one text and graph panel.
By using `addTarget()` which is exposed by the panel object we can add a target object.

```
local prometheus = grafana.prometheus;
 
// dashboard and template objects
.addPanels([
  textPanel.new(
    mode='html',
    content='<p2 align=\"center\">Services</p2>',
  ) + {gridPos: {h: 1, w: 0, x: 8, y: 0}},
  graphPanel.new(
    title='RGW Sync Overview',
    fill=2,
    formatY1='percentunit',
    datasource='Prometheus',
  )
  .addTargets([
    prometheus.target(
      expr='ceph_health_status == 2',
      intervalFactor=1,
      legendFormat='time_series',
    )
  ]) + {gridPos: {h: 0, w: 0, x: 8, y: 9}},
])
```

## Custom functions for Reusability

Using reusable functions will make the code not just easier to read but easier to maintain as well.Below is an example of making custom functions which take properties such as title, uid etc. and these functions can be reused if you want to create a number of dashboards by just passing the parameters.

```
local dashboardSchema(title, uid, time_from, refresh, schemaVersion, tags,timezone, timepicker) =
  g.dashboard.new(title=title, uid=uid, time_from=time_from, refresh=refresh, schemaVersion=schemaVersion, tags=tags, timezone=timezone, timepicker=timepicker);

local graphPanelSchema(title, nullPointMode, stack, formatY1, formatY2, labelY1, labelY2, min, fill, datasource) =
  g.graphPanel.new(title=title, nullPointMode=nullPointMode, stack=stack, formatY1=formatY1, formatY2=formatY2, labelY1=labelY1, labelY2=labelY2, min=min, fill=fill, datasource=datasource);

```