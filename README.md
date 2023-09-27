# FPGA-based Emulation of Quantum Computing

## Table of Contents

1. [Abstract](#abstract)
2. [Introduction](#introduction)
3. [Objective/Background](#objectivebackground)
4. [Literature Review/Research Papers](#literature-reviewresearch-papers)
5. [Methodology/Design Flow](#methodologydesign-flow)
   - [Simulation vs. Emulation Differentiation](#simulation-vs-emulation-differentiation)
   - [Quantum Circuit Fundamentals](#quantum-circuit-fundamentals)
   - [Hardware Implementation](#hardware-implementation)
   - [Emulating Quantum Circuit Behaviour](#emulating-quantum-circuit-behaviour)
   - [HDL-Based Simulation of Quantum Circuits](#hdl-based-simulation-of-quantum-circuits)
   - [Emulation Overview](#emulation-overview)

## Abstract <a name="abstract"></a>

Quantum computing holds immense promise, yet its practical development faces challenges due to the exponential complexity of simulating quantum algorithms on classical computers. Existing software-based simulators struggle to capture the parallelism inherent in quantum computation. To address this, our project introduces a novel approach: hardware-based quantum algorithm emulation using Field Programmable Gate Arrays (FPGAs). Leveraging FPGA technology enables parallel computation, offering significant speed-ups compared to state-of-the-art software simulators. Additionally, it provides crucial insights into precision requirements for simulating quantum circuits. By bridging the gap between quantum algorithms and FPGA-accelerated simulation, we aim to advance quantum computation accessibility and understanding.

## Introduction <a name="introduction"></a>

Quantum computing, with its promise of exponentially faster computation for certain tasks through quantum mechanical phenomena like entanglement and superposition, has captivated the scientific community. However, practical quantum computers remain in their infancy, often confined to the research labs of major corporations. This limited accessibility has spurred the development of classical simulators for quantum algorithms, designed to bridge the gap between theoretical promise and practical experimentation. Simulating quantum algorithms on classical computers is a formidable challenge due to the resource-intensive nature of quantum phenomena.

Our project addresses this challenge head-on by proposing a novel solution: FPGA-based emulation of quantum computing. Field Programmable Gate Arrays (FPGAs) offer the promise of parallel computation at a scale that surpasses traditional software-based simulators, resulting in substantial performance enhancements. This approach not only accelerates quantum algorithm simulations but also provides valuable insights into the precision required for the faithful emulation of quantum circuits.

At the heart of quantum computing are quantum circuits, analogous to conventional digital circuits but with quantum gates represented as unitary matrices, acting on quantum states. The exponential growth of quantum states with the number of qubits presents a significant hurdle in efficiently mimicking quantum operators on classical hardware. Our work proposes a quantum circuit emulator designed to empower quantum algorithm designers with FPGA's parallel computation capabilities, even without in-depth knowledge of FPGA architecture. We leverage high-level design tools, such as Vivado High-Level Synthesis (HLS), to facilitate the development of quantum circuit emulators.

In the broader context of technological advancements, FPGAs have become increasingly accessible to consumers, enabling applications to transition from conventional technologies to FPGA circuits. Quantum computing, rooted in the behavior of quantum particles governed by quantum mechanics, capitalizes on the parallelism inherent in superposition, allowing multiple states to be processed simultaneously.

With growing interest in quantum computing and its potential for outperforming classical computing through parallelism, there is a pressing need for reliable and efficient quantum algorithm simulation tools. While large-scale quantum machines are still in their nascent stages, simulation models suffice for developing quantum algorithms. The challenge lies in accurately modeling quantum processes in software, often necessitating the use of approximations. Our approach seeks to bridge this gap by providing a hardware emulator that approximates quantum effects while closely mirroring the parallel nature of quantum computation.

Quantum circuits serve as a convenient framework for describing quantum algorithms, comprising quantum bits (qubits) and gates. Existing FPGAs are well-suited for emulating these components, efficiently mapping inherently parallel computational tasks compared to software-based simulations. Therefore, our project investigates the design of quantum circuit emulators using classical circuits, culminating in the development of an FPGA-based quantum circuit emulator. By employing quantum circuit primitives, we aim to simplify the construction of new quantum algorithms, making it more intuitive and akin to conventional software library approaches.

In summary, our project explores the realm of quantum computing by leveraging FPGA technology to emulate quantum circuits efficiently. This innovative approach holds the potential to expedite quantum algorithm development, bridge the gap between quantum theory and practical experimentation, and unlock the full power of quantum parallelism.

## Objective/Background <a name="objectivebackground"></a>

**Quantum Circuit Simulation vs. Emulation**

Quantum circuit simulation involves numerically representing quantum information and applying necessary transforms dictated by the simulated quantum algorithm. However, software-based simulators often fail to capture the parallelism and quantum noise present in real quantum computers. Additionally, the exponential expansion of quantum circuit states with increasing qubits can lead to simulations taking hours or even days.

In contrast, quantum circuit emulation also manipulates mathematical representations of quantum information. The primary goal is to replicate quantum algorithm behaviour as if executed on an actual quantum computer, including quantum noise at the gate level. While classical emulation faces resource consumption challenges similar to simulation, it introduces additional complexities like parallel computation and the recreation of extrinsic factors such as quantum noise. Some simulators use programming languages to describe quantum algorithms, while others rely on gate and quantum bit descriptions. However, the description language-based simulators often provide superior performance compared to those relying solely on gate interconnections.

**Motivation for Emulation of Quantum Circuits**

Emulating quantum circuits offers a comprehensive approach to quantum algorithm development compared to simulation. It enables a deeper understanding of complex quantum computing challenges, including quantum noise and gate errors. Hardware-based emulation provides greater control over emulation parameters, such as word length of data primitives, and allows computational optimizations at the gate level that are challenging to achieve in software. This results in enhanced insight into classical modeling issues of quantum circuits and a significant performance boost compared to software simulators.

**Contribution**

This work presents a gate-level FPGA-based solution for quantum circuit simulation. Leveraging the analogies between quantum and classical circuits, an emulation environment has been created that accounts for quantum noise and parallel computation. The emulator outperforms leading software simulators in terms of algorithm runtime. Furthermore, by combining classical error analysis techniques with quantum noise encountered in real quantum computers, we derive a bound on the word length of data primitives. This bound ensures that the emulated circuit produces results similar to those of an actual quantum computer.

## Literature Review/Research Papers <a name="literature-reviewresearch-papers"></a>

1. [FPGA Emulation of Quantum Circuits: Ahmed Usman Khalid](link-to-paper)
2. [Evolving Quantum Circuits and an FPGA-based Quantum Computing Emulator: Negovetic G., Perkowski M., Lukac M., Buller A.](link-to-paper)
3. [FPGA Quantum Computing Emulator Using High-Level Design Tools, Agustin Silva, Omar Gustavo Zabaleta.](link-to-paper)
4. [FPGA-Based Quantum Circuit Emulation: A Case Study on Quantum Fourier Transform](link-to-paper)
5. [New FPGA design solution

