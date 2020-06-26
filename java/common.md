## common
```
https://download.java.net/java/GA/jdk11/9/GPL/openjdk-11.0.2_linux-x64_bin.tar.gz	jdk11
```

## thread
```
public final void stop()    //可能强行将执行到一半的线程终止，包括释放锁，引起数据不一致的问题
    // deprecated: true

public static boolean interrupted()    //判断是否被中断，并清除当前中断状态
public boolean isInterrupted()
public void interrupt()
    // sleep/wait/join由于中断而抛出异常，此时它会清除中断标记；需要在异常处理中，再次设置中断标记位

public final native void wait(long var1) throws InterruptedException    //Object
public final native void notify()    //Object
    // wait与wait(timeout)的区别是timeout后会重新尝试获取锁

public final void suspend()
public final void resume()
    // deprecated: true
    // suspend导致线程暂停的时候，不会释放资源，也不会释放锁；如果resume在suspend之前执行了，锁就更不会被释放
    // suspend挂起后，其状态是runnable

public static native void sleep(long var0) throws InterruptedException

public final void join() throws InterruptedException
public static native void yield()

```