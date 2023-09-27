# FPGA-based Emulation of Quantum Computing

## Table of Contents

1. [Abstract](#abstract)
2. [Introduction](#introduction)
3. [Objective](#objectivebackground)
4. [Research Papers](#literature-reviewresearch-papers)
5. [Design Flow](#methodologydesign-flow)
   - [Simulation vs. Emulation Differentiation](#simulation-vs-emulation-differentiation)
   - [Quantum Circuit Fundamentals](#quantum-circuit-fundamentals)
   - [Hardware Implementation](#hardware-implementation)
   - [Emulating Quantum Circuit Behaviour](#emulating-quantum-circuit-behaviour)
   - [HDL-Based Simulation of Quantum Circuits](#hdl-based-simulation-of-quantum-circuits)
   - [Emulation Overview](#emulation-overview)

## Background

- As quantum computing matures, both the number of quantum developers and open-source tools steeply rise.
- Technological restrictions slow down the expansion of shared learning and development in quantum computing.
- Quantum computers are prohibitively expensive to build and maintain, limiting access to only a few major corporations like Google and IBM.
- Quantum simulators have emerged as an alternative for developers to model quantum computer behavior.
- However, simulators face a significant limitation in terms of computation speed compared to actual quantum computers.
- Quantum computers leverage parallelism due to the superposition of qubits, while simulators on classical computers lack this parallelism.
- Simulating larger quantum computers with more qubits on classical computers results in exponential slowdown.

## Project Overview

- The project aims to prototype hardware acceleration of quantum computing simulations using FPGA.
- Traditional software-based quantum simulation on a CPU experiences exponential slowdown with larger quantum circuits.
- Offloading heavy computational tasks to specialized hardware like FPGA reduces latency and speeds up simulations.
- Hardware acceleration becomes especially advantageous as quantum circuits grow in size (higher-qubit computations).
  
This approach leverages the parallelism and matrix manipulation capabilities of FPGAs to enhance the efficiency of quantum circuit simulation.


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

## Objective <a name="objective"></a>

**Motivation for Emulation of Quantum Circuits**

Emulating quantum circuits offers a comprehensive approach to quantum algorithm development compared to simulation. It enables a deeper understanding of complex quantum computing challenges, including quantum noise and gate errors. Hardware-based emulation provides greater control over emulation parameters, such as word length of data primitives, and allows computational optimizations at the gate level that are challenging to achieve in software. This results in enhanced insight into classical modeling issues of quantum circuits and a significant performance boost compared to software simulators.

**Contribution**

This work presents a gate-level FPGA-based solution for quantum circuit simulation. Leveraging the analogies between quantum and classical circuits, an emulation environment has been created that accounts for quantum noise and parallel computation. The emulator outperforms leading software simulators in terms of algorithm runtime. Furthermore, by combining classical error analysis techniques with quantum noise encountered in real quantum computers, we derive a bound on the word length of data primitives. This bound ensures that the emulated circuit produces results similar to those of an actual quantum computer.


**Quantum Circuit Simulation vs. Emulation**

Quantum circuit simulation involves numerically representing quantum information and applying necessary transforms dictated by the simulated quantum algorithm. However, software-based simulators often fail to capture the parallelism and quantum noise present in real quantum computers. Additionally, the exponential expansion of quantum circuit states with increasing qubits can lead to simulations taking hours or even days.

In contrast, quantum circuit emulation also manipulates mathematical representations of quantum information. The primary goal is to replicate quantum algorithm behaviour as if executed on an actual quantum computer, including quantum noise at the gate level. While classical emulation faces resource consumption challenges similar to simulation, it introduces additional complexities like parallel computation and the recreation of extrinsic factors such as quantum noise. Some simulators use programming languages to describe quantum algorithms, while others rely on gate and quantum bit descriptions. However, the description language-based simulators often provide superior performance compared to those relying solely on gate interconnections.


## Research Papers <a name="literature-reviewresearch-papers"></a>

1. [FPGA Emulation of Quantum Circuits: Ahmed Usman Khalid](link-to-paper)
2. [Evolving Quantum Circuits and an FPGA-based Quantum Computing Emulator: Negovetic G., Perkowski M., Lukac M., Buller A.](link-to-paper)
3. [FPGA Quantum Computing Emulator Using High-Level Design Tools, Agustin Silva, Omar Gustavo Zabaleta.](link-to-paper)
4. [FPGA-Based Quantum Circuit Emulation: A Case Study on Quantum Fourier Transform](link-to-paper)
5. [New FPGA design solution using quantum computation concepts, 2021 IEEE 27th International Symposium for Design and Technology in Electronic Packaging.](link-to-paper)

## Design Flow <a name="methodologydesign-flow"></a>

### Simulation vs. Emulation Differentiation

Acknowledging the distinction between quantum circuit simulation and emulation is paramount. While simulation entails numerical representation and transformations, it often lacks the parallelism and quantum noise found in actual quantum computers. In contrast, emulation aims to replicate quantum algorithm behaviour on real quantum hardware, including gate-level quantum noise.

### Quantum Circuit Fundamentals

Quantum circuits are composed of quantum logic gates. Despite an infinite number of possible gates in theory, a subset suffices for implementing arbitrary-sized quantum circuits. Quantum bits (qubits) enable parallelism, with superpositions leading to probabilistic circuits. To account for finite precision, errors accumulate, affecting both software and hardware-based quantum circuit simulations. Quantum gate operations are expressed as matrix operations.

### Hardware Implementation

Implementing quantum gate operations on FPGA hardware is a critical step. This often involves low-level languages and leverages FPGA's reconfigurability and parallel processing capabilities. Our project explores the feasibility of implementing a Quantum Emulator on FPGA, utilizing high-level design tools like Xilinx Vivado IDE.

### Emulating Quantum Circuit Behaviour

Emulating quantum circuits demands translating quantum physics principles into classical technologies effectively. The primary objectives encompass resource-efficient simulation, parallelism emulation using FPGA technology, user-friendly modelling tools, and circuit correctness verification. Quantum circuits are constructed from predefined quantum gate components, and their correctness can be verified through software simulation or FPGA emulation. This methodology streamlines the process by modeling quantum circuits using VHDL and synthesizing them in hardware for practical performance.

### HDL-Based Simulation of Quantum Circuits

In our project, we explore HDL-based simulation of quantum circuits, which involves employing a hardware description language like VHDL. This approach leverages analogies between the quantum circuit model and classical circuits to construct and simulate quantum circuits.

**Key Characteristics:**

- **Direct Incorporation:** HDL simulation of quantum circuits aligns qubits and quantum gates with classical gates and bits, respectively. Qubits are described using two complex numbers in VHDL, employing the "real" keyword. Gates are constructed with qubits as inputs and outputs, and the gate transformations are described using behavioral VHDL. The quantum circuit is then constructed by combining these gates using structural VHDL.

- **Challenges with Entanglement:** An essential challenge in HDL simulation is dealing with entanglement explicitly. Unlike previous simulators that expanded the quantum circuit to full basis states and applied tensor products, HDL aims for simplicity in gate descriptions. Therefore, explicit detection and simulation of entanglement are required. Detailed entanglement extraction algorithms have been derived to detect when entanglement occurs or disappears. These algorithms are simulated using functional VHDL and exhibit exponential complexity, resulting in resource usage similar to expanded state space simulators.

- **CAD Simulation Tools:** Utilizing VHDL for simulating quantum circuits allows us to harness CAD simulation tools typically used in classical circuit development. This involves either employing structural VHDL or using graphical netlist creation tools, streamlining the processes of circuit creation and result simulation.

**Performance Considerations:**

According to prior findings, the runtime for non-entangled cases of simulation follows an O(n^2) complexity. While some simulation runtimes for small quantum circuits have been reported, it's essential to note that entanglement extraction remains a complex process. Overall, the simulation speed is inherently constrained by the capabilities of the VHDL simulation tool.

Incorporating HDL-based simulation into our project enables us to explore a robust approach to simulating quantum circuits while addressing the unique challenges posed by quantum entanglement. By leveraging VHDL, we tap into the familiarity of CAD simulation tools, thus enhancing our project's capabilities in quantum circuit emulation.

### Emulation Overview

**Emulator Overview**

The design process of our emulator is illustrated in Figure 3.1, and it encompasses the construction of quantum circuits using quantum gate descriptions embedded within the emulator. The correctness of these circuits can be verified through either software simulation or FPGA emulation. This technique involves modeling quantum circuits using VHDL and then synthesizing them in hardware, which is essential to achieve the performance required to make the entire process practical.

**Key Components of the Emulator:**

1. **C++ Command-Line Interface:** This interface serves as a fast and efficient tool for generating VHDL descriptions of the gates needed in quantum circuits. It simplifies the process of calling C++ functions responsible for generating gate descriptions. These descriptions cover a range of gates, including the X-gate, Z-gate, Hadamard Gate, Rotation gates, as well as common multiple input gates like the controlled versions of single input gates and the swap gate. To generate the appropriate VHDL description of a gate, the user simply provides the gate name, system size, and the number of inputs. The generated gates utilize the expanded state space notation for both inputs and outputs, ensuring comprehensive gate functionality.

![image](https://github.com/ManishPatla/QuantumComputation_FPGAs/assets/109287423/52cceb39-07ab-4cf6-9cb2-dded5a760c17)


*Figure 3.1: Emulation Overview*

This comprehensive approach to emulation allows for the efficient and precise replication of quantum circuit behavior on FPGA hardware, facilitating the development and testing of quantum algorithms in a real-world, parallel computing environment.


