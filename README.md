This is a compendium of presentations and reports I have worked on during the MIRI HPC master's at UPC. They include complex, advanced topics on computer architecture, relevant papers from MICRO/ISCA/HPCA conferences (recent publications and seminal works from the 80s/90s alike), as well as hands-on tinkering with RISC-V toolchains and the CVA6 processor from OpenHWGroup as part of a subject's final project. Also, two presentations near and dear to my heart are included in this repository, from the early stages of my master's thesis development learning about main memory and memory controllers by ceremoniously bashing my head against the [DRAMsim3 simulator](https://github.com/umd-memsys/DRAMsim3).

As a formerly-inexperienced student with not much background in computer architecture, I have strived to squeeze every ounce of wisdom and knowledge there was to be had from subjects' contents, projects throughout the master's and my research work within the [CAOS group at BSC](https://www.bsc.es/discover-bsc/organisation/scientific-structure/computer-architecture-operating-systems-caos). The purpose of this repository is not only to show what I have learned after much struggle and hard work, but also to share the knowledge I have gained by uploading the series of presentations and reports I am most fond of, in retrospect, after the fact.

Don't be scared by the high page-counts of slide presentations: they are but a byproduct of my meticulousness in attempting to explaining obscure, esoteric concepts as graphically and as "approachably" as possible. Hand-crafted transition effects from slide to slide with brightly-coloured arrows and helplessly insightful comments tend to get out of hand quickly if the concept at hand is interesting and/or complex enough. The more traditional text-based reports also suffer from my unbridled pedantry, only this time in the form of unnecessarily-long and convoluted sentences often spanning two, three, even four lines within a paragraph.

Here's an outline of what each file contains (all source papers are included in the folder above and are numbered accordingly):

  - **_ECC in CVA6/Ariane processor_**: presentation detailing ECC basics (from parity, to Hamming codes, to SEC-DED, to [Hsiao70] XOR combinations, [CMOS VLSI Design](http://pages.hmc.edu/harris/cmosvlsi/4e/index.html) and [Memory Systems: Cache, DRAM, Disk's](https://shop.elsevier.com/books/memory-systems/jacob/978-0-12-379751-3) chapter 30 as source material), development of [Verilog modules](https://github.com/sergioge99/ECC-Verilog-Modules-for-Caches) for encoding/decoding/fault injections to test designs, exploration of the CVA6/Ariane processor's cache subsytem and a lengthy tutorial on (1) how to make the processor run, (2) how to use OpenHWGroup's core-v-verif repository and (3) how to modify/fix the CVA6 repository to make it output .vcd and .fst waveform files for debugging.
  
  - **_Verification tutorial CVA6_**: the previous tutorial on (1) how to make the processor run, (2) how to use OpenHWGroup's core-v-verif repository and (3) how to modify/fix the CVA6 repository to make it output .vcd waveform files for debugging. It includes tinkering with the riscv-gnu-toolchain, Verilator compilation options for the processor, verification of the processor with various RISC-V compliance tests via the core-v-verif repository. Final pages include the entire installation script for all the tools used during the project.

  - **_RISC-V Summit 2022 report_**: a series of talks from the North American edition of the summit and a more formal tutorial on the riscv-gnu-toolchain on its usage, cross-compilation and QEMU+GDB debugging.

    - [RISC-V and the Elf: A Story About Randomisation for Safe and Secure Critical Systems](https://www.youtube.com/watch?v=To_wmz8xIVU&list=PL85jopFZCnbPPRyjl_qMQ50DPq_iQKhFg&index=94): the more technical of the three talks, it focuses on the practice of software randomisation, what it is and how it is relevant vis-a-vis secure critical systems; the talk revolves around a publication on the matter from the talk’s speaker, Leonidas Kosmidis from UPC-BSC.
    - [Is RISC-V HPC? RISC-V is HPC!](https://www.youtube.com/watch?v=HYSvMBWy3cM&list=PL85jopFZCnbPPRyjl_qMQ50DPq_iQKhFg&index=13&t=7s): an introspective look into open-source hardware, HPC and related European initiatives from the viewpoint of John Davis, SIG HPC Chair and BSC.
    - [RISC-V for Aerospace and Defense Applications](https://www.youtube.com/watch?v=GrTjDgSpSmY&list=PL85jopFZCnbPPRyjl_qMQ50DPq_iQKhFg&index=55): a very interesting talk from SiFive executive Tom Leahy on RISC-V funding initiatives under the umbrella of the US’s CHIPS Act 2022 and how the Aerospace and Defense (A&D) market is specially interested in the vertical-integration possibilities that an open ISA provides, not only in meeting highly-specific requirements from defense-related projects, but also in the industrial and commercial autonomy a national semiconductor industry paired with a "domestic" ISA could bring to the table (a bit number-heavy, but the between-the-lines context and tone of the talk was very telling and interesting in my view).
    - [Toolchains tutorial](https://www.youtube.com/watch?v=mBNX843U2qE&list=PL85jopFZCnbPPRyjl_qMQ50DPq_iQKhFg&index=68): a hands-on session by Christoph Müllner of VRULL working with the 4. Improving Instruction Cachesriscv-gnu-toolchain project, as well as an theoretical introductory part on toolchain-related concepts, terminology and definitions.

  - **_Energy-efficient IQ archs.pdf_**: a presentation on [two](https://ieeexplore.ieee.org/document/9923800) [different](https://ieeexplore.ieee.org/document/7011406) approaches aiming to mitigate the high energy consumption of out-of-order issue queues: one based on using a series of parallel, in-order issue queues for depence-chain steering and the other exploiting ready-at-dispatch instructions by executing them in an intermediate execution stage placed before traditional out-of-order stages, avoiding the usage of the OoO IQ when applicable.

  - **_Improving Instruction Caches_**: both the final presentation and report covering four seminal papers (see source material folder) about compiler-level techniques and optimizations to mitigate aliasing conflicts in direct-mapped caches.

  - **_Memory Dependence Prediction Using Store Sets_**: a comprehensive, detailed explanation of how to deal with memory-order violations between stores and loads as a result of load speculation, as put forward in [Chrysos and Emer](https://ieeexplore.ieee.org/document/694770)'s paper.

  - **_"DRAMsim3's memory controller" and "Tracking contention in memory controllers"_**: two presentations covering the basics of DRAMsim3's memory controller (from front-end transaction management and write-batching to generation of DRAM commands and enforcement of JEDEC timing constraints) and basics ideas on contention-tracking between DRAM commands within the MC. The last presentation outlines one of the initial, basic ideas of multicore contention-tracking in DRAM for my master's final thesis project.
