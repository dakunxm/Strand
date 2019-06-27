# Strand

#### Description
对Boost::Asio::Strand进行推导，并使用[Remotery](https://github.com/Celtoys/Remotery)可视化线程执行和函数调用的情况。

This is an implement for Boost::Asio::Strand.To visually demonstrate what happens with the IO threads and handlers, I’ve used [Remotery](https://github.com/Celtoys/Remotery) .

测试代码模拟了4个工作线程和8个连接。每个连接会给出一组计算任务到任务队列中，每个任务耗时5 ms到15 ms。

The code used emulates 4 worker threads, and 8 connections. Handlers (aka *work items*) with a random workload of `[5ms,15ms]`for a random connection are placed in the worker queue.

测试比较:

Without strand

![time-slice](/imgs/time-slice.png)

With strand

![time-slice](/imgs/time-slice-strand.png)

more details in my blog: [Strands](https://wkkkkk.github.io/2019/06/06/strands/)