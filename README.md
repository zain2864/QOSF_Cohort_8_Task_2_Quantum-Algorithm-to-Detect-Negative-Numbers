# QOSF_Cohort_8_Task_2_Quantum-Algorithm-to-Detect-Negative-Numbers

## Introduction
This repository serves as Zain Mughal's application for the QOSF Mentorship Program. Thank you for your consideration, and please don't hesitate to reach out if you have any questions at zain2864@gmail.com

The primary objective of this task is to determine whether a given list of numbers contains any negative integers, utilizing the power of Grover's quantum search algorithm. The algorithm offers significant speedup over classical methods and showcases the benefits of quantum computing in solving specific problems more efficiently.

## Overview 
1. Binary Representation: Each integer in the list undergoes a transformation to its two's complement binary representation, ensuring that negative numbers are identifiable with a leading '1' bit.
2. Quantum Circuit Initialization: A quantum circuit is initialized based on the maximum bit-length from our list of numbers. All qubits are set to a superposition state at the start.
3. Oracle Function: The oracle plays a pivotal role in Grover's algorithm. It recognizes and introduces a phase flip to the desired solution state. For this task, the oracle was designed to mark states corresponding to negative numbers. With the two's complement representation, marking states with a leading '1' bit becomes straightforward using a Multi-controlled-Phase gate, to create an MCZ gate, on the auxiliary qubit.
4. Amplitude Amplification: Central to Grover's algorithm is amplitude amplification. This process magnifies the amplitude of desired states while reducing the amplitude of undesired states.
5. Grover's Diffusion Operator: Post the oracle's action, Grover's diffusion operator is applied. This operator amplifies the amplitude of marked states by inverting the amplitude of all states concerning the average amplitude.
6. Iterations: The oracle and diffusion steps get repeated approximately $\frac{\pi}{4} \sqrt{N}$ times, where N represents the number of items in the list. This iteration count is optimal for Grover's algorithm, maximizing the likelihood of measuring a marked state.

## Efficiency and Justification
Employing Grover's algorithm offers a significant speedup over classical counterparts. Typically, each number would have to be checked individually in a classical approach, leading to linear runtime in worst-case scenarios. With Grover's algorithm, a quadratic speedup is achieved, approximating a $\sqrt{N}$ runtime.

It's worth noting that Grover's algorithm, despite its speedup, provides a probabilistic solution. This means the correct answer is highly probable but not guaranteed in every run. Unlike deterministic classical algorithms, however, the success probability can be amplified by repeating the quantum procedure multiple times.

The two's complement representation for numbers efficiently encodes the sign of the number in the most significant bit. This encoding allows our oracle to be simplistic and efficient, marking negative numbers by inspecting the leading bit.

## Validity for All Kinds of Numbers
The proposed quantum approach caters to all integers, be they positive or negative. Here's the rationale:
1. Universal Two's Complement Representation: Every integer, positive or negative, can be depicted in two's complement binary form. This encoding ensures that negative numbers always start with a '1' bit, distinguishing them from positive numbers and zero. This simple yet powerful characteristic ensures that our quantum solution is valid for all negative numbers. The use of the two's complement representation is universal in digital systems for signed number representation, further validating our approach for any list of integers.
2. Scalability: The quantum circuit's size adapts based on the maximum bit-length of the numbers in the list. As numbers increase in magnitude, they can be processed by merely augmenting the number of qubits in the circuit.
3. Robust Oracle: The oracle's design promises to consistently mark states corresponding to negative numbers, irrespective of the number's magnitude or exact value.


## References: 
- Quantum Complexity Theory (QCT), Bernstein, Ethan, and Umesh Vazirani: This paper provided an in-depth analysis of the efficiency and complexity of quantum algorithms. Leveraging its insights, this task implemented the Grover's algorithm ensuring that the quantum circuit design adhered to the principles ensuring optimal efficiency. The paper's discussion on quantum oracle was particularly useful in designing the oracle for the problem.
- Rapid Solutions in Quantum Computing (RSQC), Deutsch, David, and Richard Jozsa: RSQC discussed the speed advantages quantum algorithms could offer over classical counterparts. Inspired by its discussions, this task aimed to demonstrate how Grover's algorithm can provide rapid solutions, especially when searching unsorted databases, which is akin to the problem of searching for a negative number in an unsorted list.
- Database Search in Quantum Computing (DSQC), Grover, Lov K: DSQC provided a comprehensive understanding of how Grover's algorithm can be applied to search problems. The paper's detailed analysis of Grover's iterative structure and the diffusion operator was pivotal in creating the quantum circuits for the problem. The paper's illustrations and circuit designs greatly influenced the circuit implementation.
- Qiskit Documentation: The official documentation provided guidance on the implementation details of the quantum circuits and algorithms using the Qiskit library.
