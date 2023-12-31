# FPGA-based Emulation of Quantum Circuits  
### QUANTUM COMPUTING

![image](https://github.com/ManishPatla/QuantumComputation_FPGAs/assets/109287423/810cdb68-3fee-41a4-8321-66625d9649d5)


## Table of Contents

1. [Abstract](#abstract)
2. [Introduction](#introduction)
3. [Objective](#objective)
4. [Literature Review/Research Papers](#literature-reviewresearch-papers)
5. [Methodology/Design Flow](#methodology/design-flow)
   - [Simulation vs Emulation Differentiation](#simulation-vs-emulation-differentiation)
   - [Quantum Circuit Fundamentals](#quantum-circuit-fundamentals)
   - [Hardware Implementation](#hardware-implementation)
   - [Emulating Quantum Circuit Behaviour](#emulating-quantum-circuit-behaviour)
   - [HDL-Based Simulation of Quantum Circuits](#hdl-based-simulation-of-quantum-circuits)
   - [Emulation Overview](#emulation-overview)
6. [FPGA Architecture  Design Flow](#fpga-architecture-design-flow)
7. [Implementation Procedure](#implementationprocedure)
9. [Results](#results)
10. [Conclusion](#objective)
11. [Overall Summary](#Summary)

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


## Literature Survey/Research Papers <a name="literature-reviewresearch-papers"></a>

1. [FPGA Emulation of Quantum Circuits: Ahmed Usman Khalid](link-to-paper)
2. [Evolving Quantum Circuits and an FPGA-based Quantum Computing Emulator: Negovetic G., Perkowski M., Lukac M., Buller A.](link-to-paper)
3. [FPGA Quantum Computing Emulator Using High-Level Design Tools, Agustin Silva, Omar Gustavo Zabaleta.](link-to-paper)
4. [FPGA-Based Quantum Circuit Emulation: A Case Study on Quantum Fourier Transform](link-to-paper)
5. [New FPGA design solution using quantum computation concepts, 2021 IEEE 27th International Symposium for Design and Technology in Electronic Packaging.](link-to-paper)

## Methodology/Design Flow

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

- **Direct Incorporation:** HDL simulation of quantum circuits aligns qubits and quantum gates with classical gates and bits, respectively. Qubits are described using two complex numbers in HDL, employing the "real" keyword. Gates are constructed with qubits as inputs and outputs, and the gate transformations are described using behavioral VHDL. The quantum circuit is then constructed by combining these gates using structural VHDL.

- **Challenges with Entanglement:** An essential challenge in HDL simulation is dealing with entanglement explicitly. Unlike previous simulators that expanded the quantum circuit to full basis states and applied tensor products, HDL aims for simplicity in gate descriptions. Therefore, explicit detection and simulation of entanglement are required. Detailed entanglement extraction algorithms have been derived to detect when entanglement occurs or disappears. These algorithms are simulated using functional VHDL and exhibit exponential complexity, resulting in resource usage similar to expanded state space simulators.

- **CAD Simulation Tools:** Utilizing HDL for simulating quantum circuits allows us to harness CAD simulation tools typically used in classical circuit development. This involves either employing structural VHDL or using graphical netlist creation tools, streamlining the processes of circuit creation and result simulation.

**Performance Considerations:**

According to prior findings, the runtime for non-entangled cases of simulation follows an O(n^2) complexity. While some simulation runtimes for small quantum circuits have been reported, it's essential to note that entanglement extraction remains a complex process. Overall, the simulation speed is inherently constrained by the capabilities of the VHDL simulation tool.

Incorporating HDL-based simulation into our project enables us to explore a robust approach to simulating quantum circuits while addressing the unique challenges posed by quantum entanglement. By leveraging VHDL, we tap into the familiarity of CAD simulation tools, thus enhancing our project's capabilities in quantum circuit emulation.

### Emulation Overview

**Emulator Overview**

The design process of our emulator is illustrated in Figure , and it encompasses the construction of quantum circuits using quantum gate descriptions embedded within the emulator. The correctness of these circuits can be verified through either software simulation or FPGA emulation. This technique involves modeling quantum circuits using HDL and then synthesizing them in hardware, which is essential to achieve the performance required to make the entire process practical.


![image](https://github.com/ManishPatla/QuantumComputation_FPGAs/assets/109287423/52cceb39-07ab-4cf6-9cb2-dded5a760c17)


*Figure 3.1: Emulation Overview*

This comprehensive approach to emulation allows for the efficient and precise replication of quantum circuit behavior on FPGA hardware, facilitating the development and testing of quantum algorithms in a real-world, parallel computing environment.

### FPGA Architecture  Design Flow

#### Components of an FPGA

FPGAs are composed of three primary types of modules:

#### 1. Configurable Logic Block (CLB)

The Configurable Logic Block (CLB) serves as the foundational building block within an FPGA. Each CLB comprises multiple slices, which in turn consist of various elements:

- **Function Generators (LUTs):** Look-Up Tables are used to implement logic functions.
- **Registers:** Storage elements for holding data.
- **Multiplexers:** Used for data routing and selection.
- **Carry Logic:** Essential for arithmetic and logic operations.

#### 2. Switch Matrix or Interconnection Wires

Interconnection within an FPGA is facilitated by the Switch Matrix. This component handles the routing of signals between CLBs and from CLBs to Input/Output Blocks (IOBs).

#### 3. IO Blocks (IOB)

IO Blocks serve as the basic input/output function blocks of the FPGA. These blocks enable communication between the FPGA and external devices or systems.

#### Understanding the Interaction

The interaction among these components is crucial for the proper functioning of an FPGA. The CLBs provide the logic and computational capabilities, the Switch Matrix facilitates communication and connectivity, and the IOBs handle input and output operations.

This architecture provides a highly customizable platform for implementing digital circuits based on specific requirements, allowing for flexible configurations and adaptations.



![image](https://github.com/ManishPatla/QuantumComputation_FPGAs/assets/109287423/eaeeb16b-19b9-44c8-8361-07631a972854)


#### Typical FPGA Design Flow

<img width="542" alt="image" src="https://github.com/ManishPatla/QuantumComputation_FPGAs/assets/109287423/86cfbced-a6c8-415b-978b-6d4df10a3141">


### FPGA Selection and Design Process

This Step provides an overview of the process involved in selecting an FPGA and the subsequent design stages. It highlights key considerations from choosing an FPGA to its programming.

#### 1. FPGA Selection

FPGA selection is the initial step in the design phase. Vendors offer FPGAs tailored to specific end-user applications, such as automotive, defense, and space applications. Recent technologies, like 5G Wireless, Embedded Vision, and Industrial IoT, leverage FPGA capabilities, particularly with the inclusion of ARM processors and C-based compilers for FPGA platforms.

#### Device Categories
- **Xilinx Automotive (XA)**
  - XA Zynq UltraScale+
  - XA Zynq®-7000
  - XA Artix®-7
  - Kintex®

#### 2. Choosing an FPGA

When choosing an FPGA, several limitations need consideration:

- Number of Available I/Os (Differential and Single Ended)
- Internal Memories (RAMs)
- DSP Slices (Complex Multipliers)
- Connectivity Ports (Serial Interfaces, Memory Interfaces)

Designers should aim to utilize 60% to 75% of logic resources like slices and LUTs to avoid issues related to routing congestion and timing closure. Considering pin-compatible devices with higher resources allows room for additional logic in evolving designs.

#### 3. Estimation

Estimating resource utilization aids in FPGA selection and system Bill of Materials (BoM).

#### 3.1 Area Estimation
- Predicts FPGA occupancy; choosing an FPGA with insufficient gate count poses risks to the project.
- Microarchitecture analysis helps estimate the area of individual modules and built-in FPGA resources (e.g., memory, DSP slices, IOs).

#### 3.2 Power Estimation
- Power estimation tools like Xilinx Power Estimator (XPE) and Vivado Power Analysis help in budgeting power for design and thermal management.

#### 4. Design Entry

Design entry formats include RTL design (VHDL, Verilog, etc.), schematic entry, third-party IP cores, and simulation libraries.

#### 5. Design Synthesis

Design synthesis generates Gate Level Netlist for implementation.

#### 6. Design Implementation

#### Stages:
1. **Translate:** Merges netlists, performs checks, and adds user constraints.
2. **Mapping:** Allocates resources and processes constraints.
3. **Placement and Routing:** Finalizes the physical design database and provides reports on delays.

#### 7. Device Programming

This phase involves creating a configuration file and programming the FPGA either directly from a host computer using a download cable or through flash/PROM.

<img width="608" alt="image" src="https://github.com/ManishPatla/QuantumComputation_FPGAs/assets/109287423/708134b2-4e5a-4c7f-8eb7-f17507923a3a">


#### FPGA Design Conclusion:
Running a design through a simple FPGA flow sometimes won’t be sufficient for complex designs. Therefore, for stringent design requirements like dense area or aggressive timing requirements or for other challenges like a large FPGA, we need to go through an advanced FPGA flow.


### Implementation Procedure

###### Preliminary :
Get Familiar with Quantum Computing and its concepts like Superposition,Entanglement & Quantum Algorithms like Grover,Shors,Teleportation and No Cloning Theroem etc.
Gain Hands on Expereince with the Qiskit Tool,Build Quantum gates and Circuits by coding them in Qiskit.
Simulate and Develop a  Quantum Netlist in Qiskit to verify its Functionality.

### QISKIT 
Qiskit is the library of python that is developed by IBM and is meant to code and create Quantum circuits and run these circuits on local simulators, IBM quantum simulators, or real IBM Quantum Computers. 


#### Quantum Full Adder in an FPGA Hardware Chip

The idea is to Program this style of Architecture in FPGA and Develop a Quantum Hardware in FPGA.

In General 
Classical Computation known for Determenstic output. 
Quantum Computation gives us an Undetermenstic Output. 

At this level, Quantum Hardware has several challenges like 
*Signifucant Errors 
*Creating Cost in millions 

Hence we need an emulator or classical computer to accelerate Quantum software.

2 Ways of Emulation :

- Software : Classical Simulation
- Hardware : FPGA emulation


# Quantum Full Adder


A Quantum Full Adder is a specialized quantum circuit designed for addition in the context of quantum computing. Unlike classical full adders that operate on classical bits, quantum full adders take advantage of the principles of quantum mechanics to perform addition in a quantum computing environment.

## Key Features:

### 1. Superposition:
   Quantum full adders can process multiple inputs simultaneously, thanks to the principle of superposition. Qubits, the quantum counterparts of classical bits, can 
   exist in multiple states at the same time.

### 2. Entanglement:
   Quantum bits (qubits) can be entangled, establishing correlations between them. This entanglement property enables quantum full adders to explore parallel 
   computational paths.

### 3. Probabilistic Nature:
   Quantum computing is inherently probabilistic. Quantum full adders provide results that are probabilistic in nature, and multiple computations may be performed 
   simultaneously with varying probabilities.

### 4. Quantum Gates:
   Quantum circuits, including full adders, use quantum gates such as controlled NOT (CNOT) gates. These gates enable the manipulation and interaction of qubits, 
   contributing to the unique behavior of quantum circuits.

## Quantum Full Adder Design:

The design of a quantum full adder involves leveraging quantum gates and principles to perform addition. Quantum carry gates and CNOT gates are commonly used in the construction of quantum full adders, allowing for the parallel processing of quantum states.

**Note:** The behavior and design of quantum circuits, including full adders, differ significantly from classical circuits due to the principles of quantum computing. Results obtained from quantum computations may be probabilistic, and the quantum full adder operates in a fundamentally different manner compared to its classical counterpart.

### QISKIT IMPLEMENTATION OF QUANTUM CIRCUIT

It has all the required gates that are required to create a full adder circuit. Following Quantum Gates are used to construct a Full Adder Circuit.
- X Gate      : X gate is a single-qubit gate. It is generally known as a bit flip gate which flips the current state of a qubit.
- CNOT Gate   : CNOT is a multi-qubit gate in which 1 qubit has control while the other one is the target qubit when the control qubit is 1 then it flips the state 
                of he target qubit otherwise it remains unchanged.
- Toffoli Gate: Toffoli gate is a multi-qubit gate that involves 3 qubits. The first two qubits are control and the third qubit is the target qubit. It behaves like 
                a classical AND operation Quantum Full Adder Circuit

<img width="499" alt="image" src="https://github.com/ManishPatla/QuantumComputation_FPGAs/assets/109287423/38d90df9-5236-4dd4-85e4-e0c047aba8df">






























### Step1 : Build an Quantum Circuit using Qiskit 

*Implementing QUANTUM CIRCUIT based on QUANTUM TELEPORTATION ALGORITHM , by coding it in Qiskit and generate equivalent Quantum Netlist* 

### Algorithm Implemented :

Explanation of Algorithm!!! 

Qiskit Implementation of the Circuit:














Circuit:








Functionality Verification:





Adv and Disadvantage of this :




Specifying [Proof] the reason why we are emulating it using FPGA Hardware 






### Step2 : Either HDL /MATRIX Representation







### Step3 : Simulation using XILINX VIVADO DESIGN SUITE 






### Synthesis :






### Dumping   : 








