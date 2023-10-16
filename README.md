# QOSF_Cohort_8_Task_2_Quantum-Algorithm-to-Detect-Negative-Numbers

## Introduction
This repository serves as Zain Mughal's application for the QOSF Mentorship Program. Thank you for your consideration, and please don't hesitate to reach out if you have any questions at zain2864@gmail.com

The primary objective of this task is to determine whether a given list of numbers contains any negative integers, utilizing the power of Grover's quantum search algorithm. The algorithm offers significant speedup over classical methods and showcases the benefits of quantum computing in solving specific problems more efficiently.

## Overview 
1. Binary Representation: Each integer in the list is transformed into its two's complement binary representation, facilitating the identification of negative numbers.
2. Quantum Circuit Initialization: The quantum circuit is set up with qubits based on the maximum bit-length of the numbers in the list.
3. Oracle Function: This crucial function marks the quantum states corresponding to negative numbers using a Z-gate.
4. Grover's Diffusion Operator: Amplifies the probability of states that represent negative numbers, bringing us closer to the solution.
5. Iterations: Grover's algorithm requires a specific number of iterations, optimally given by $\frac{\pi}{4} \sqrt{N}$ to achieve the highest probability of success.

## Technical Insights
- Amplitude Amplification: At the heart of Grover's algorithm is the principle of amplitude amplification. It magnifies the amplitude of the desired states while diminishing others.
- Quantum Oracle: The oracle introduces a phase flip to the solution state, marking it for amplification.
- Diffusion Operator: Post the oracle's action, the diffusion operator inverts the amplitude of all states concerning the average amplitude, facilitating the amplification process.
- Handling Multiple Solutions: In situations with multiple negative numbers, Grover's algorithm has an increased probability of finding a solution.

##Benefits
- Speed: Grover's algorithm provides a quadratic speedup over classical algorithms, making this quantum approach significantly faster.
- Efficiency: The two's complement representation ensures a straightforward and efficient identification of negative numbers.

###Future Directions
The implemented quantum algorithm serves as a foundational step. It can be extended and optimized for larger datasets and more complex quantum search problems. The inherent properties of quantum states and the unique features of quantum algorithms like Grover's open up a world of possibilities.
