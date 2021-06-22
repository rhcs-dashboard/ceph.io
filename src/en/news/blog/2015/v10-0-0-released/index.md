---
title: "v10.0.0 released"
date: "2015-11-23"
author: "sage"
---

This is the first development release for the Jewel cycle.  We are off to a good start, with lots of performance improvements flowing into the tree.  We are targeting sometime in Q1 2016 for the final Jewel.

### NOTABLE CHANGES

- build: cmake tweaks ([pr#6254](http://github.com/ceph/ceph/pull/6254), John Spray)
- build: more CMake package check fixes ([pr#6108](http://github.com/ceph/ceph/pull/6108), Daniel Gryniewicz)
- ceph-disk: get Nonetype when ceph-disk list with –format plain on single device. ([pr#6410](http://github.com/ceph/ceph/pull/6410), Vicente Cheng)
- ceph: fix tell behavior ([pr#6329](http://github.com/ceph/ceph/pull/6329), David Zafman)
- ceph-fuse: While starting ceph-fuse, start the log thread first ([issue#13443](http://tracker.ceph.com/issues/13443), [pr#6224](http://github.com/ceph/ceph/pull/6224), Wenjun Huang)
- client: don’t mark\_down on command reply ([pr#6204](http://github.com/ceph/ceph/pull/6204), John Spray)
- client: drop prefix from ints ([pr#6275](http://github.com/ceph/ceph/pull/6275), John Coyle)
- client: sys/file.h includes for flock operations ([pr#6282](http://github.com/ceph/ceph/pull/6282), John Coyle)
- cls\_rbd: change object\_map\_update to return 0 on success, add logging ([pr#6467](http://github.com/ceph/ceph/pull/6467), Douglas Fuller)
- cmake: Use uname instead of arch. ([pr#6358](http://github.com/ceph/ceph/pull/6358), John Coyle)
- common: assert: \_\_STRING macro is not defined by musl libc. ([pr#6210](http://github.com/ceph/ceph/pull/6210), John Coyle)
- common: fix OpTracker age histogram calculation ([pr#5065](http://github.com/ceph/ceph/pull/5065), Zhiqiang Wang)
- common/MemoryModel: Added explicit feature check for mallinfo(). ([pr#6252](http://github.com/ceph/ceph/pull/6252), John Coyle)
- common/obj\_bencher.cc: fix verification crashing when there’s no objects ([pr#5853](http://github.com/ceph/ceph/pull/5853), Piotr Dałek)
- common: optimize debug logging ([pr#6307](http://github.com/ceph/ceph/pull/6307), Adam Kupczyk)
- common: Thread: move copy constructor and assignment op ([pr#5133](http://github.com/ceph/ceph/pull/5133), Michal Jarzabek)
- common: WorkQueue: new PointerWQ base class for ContextWQ ([issue#13636](http://tracker.ceph.com/issues/13636), [pr#6525](http://github.com/ceph/ceph/pull/6525), Jason Dillaman)
- compat: use prefixed typeof extension ([pr#6216](http://github.com/ceph/ceph/pull/6216), John Coyle)
- crush: validate bucket id before indexing buckets array ([issue#13477](http://tracker.ceph.com/issues/13477), [pr#6246](http://github.com/ceph/ceph/pull/6246), Sage Weil)
- doc: download GPG key from download.ceph.com ([issue#13603](http://tracker.ceph.com/issues/13603), [pr#6384](http://github.com/ceph/ceph/pull/6384), Ken Dreyer)
- doc: fix outdated content in cache tier ([pr#6272](http://github.com/ceph/ceph/pull/6272), Yuan Zhou)
- doc/release-notes: v9.1.0 ([pr#6281](http://github.com/ceph/ceph/pull/6281), Loic Dachary)
- doc/releases-notes: fix build error ([pr#6483](http://github.com/ceph/ceph/pull/6483), Kefu Chai)
- doc: remove toctree items under Create CephFS ([pr#6241](http://github.com/ceph/ceph/pull/6241), Jevon Qiao)
- doc: rename the “Create a Ceph User” section and add verbage about… ([issue#13502](http://tracker.ceph.com/issues/13502), [pr#6297](http://github.com/ceph/ceph/pull/6297), ritz303)
- docs: Fix styling of newly added mirror docs ([pr#6127](http://github.com/ceph/ceph/pull/6127), Wido den Hollander)
- doc, tests: update all [http://ceph.com/](http://ceph.com/) to download.ceph.com ([pr#6435](http://github.com/ceph/ceph/pull/6435), Alfredo Deza)
- doc: update doc for with new pool settings ([pr#5951](http://github.com/ceph/ceph/pull/5951), Guang Yang)
- doc: update radosgw-admin example ([pr#6256](http://github.com/ceph/ceph/pull/6256), YankunLi)
- doc: update the OS recommendations for newer Ceph releases ([pr#6355](http://github.com/ceph/ceph/pull/6355), ritz303)
- drop envz.h includes ([pr#6285](http://github.com/ceph/ceph/pull/6285), John Coyle)
- libcephfs: Improve portability by replacing loff\_t type usage with off\_t ([pr#6301](http://github.com/ceph/ceph/pull/6301), John Coyle)
- libcephfs: only check file offset on glibc platforms ([pr#6288](http://github.com/ceph/ceph/pull/6288), John Coyle)
- librados: fix examples/librados/Makefile error. ([pr#6320](http://github.com/ceph/ceph/pull/6320), You Ji)
- librados: init crush\_location from config file. ([issue#13473](http://tracker.ceph.com/issues/13473), [pr#6243](http://github.com/ceph/ceph/pull/6243), Wei Luo)
- librados: wrongly passed in argument for stat command ([issue#13703](http://tracker.ceph.com/issues/13703), [pr#6476](http://github.com/ceph/ceph/pull/6476), xie xingguo)
- librbd: deadlock while attempting to flush AIO requests ([issue#13726](http://tracker.ceph.com/issues/13726), [pr#6508](http://github.com/ceph/ceph/pull/6508), Jason Dillaman)
- librbd: fix enable objectmap feature issue ([issue#13558](http://tracker.ceph.com/issues/13558), [pr#6339](http://github.com/ceph/ceph/pull/6339), xinxin shu)
- librbd: remove duplicate read\_only test in librbd::async\_flatten ([pr#5856](http://github.com/ceph/ceph/pull/5856), runsisi)
- mailmap: modify member info ([pr#6468](http://github.com/ceph/ceph/pull/6468), Xiaowei Chen)
- mailmap: updates ([pr#6258](http://github.com/ceph/ceph/pull/6258), M Ranga Swami Reddy)
- mailmap: Xie Xingguo affiliation ([pr#6409](http://github.com/ceph/ceph/pull/6409), Loic Dachary)
- mds: implement snapshot rename ([pr#5645](http://github.com/ceph/ceph/pull/5645), xinxin shu)
- mds: messages/MOSDOp: cast in assert to eliminate warnings ([issue#13625](http://tracker.ceph.com/issues/13625), [pr#6414](http://github.com/ceph/ceph/pull/6414), David Zafman)
- mds: new filtered MDS tell commands for sessions ([pr#6180](http://github.com/ceph/ceph/pull/6180), John Spray)
- mds/Session: use projected parent for auth path check ([issue#13364](http://tracker.ceph.com/issues/13364), [pr#6200](http://github.com/ceph/ceph/pull/6200), Sage Weil)
- mon: should not set isvalid = true when cephx\_verify\_authorizer return false ([issue#13525](http://tracker.ceph.com/issues/13525), [pr#6306](http://github.com/ceph/ceph/pull/6306), Ruifeng Yang)
- osd: Add config option osd\_read\_ec\_check\_for\_errors for testing ([pr#5865](http://github.com/ceph/ceph/pull/5865), David Zafman)
- osd: add pin/unpin support to cache tier (11066) ([pr#6326](http://github.com/ceph/ceph/pull/6326), Zhiqiang Wang)
- osd: auto repair EC pool ([issue#12754](http://tracker.ceph.com/issues/12754), [pr#6196](http://github.com/ceph/ceph/pull/6196), Guang Yang)
- osd: drop the interim set from load\_pgs() ([pr#6277](http://github.com/ceph/ceph/pull/6277), Piotr Dałek)
- osd: FileJournal: \_fdump wrongly returns if journal is currently unreadable. ([issue#13626](http://tracker.ceph.com/issues/13626), [pr#6406](http://github.com/ceph/ceph/pull/6406), xie xingguo)
- osd: FileStore: add a field indicate xattr only one chunk for set xattr. ([pr#6244](http://github.com/ceph/ceph/pull/6244), Jianpeng Ma)
- osd: FileStore: LFNIndex: remove redundant local variable ‘obj’. ([issue#13552](http://tracker.ceph.com/issues/13552), [pr#6333](http://github.com/ceph/ceph/pull/6333), xiexingguo)
- osd: FileStore: potential memory leak if \_fgetattrs fails ([issue#13597](http://tracker.ceph.com/issues/13597), [pr#6377](http://github.com/ceph/ceph/pull/6377), xie xingguo)
- osd: FileStore: remove unused local variable ‘handle’ ([pr#6381](http://github.com/ceph/ceph/pull/6381), xie xingguo)
- osd: fix bogus scrub results when missing a clone ([issue#12738](http://tracker.ceph.com/issues/12738), [issue#12740](http://tracker.ceph.com/issues/12740), [pr#5783](http://github.com/ceph/ceph/pull/5783), David Zafman)
- osd: fix debug message in OSD::is\_healthy ([pr#6226](http://github.com/ceph/ceph/pull/6226), Xiaoxi Chen)
- osd: fix MOSDOp encoding ([pr#6174](http://github.com/ceph/ceph/pull/6174), Sage Weil)
- osd: init started to 0 ([issue#13206](http://tracker.ceph.com/issues/13206), [pr#6107](http://github.com/ceph/ceph/pull/6107), Sage Weil)
- osd: KeyValueStore: fix the name’s typo of keyvaluestore\_default\_strip\_size ([pr#6375](http://github.com/ceph/ceph/pull/6375), Zhi Zhang)
- osd: new and delete ObjectStore::Transaction in a function is not necessary ([pr#6299](http://github.com/ceph/ceph/pull/6299), Ruifeng Yang)
- osd: optimize get\_object\_context ([pr#6305](http://github.com/ceph/ceph/pull/6305), Jianpeng Ma)
- osd: optimize MOSDOp/do\_op/handle\_op ([pr#5211](http://github.com/ceph/ceph/pull/5211), Jacek J. Lakis)
- osd: os/chain\_xattr: On linux use linux/limits.h for XATTR\_NAME\_MAX. ([pr#6343](http://github.com/ceph/ceph/pull/6343), John Coyle)
- osd: reorder bool fields in PGLog struct ([pr#6279](http://github.com/ceph/ceph/pull/6279), Piotr Dałek)
- osd: ReplicatedPG: remove unused local variables ([issue#13575](http://tracker.ceph.com/issues/13575), [pr#6360](http://github.com/ceph/ceph/pull/6360), xiexingguo)
- osd: reset primary and up\_primary when building a new past\_interval. ([issue#13471](http://tracker.ceph.com/issues/13471), [pr#6240](http://github.com/ceph/ceph/pull/6240), xiexingguo)
- radosgw-admin: Checking the legality of the parameters ([issue#13018](http://tracker.ceph.com/issues/13018), [pr#5879](http://github.com/ceph/ceph/pull/5879), Qiankun Zheng)
- radosgw-admin: Create –secret-key alias for –secret ([issue#5821](http://tracker.ceph.com/issues/5821), [pr#5335](http://github.com/ceph/ceph/pull/5335), Yuan Zhou)
- radosgw-admin: metadata list user should return an empty list when user pool is empty ([issue#13596](http://tracker.ceph.com/issues/13596), [pr#6465](http://github.com/ceph/ceph/pull/6465), Orit Wasserman)
- rados: new options for write benchmark ([pr#6340](http://github.com/ceph/ceph/pull/6340), Joaquim Rocha)
- rbd: fix clone isssue ([issue#13553](http://tracker.ceph.com/issues/13553), [pr#6334](http://github.com/ceph/ceph/pull/6334), xinxin shu)
- rbd: fix init-rbdmap CMDPARAMS ([issue#13214](http://tracker.ceph.com/issues/13214), [pr#6109](http://github.com/ceph/ceph/pull/6109), Sage Weil)
- rbdmap: systemd support ([issue#13374](http://tracker.ceph.com/issues/13374), [pr#6479](http://github.com/ceph/ceph/pull/6479), Boris Ranto)
- rbd: rbdmap improvements ([pr#6445](http://github.com/ceph/ceph/pull/6445), Boris Ranto)
- release-notes: draft v0.94.4 release notes ([pr#5907](http://github.com/ceph/ceph/pull/5907), Loic Dachary)
- release-notes: draft v0.94.4 release notes ([pr#6195](http://github.com/ceph/ceph/pull/6195), Loic Dachary)
- release-notes: draft v0.94.4 release notes ([pr#6238](http://github.com/ceph/ceph/pull/6238), Loic Dachary)
- rgw: add compat header for TEMP\_FAILURE\_RETRY ([pr#6294](http://github.com/ceph/ceph/pull/6294), John Coyle)
- rgw: add default quota config ([pr#6400](http://github.com/ceph/ceph/pull/6400), Daniel Gryniewicz)
- rgw: add support for getting Swift’s DLO without manifest handling ([pr#6206](http://github.com/ceph/ceph/pull/6206), Radoslaw Zarzynski)
- rgw: clarify the error message when trying to create an existed user ([pr#5938](http://github.com/ceph/ceph/pull/5938), Zeqiang Zhuang)
- rgw: fix objects can not be displayed which object name does not cont… ([issue#12963](http://tracker.ceph.com/issues/12963), [pr#5738](http://github.com/ceph/ceph/pull/5738), Weijun Duan)
- rgw: fix typo in RGWHTTPClient::process error message ([pr#6424](http://github.com/ceph/ceph/pull/6424), Brad Hubbard)
- rgw: fix wrong etag calculation during POST on S3 bucket. ([issue#11241](http://tracker.ceph.com/issues/11241), [pr#6030](http://github.com/ceph/ceph/pull/6030), Radoslaw Zarzynski)
- rgw: mdlog trim add usage prompt ([pr#6059](http://github.com/ceph/ceph/pull/6059), Weijun Duan)
- rgw: modify the conditional statement in parse\_metadata\_key method. ([pr#5875](http://github.com/ceph/ceph/pull/5875), Zengran Zhang)
- rgw: refuse to calculate digest when the s3 secret key is empty ([issue#13133](http://tracker.ceph.com/issues/13133), [pr#6045](http://github.com/ceph/ceph/pull/6045), Sangdi Xu)
- rgw: remove extra check in RGWGetObj::execute ([issue#12352](http://tracker.ceph.com/issues/12352), [pr#5262](http://github.com/ceph/ceph/pull/5262), Javier M. Mellid)
- rgw: support core file limit for radosgw daemon ([pr#6346](http://github.com/ceph/ceph/pull/6346), Guang Yang)
- rgw: swift use Civetweb ssl can not get right url ([issue#13628](http://tracker.ceph.com/issues/13628), [pr#6408](http://github.com/ceph/ceph/pull/6408), Weijun Duan)
- rocksdb: build with PORTABLE=1 ([pr#6311](http://github.com/ceph/ceph/pull/6311), Sage Weil)
- rocksdb: remove rdb source files from dist tarball ([issue#13554](http://tracker.ceph.com/issues/13554), [pr#6379](http://github.com/ceph/ceph/pull/6379), Kefu Chai)
- rocksdb: use native rocksdb makefile (and our autotools) ([pr#6290](http://github.com/ceph/ceph/pull/6290), Sage Weil)
- rpm: ceph.spec.in: correctly declare systemd dependency for SLE/openSUSE ([pr#6114](http://github.com/ceph/ceph/pull/6114), Nathan Cutler)
- rpm: ceph.spec.in: fix libs-compat / devel-compat conditional ([issue#12315](http://tracker.ceph.com/issues/12315), [pr#5219](http://github.com/ceph/ceph/pull/5219), Ken Dreyer)
- rpm: rhel 5.9 librados compile fix, moved blkid to RBD check/compilation ([issue#13177](http://tracker.ceph.com/issues/13177), [pr#5954](http://github.com/ceph/ceph/pull/5954), Rohan Mars)
- scripts: release\_notes can track original issue ([pr#6009](http://github.com/ceph/ceph/pull/6009), Abhishek Lekshmanan)
- test/libcephfs/flock: add sys/file.h include for flock operations ([pr#6310](http://github.com/ceph/ceph/pull/6310), John Coyle)
- test\_rgw\_admin: use freopen for output redirection. ([pr#6303](http://github.com/ceph/ceph/pull/6303), John Coyle)
- tests: allow docker-test.sh to run under root ([issue#13355](http://tracker.ceph.com/issues/13355), [pr#6173](http://github.com/ceph/ceph/pull/6173), Loic Dachary)
- tests: ceph-disk workunit uses configobj ([pr#6342](http://github.com/ceph/ceph/pull/6342), Loic Dachary)
- tests: destroy testprofile before creating one ([issue#13664](http://tracker.ceph.com/issues/13664), [pr#6446](http://github.com/ceph/ceph/pull/6446), Loic Dachary)
- tests: port uniqueness reminder ([pr#6387](http://github.com/ceph/ceph/pull/6387), Loic Dachary)
- tests: test/librados/test.cc must create profile ([issue#13664](http://tracker.ceph.com/issues/13664), [pr#6452](http://github.com/ceph/ceph/pull/6452), Loic Dachary)
- tools/cephfs: fix overflow writing header to fixed size buffer (#13816) ([pr#6617](http://github.com/ceph/ceph/pull/6617), John Spray)
- tools: ceph-monstore-update-crush: add “–test” when testing crushmap ([pr#6418](http://github.com/ceph/ceph/pull/6418), Kefu Chai)
- tools:remove duplicate references ([pr#5917](http://github.com/ceph/ceph/pull/5917), Bo Cai)
- vstart: grant full access to Swift testing account ([pr#6239](http://github.com/ceph/ceph/pull/6239), Yuan Zhou)
- vstart: set cephfs root uid/gid to caller ([pr#6255](http://github.com/ceph/ceph/pull/6255), John Spray)

### GETTING CEPH

- Git at [git://github.com/ceph/ceph.git](http://github.com/ceph/ceph)
- Tarball at [http://ceph.com/download/ceph-10.0.0.tar.gz](http://ceph.com/download/ceph-10.0.0.tar.gz)
- For packages, see [http://ceph.com/docs/master/install/get-packages](http://ceph.com/docs/master/install/get-packages)
- For ceph-deploy, see [http://ceph.com/docs/master/install/install-ceph-deploy](http://ceph.com/docs/master/install/install-ceph-deploy)