========================================
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

* Workload optimized frequency

  * Manage energy between threads/cores with reduces wakeup latency

* Optical-style signaling technology delivers 25Gbit/sec

  * Multi-drawer SMP connection
  * NVLINK 2 GPU accelerator attach
  * New CAPI accelerator attach

* New interrupt architecture

  * Today: Interrupt arrives, interrupt controller can't find the partition
    where the interrupt is located
  * POWER9: Hardware accelerated interrupts come through with a partition ID
    attached to it, then broadcast goes out to find out if the partition is
    executing something
  * Helps a lot with densely loaded hypervisor

* Accelerators

  * Fewer hypervisor calls, user mode virtualization management
  * GZIP accelerator for compression/decompression (on the CPU die, no
    overhead for GZIP compression/decompression)
  * AES cryptography support
  * True random number generation
  * Data mover

* New CAPI

  * Accelerator has a Power Service Layer (PSL) to reduce latency in
    communicating with the POWER9 chip
  * Optimized CAP protocal to talk to accelerators
  * PSL is moved to POWER9 die rather than accelerator -- reduces latency

* 192GB/s duplex bandwidth on PCIe Gen 4 (48 lanes)

  * Should see some adapters coming for Gen4 soon -- especially InfiniBand
    adapters

* 300GB/s duplex bandwidth for Common Link (25Gbit/sec x 48 lanes)
