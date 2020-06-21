## common

> jmap -dump:format=b,file=xxxxx/yyyyy 442491

> jmap -histo 962198

> -XX:+HeapDumpBeforeFullGC、-XX:+HeapDumpAfterFullGC

> jinfo -flags 390032

> jinfo -flag +HeapDumpBeforeFullGC 390032

> jinfo -flag +HeapDumpAfterFullGC 390032

## gperftools

> export LD_PRELOAD=/.../gperftools-2.5/lib/libtcmalloc.so

> export HEAPPROFILE=/.../gperftools/data/

> export HEAP_PROFILE_ALLOCATION_INTERVAL=2000000000


