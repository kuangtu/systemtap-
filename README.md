# systemtap-examples
对于systemtap自带的示例，进行注释学习。



## Best Example

根据文档中的说明，对于最佳示例从语法、运行过程等方面进行分析。

根据文档说明，最佳示例如下：

![best example](jpg/best example.jpg)

对于上面的示例进行分析和注释。

## general/varwatch.stp - Watch a Variable Changing Value in a Thread

该脚本放置了一组探测器（由 $1 指定），每个探测器监视某个上下文 $variable 表达式（由 $2 指定）的状态。每当值发生变化时，就会跟踪活动线程的事件。


## process/proctop.stp - Periodically Print Process Information With History

每5秒钟，打印出25个占用系统时间最长的进程的列表，并提供有关这些进程的信息。


## profiling/fntimes.stp - Show Functions Taking Longer Than Usual

fntimes.stp脚本监控给定函数族（假定非递归）的执行时间历史记录。然后，每次（在预热间隔之后）与历史最大值进行比较。如果超过某个阈值（250%），则打印一条消息


# tapeset
示例中包含了tapset库，对于主要的库进行说明。

## scheduler.stp

```
probe scheduler.process_exit =
        __scheduler.process_exit.tp !,
        __scheduler.process_exit.kp
{
        name = "process_exit"
}
```

`process_exit`方法执行了了`process_exit.tp`，监测内核函数`kernel.trace("sched_process_exit")`。








