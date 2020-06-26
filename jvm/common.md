## jmm的理解
```
jmm的关键技术点是围绕着多线程的原子性、可见性、有序性来建立的

指令重排可以保证串行语义一致，但是不能保证多线程间的语义一致；指令重排是减少中断的一种技术

哪些指令不能重排，happen-before原则

```
## happen-before原则
```
程序次序规则： 在一个单独的线程中，按照程序代码的执行流顺序，（时间上）先执行的操作happen—before（时间上）后执行的操作
（同一个线程中前面的所有写操作对后面的操作可见）

管理锁定规则：一个unlock操作happen—before后面（时间上的先后顺序）对同一个锁的lock操作。
（如果线程1解锁了monitor a，接着线程2锁定了a，那么，线程1解锁a之前的写操作都对线程2可见（线程1和线程2可以是同一个线程））

volatile变量规则：对一个volatile变量的写操作happen—before后面（时间上）对该变量的读操作。
（如果线程1写入了volatile变量v（临界资源），接着线程2读取了v，那么，线程1写入v及之前的写操作都对线程2可见（线程1和线程2可以是同一个线程））

传递性：如果操作A happen—before操作B，操作B happen—before操作C，那么可以得出A happen—before操作C。
（A h-b B ， B h-b C 那么可以得到 A h-b C）

线程启动规则：Thread.start()方法happen—before调用用start的线程前的每一个操作。
（假定线程A在执行过程中，通过执行ThreadB.start()来启动线程B，那么线程A对共享变量的修改在接下来线程B开始执行前对线程B可见。注意：线程B启动之后，线程A在对变量修改线程B未必可见。）

线程终止规则：线程的所有操作都happen—before对此线程的终止检测，可以通过Thread.join（）方法结束、Thread.isAlive（）的返回值等手段检测到线程已经终止执行。
(线程t1写入的所有变量，在任意其它线程t2调用t1.join()，或者t1.isAlive() 成功返回后，都对t2可见。)

线程中断规则：对线程interrupt()的调用 happen—before 发生于被中断线程的代码检测到中断时事件的发生。
(线程t1写入的所有变量，调用Thread.interrupt()，被打断的线程t2，可以看到t1的全部操作)

对象终结规则：一个对象的初始化完成（构造函数执行结束）happen—before它的finalize（）方法的开始。
(对象调用finalize()方法时，对象初始化完成的任意操作，同步到全部主存同步到全部cache。)
```