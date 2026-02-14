---
title: "Research"
permalink: /en/research/
lang: en
---

Our research team works on themes such as those listed below. We are also interested in a wide range of topics that may fall outside these categories, as long as they can contribute to the development of practical quantum computers.

For a complete list of papers and talks, please see [Publications](../publication/). For information aimed at students, please refer to the [For Students](../student/) page.

## Computer Architecture

### Overview
The design and interfaces of modern computers are meticulously engineered to handle complex tasks while maintaining high performance and generality. Put differently, if a CPU interface required users to directly provide internal voltage-level signals, the development of modern computing would not have been possible. In contrast, in today’s quantum computing research, the gap between theory and implementation is enormous due to the difficulty of modeling quantum devices and the complexity of quantum error-correction theory, and concrete instruction sets and internal logic have not yet been established. To bridge this gap, we aim to develop technologies that enable quantum computing systems with reliability as well as “computer-like” capabilities commonly expected in practice, such as branching and loop processing. Furthermore, by constructing instruction sets, runtimes, and internal logic suited to various hardware platforms and applications, we explore the behavior of fault-tolerant quantum computers that are both versatile and practical. We also conduct system design studies and development in national projects such as Q-LEAP and Moonshot, with a long-term view toward the future evolution of quantum computers.

### Examples of past research
- **Implementation of error estimation mechanisms:** We designed circuits for real-time quantum error estimation and evaluated their performance.  
  [DAC2021](https://arxiv.org/abs/2103.14209) [HPCA2022](https://ieeexplore.ieee.org/document/9773181) [VLSISymp2024](https://ieeexplore.ieee.org/document/10185351)
- **Design of error estimation mechanisms:** We proposed methods to perform quantum error correction faster and with higher accuracy.  
  [PRR2020](https://arxiv.org/abs/1801.04377) [arxiv2025](https://arxiv.org/abs/2509.01892) [arxiv2025](https://arxiv.org/abs/2508.07913)
- **Resource estimation and bottleneck analysis:** We predicted quantum computer execution time and, based on that, identified bottlenecks and optimized system designs.  
  [npjQI2024](https://arxiv.org/abs/2210.14109) [arxiv2024](https://arxiv.org/abs/2411.17519)
- **Load/store design:** We separated memory and processors in a quantum computer, proposed a highly general instruction set, and realized memory regions with high efficiency.  
  [HPCA2025](https://arxiv.org/abs/2412.20486)
- **Interconnects:** For two-dimensional qubit arrays, we designed mechanisms to build reliable communication on top of noisy, high-error-rate links.  
  [PRR2026](https://arxiv.org/abs/2503.14894)
- **Distributed networks:** We proposed techniques to appropriately multiplex entanglement generation and hide communication latency off the critical path.  
  [arxiv2026](https://arxiv.org/abs/2601.09374)

## Programming and Compilation

### Overview
Existing quantum programs are often described in low-level representations such as quantum circuits. While such descriptions are clear and concise for small-scale computations, they introduce many difficulties and inconveniences when aiming for fault-tolerant quantum computers that outperform supercomputers. Today, because instruction sets for fault-tolerant quantum computers and their associated standard compilers are not yet established, it remains unclear what optimizations should be performed manually or automatically, and which benchmarks best capture the effective performance of fault-tolerant systems. We explore what system software, such as compilers, debuggers, profilers, and simulators, should look like for quantum computing, with the goal of bringing programming principles and methodologies used to extract peak performance on supercomputers into the quantum domain. Based on these software frameworks, we formulate problems for maximizing quantum computer performance as well-structured mathematical problems, and use algorithms and data structures to optimize and verify programs. In addition, by clarifying what performance characteristics applications demand from the machine through such system software, we identify how quantum computers should be designed in terms of performance trade-offs.

### Examples of past research
- **Decomposing large instructions:** We proposed a framework to decompose abstract program instructions into fault-tolerant primitive operations executable on real devices, enabling efficient execution.  
  [arxiv2024](https://arxiv.org/abs/2401.15829)
- **Error-aware optimization:** By running multiple programs and applying statistical processing, we reduce T-gates and lower error-estimation failure rates without modifying the hardware.  
  [PRXQ2022](https://arxiv.org/abs/2010.03887) [npjQI2025](https://arxiv.org/abs/2405.15565)
- **Program verification:** We proposed fast methods to verify that logical instructions on fault-tolerant quantum computers can still be executed safely after hardware mapping.  
  [APLAS2024](https://arxiv.org/abs/2409.00529) [QCE2024](https://ieeexplore.ieee.org/document/10821167)
- **Program parallelization:** We parallelized phase-estimation subroutines with small overhead and improved effective throughput until parallel efficiency saturated.  
  [npjQI2024](https://arxiv.org/abs/2210.14109)
- **Job scheduling:** We propose efficient job-scheduling methods grounded in the mechanisms of fault-tolerant quantum computing.  
  [QCE2025](https://arxiv.org/abs/2505.06741)

## Large-Scale Quantum Device Control

### Overview
To realize quantum computers, a variety of quantum devices, such as superconducting circuits, neutral atoms, photonics, ions, and semiconductors, have been proposed as physical media for storing quantum information, and experiments at scales beyond 100 qubits are now possible. However, practical quantum computation is often considered to require controlling at least tens of thousands of qubits for hours or longer at today’s levels of accuracy. When operating such large-scale quantum devices for long durations, variations in device characteristics and temporal drift, issues that were not dominant in small-scale laboratory experiments, emerge as major obstacles to scaling. We work closely with experimental physicists and, at times, directly control real devices, to design computing systems that leverage the strengths of the underlying physical platform while compensating for its weaknesses. Concretely, we model discrepancies between theory and experiment as computer system design challenges, and address them from a computer-architectural perspective to remove obstacles to future scaling. We also incorporate the resulting ideas into software for controlling quantum devices with realistic time and cost, and develop testbenches to evaluate our proposed designs.

### Examples of past research
- **Adapting to error-rate fluctuations:** We proposed mechanisms to non-destructively detect error-rate variations (e.g., burst errors) via error estimation and dynamically switch error-correction methods.  
  [MICRO2022](https://arxiv.org/abs/2501.00331)
- **Handling device variability:** By storing qubit-parameter variability in compressed tables, we enabled fast, variability-aware error estimation on FPGAs.  
  [ASPDAC2023](https://ieeexplore.ieee.org/document/10044818)
- **Evaluating the impact of leakage errors:** We evaluated the impact of leakage errors, in which qubits leave the computational subspace.  
  [NJP](https://arxiv.org/abs/2308.08186)
- **Evaluating the impact of coherent errors:** We proposed an efficient method to evaluate the impact of coherent rotation errors on qubits.  
  [PRL2017](https://arxiv.org/abs/1703.03671)
- **Mitigating loss errors:** Using information available when loss-type errors occur (e.g., in photonic systems), we improved the accuracy and speed of error estimation.  
  [arxiv2025](https://arxiv.org/abs/2509.08408)

## System and Software Development

### Overview
Developing and operating quantum computers requires a diverse set of software tools. Moreover, software is indispensable for making quantum computers usable across a wide range of domains and for enabling concrete economic value creation through real-world use. Our team develops software to accelerate quantum computer development and increase its value. Such software must be properly designed, highly extensible and reusable, and managed under appropriate licenses. In modern quantum computer development, two efforts proceed in parallel: a bottom-up approach that maximizes the use of existing quantum computers, and a top-down approach that forecasts practical-scale systems and works backward to determine the required system architecture. The former demands smooth adaptation to frequent technology updates, while the latter requires loosely coupled systems and high compatibility that can withstand technological variation. Depending on the goals and lifecycle of a given technology or architecture, we also work on systematizing methodologies for efficiently accumulating and refining software and documentation assets with the right level of abstraction and generality.

### Examples of our efforts
- **Quantum circuit simulator:** We developed Qulacs, a high-performance quantum circuit simulator. We implemented SIMD-based optimizations for major gates, added support for general operations needed in research (such as completely positive maps and instruments), and accelerated execution via gate synthesis at various levels.  
  [Quantum2021](https://arxiv.org/abs/2011.13524) [github](https://github.com/qulacs/qulacs)
- **Superconducting-qubit measurement tools:** For superconducting-qubit experiments, we separated an abstract layer (e.g., quantum circuits and Hamiltonian dynamics) from the analog control-instrument layer (e.g., local oscillators and arbitrary waveform generators) and built infrastructure enabling versatile measurements. We also developed software for automated qubit calibration.  
  [release](https://www.riken.jp/pr/news/2023/20231005_1/index.html)
- **Toolchain for fault-tolerant quantum computing:** We built a compiler that describes programs using a compact intermediate representation inspired by LLVM and translates them into an instruction set for fault-tolerant quantum computing. We also developed a profiler to predict program execution time and a visualizer to show runtime memory usage.
