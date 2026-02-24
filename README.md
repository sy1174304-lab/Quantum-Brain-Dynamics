# Quantum-Brain-Dynamics
The core engine integrates many-body physics with synaptic feedback mechanisms to observe how quantum states transition over time under specific energetic constraints.

Quantum Brain Dynamics: LMG Hamiltonian & Qubit Activity Simulation
​ Project Overview

​This repository contains a sophisticated computational model designed to simulate Quantum Brain Dynamics using the Lipkin-Meshkov-Glick (LMG) Hamiltonian framework. The project explores the intersection of quantum mechanics and neural firing patterns, utilizing high-dimensional Hilbert spaces to represent quantum neurons (qubits) and their temporal evolution.
​The core engine integrates many-body physics with synaptic feedback mechanisms to observe how quantum states transition over time under specific energetic constraints.
​ Technical Architecture

​1. Quantum Hamiltonian Construction
​The model implements the LMG Hamiltonian, a cornerstone in many-body quantum physics, to define the energy landscape of the neural network:
​Hilbert Space Representation: The system operates in a 2^N dimensional space, where N represents the number of quantum neurons.

​Energy Splitting (\sigma_z): A bitwise logic gate mechanism (j >> i) is used to assign energy levels to each qubit based on its state, multiplied by the \epsilon (epsilon) parameter.
​Quantum Tunneling/Interaction (\sigma_x): The model simulates interactions and state-flipping (tunneling) between neurons using bitwise XOR operations (j \oplus (1 << i)) to represent the \sigma_x operator.
​Synaptic Coupling: The interaction terms are further refined through \gamma (gamma) coefficients to define the strength of the neural connectivity.

​2. Temporal Evolution & Unitary Dynamics
​To observe the brain model in motion, the system employs Unitary Time Evolution:
​Time-Evolution Operator: The code calculates the operator U(t) = \exp(-iHt) using the scipy.linalg.expm function to ensure high-precision matrix exponentiation.
​State Propagation: Initialized quantum states (e.g., a single active neuron) are propagated through time using the dot product of the evolution operator and the state vector.
​Synaptic Feedback Loop: A specialized function incorporates a time-constant \tau_r (tau_r) to simulate exponential decay and feedback in synaptic responses: f(t) = \tau_r \cdot e^{-t/\tau_r}.

​3. Neural Activity Simulation
​Beyond the raw quantum state, the model simulates macroscopic neural activity:
​Qubit Firing Patterns: The activity of each qubit is modeled as a periodic function (Sine wave) integrated with Gaussian white noise (\text{random.randn}) to simulate realistic biological environments.
​Multi-Channel Tracking: The system can track N=10 or more channels simultaneously, providing a comprehensive view of network 

Implementation & Requirements


​Dependencies
​The project relies on the following scientific computing libraries:
​NumPy: For high-performance multidimensional array processing and bitwise operations.
​SciPy: Specifically the linalg module for complex matrix exponentiation.
​Matplotlib: For rendering temporal activity graphs and state probability distributions.
​Usage Protocol

​Model Initialization: Instantiate the QuantumBrainModel with desired quantum parameters.
​Hamiltonian Generation: Generate the 2^N \times 2^N energy matrix.
​Execution: Run the time-evolution loop to generate state vectors across the time series t.
​Visualization: Plot the absolute square of the state coefficients to visualize neuron activation probability.

​Note: This research is part of an independent scientific study focused on the potential for quantum computing architectures in biological neural simulation.
