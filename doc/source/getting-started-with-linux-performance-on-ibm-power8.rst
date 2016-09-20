====================================================
Getting Started with Linux Performance on IBM POWER8
====================================================

*Speaker: Steve Nasypany*

.. note::

   I stopped taking notes during this session because almost all of the useful
   material in this talk is already in the slides. There are lots of links
   and details about which utilities you can use.

* IBM Developerworks PowerLinux Community has the latest on Linux
* ``lpcpu`` - Linux Performance Customer Profiler Utility

  * Equivalent to ``perfpmr`` in AIX
  * Digs up lots of diagnostic data from the server, deeper profiling

* ``ppc64_cpu --frequency`` -- check to see if the CPU frequency was set very
  low during a PoC (previous users may have set that)
* Use ``nstress`` on AIX/Linux to test CPU/memory/storage
* Linux pages more data out to swap than AIX does

  * AIX won't page out data to swap after boot unless memory usage is > 97%

* Use ``tuned`` to manage performance improvements
* Recent research in the Completely Fair Scheduler (CFS) scheduler shows that
  it needs significant optimizations

  * Read *The Linux Scheduler: a Decade of Wasted Cores*

* Linux boots to the highest SMT setting (8) by default
* Thread counts can be controlled with ``ppc64_cpu`` command
* Linux uses virtual CPU's (not the same as AIX's Virtual Processors)

  * AIX Virtual Processor maps to the capacity of *one physical core*
  * Linux CPU maps to hardware thread, which could be a single core, or a
    single thread in a core (depending on SMT configuration)

* Increasing SMT provides additional lanes for processing, but it won't give
  better performance for a single threaded application
* RHEL 7.1 had SMT fixes for SMT8 performance issues (exact defect fix is
  unknown)
* CPU accounting is different in AIX and Linux

  * Linux doesn't use calibrated PURR metrics
  * If a single SMT thread is busy in Linux, you see core CPU usage as 12.5%

* CPU Metrics

  * In AIX, idle time is sent back to the hypervisor
  * In Linux, the *steal* metric is used to identify that other guests were
    using the CPU at the time
  * High steal time means the other guests on the server are using all of the
    CPU time
  * ``nmon`` shows steal time very well
  * ``nmon`` v16 has GPU stats and CPU interrupt stats

* NUMA

  * Use ``numastat`` and ``numactl`` in Linux to see how much RAM is assigned
    to each CPU and adjust threads
  * In POWER7, optimizing affinity could save ~ 35% performance
  * In POWER8, it's more like 10% (since POWER8 has more bandwidth)

