## common
```
jmap -dump:format=b,file=xxxxx/yyyyy 442491
jmap -histo 962198
jmap -histo:live 446481
jstat -gcutil 122327 1000
jcmd 719932 VM.native_memory summary scale=MB

jinfo -flags 390032
jinfo -flag +HeapDumpBeforeFullGC 390032
jinfo -flag +HeapDumpAfterFullGC 390032

-XX:+HeapDumpBeforeFullGC -XX:+HeapDumpAfterFullGC -XX:+PrintAdaptiveSizePolicy -XX:G1HeapRegionSize=16M

concurrent humongous allocation
G1 Humongous Allocation
```

## gperftools
```
export LD_PRELOAD=/.../gperftools-2.5/lib/libtcmalloc.so
export HEAPPROFILE=/.../gperftools/data/
export HEAP_PROFILE_ALLOCATION_INTERVAL=2000000000
```

## jmap histo instance
```
Element Type        Encoding
boolean             Z
byte                B
char                C
class or interface  Lclassname;
double              D
float               F
int                 I
long                J
short               S 
```
