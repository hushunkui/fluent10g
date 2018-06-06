![FlueNT10G](logo.svg)

#### What is FlueNT10G?

FlueNT10G is an open-source, free-to-use FPGA-based network tester. FlueNT10G
can precisely replay pre-recorded or synthetically generated network traces,
capture incoming network traffic and accurately record network latencies on a
per-packet basis.

#### What replay/capture throughput does FlueNT10G achieve?

FlueNT10G can concurrently replay and capture network traffic on three 10 Gbps
network interfaces for all packet sizes. When operated exclusively in replay or
capture mode, four 10 Gbps network interface can be served.

#### How precise is the replay of network traces?

FlueNT10G replays traffic according to the timestamps included in the trace
file. The 10G MAC IP cores are operated with a clock frequency of 156.25 MHz.
Thus, the achievable replay precision is 6.4 nanoseconds.

#### How accurate are traffic capturing and latency measurements?

FlueNT10G records the arrival time (and optionally the latency) of each packet
it receives. Since the 10G MAC IP cores are operated with a clock frequency of
156.25 MHz, the timestamping precision of our design is 6.4 nanoseconds.
However, we found that the 10G MAC IP core on Xilinx Virtex-7 devices
introduces minor delay variations on the receive-side. In our experiments we
observed a timestamp precision of 25.6 nanoseconds. We plan to port our design
to an UltraScale FPGA board in the future to achieve even higher accuracy.

#### Is there a maximum trace file size?

Instead of pre-loading trace data to the memory of the FPGA board before replay
can start, FlueNT10G continuously streams data between host computer and the
FPGA board during active measurements. Thus, the maximum trace file size is
only limited by the memory capacity of the host computer. The same applies to
network capture data.

#### What do I need to use FlueNT10G?

FlueNT10G is composed of an FPGA-based hardware component, as well as software
running on a standard PC. Currently our implementation targets the [NetFPGA-SUME](https://netfpga.org) board. However, if you are familiar with
FPGA hardware development, the effort to port our design to another board
should be manageable. To generate the FPGA bitstream, you need a license for
the Xilinx Vivado tool chain. Additionally, a license for the [Xilinx 10
Gigabit Ethernet MAC IP core](https://www.xilinx.com/products/intellectual-property/do-di-10gemac.html)
is required. To sum up, you will need:

* NetFPGA-SUME or (with some development effort) another PCIe Gen3 FPGA board
* Standard PC with a free PCIe Gen3 slot
* License for Xilinx Vivado Design Suite
* License for Xilinx 10 Gigabit Ethernet MAC IP core

#### Where can I find more information?

FlueNT10G will be presented at the International Conference on Field
Programmable Logic & Applications 2018 in Dublin, Ireland. You can find our
paper [here](xxx). BibTeX:

```
@inproceedings{fluent10g-fpl2018,
  author={{Oeldemann, Andreas and Wild, Thomas and Herkersdorf, Andreas}},
  title={{FlueNT10G: A Programmable FPGA-based Network Tester for Multi-10-Gigabit Ethernet}},
  booktitle={Field Programmable Logic and Applications (FPL), 2018 28th International Conference on},
  year={2018}
}
```

#### Is there in in-depth documentation?

We are currently working on this! Please come back soon!

#### Who is behind FlueNT10G? How can I get in touch with the team?

FlueNT10G is actively being developed by a team of researchers at the [Chair of
Integrated Systems](https://www.lis.ei.tum.de) at the Technical University of
Munich. Please contact
[Andreas Oeldemann](http://www.lis.ei.tum.de/?id=oeldemann) in case of questions,
feedback, problems and so on.