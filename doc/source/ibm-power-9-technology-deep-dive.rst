IBM POWER9 Technology Advanced Deep Dive
========================================

*Speaker: Jeff Stuecheli*

* POWER9 will have multiple chips, like POWER8

  * Each chip is optimized for certain workloads, like Cognitive, HPC, Cloud
    and Enterprise

* Core counts

  * Memory signaling surrounds the cores
  * Core size is customizable

* NVLink 2.0, CAPI 2.0 and New CAPI (25Gbit/sec)
* PCIe Gen4 with 48 lanes
* Quality of Service controls are built in for cloud/virtualized workloads
* 25Gbit/sec common link interface (will be called "Blue Link")

  * For accelerators or remote SMP

* 8 billion transistors
* Two chips:

  * SMT4 Core

    * 24 SMT4 cores per chip
    * Linux optimized
    * Commodity packaging form factor
    * 8 DDR4 ports max

  * SMT8 Core

    * 12 SMT8 cores per chip
    * PowerVM optimized
    * Buffered memory attached

* Latency is greatly reduced between cores
* Efficient cores deliver 2x compute resources per socket
* Hardware-assisted garbage collection
* New interrupt architecture

  * Automated partition routing for extreme virtualization
  * Could be helpful for busy clouds
