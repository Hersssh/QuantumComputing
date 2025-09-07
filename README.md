**QLang Syntax for Beginners**

QLang is a **toy quantum programming language** designed for learning.\
It lets you write programs that simulate **qubits, gates, entanglement,
and measurements** --- all in simple text.

**🟢 1. Declaring Qubits**

Before using a qubit, declare it:

qubit q0

qubit q1

-   You can name qubits however you like: q0, a, ancilla, data1.

-   Each qubit starts in state **\|0⟩**.

**🟢 2. Applying Gates**

Think of gates as "actions" on qubits.

**🎲 Single-qubit gates**

hadamard q0 \# puts q0 into superposition

h q0 \# shorthand for hadamard

x q0 \# NOT gate (flips 0 ↔ 1)

y q0 \# Pauli-Y

z q0 \# phase flip

s q0 \# quarter-turn phase

t q0 \# eighth-turn phase

**🤝 Multi-qubit gates**

cnot q0,q1 \# control = q0, target = q1

cz q0,q1 \# controlled-Z

swap q0,q1 \# swap states of q0 and q1

**🟢 3. Measuring Qubits**

Turn quantum states into classical bits.

measure q0 \# measure one qubit

measure all \# measure everything

-   After measuring, the qubit collapses to 0 or 1.

-   In **probability mode**, you'll see the distribution instead of a
    single random value.

**🟢 4. Execution Modes**

Control how results are shown:

mode single \# gives one random outcome

mode probability \# shows probability histogram

shots 1000 \# run experiment 1000 times

**🟢 5. Conditionals**

Run gates depending on previous measurement results:

if q0 == 1 then x q1

-   Works only if q0 was **measured earlier**.

**🟢 6. Oracles & Grover's Algorithm**

Special tools for search problems.

oracle_mark 0110 \# mark a specific state

grover_diffusion \# spread amplitudes toward marked state

**🟢 7. Comments**

Add notes for yourself (ignored by QLang):

\# This creates a Bell state

**🌟 Example Programs**

**A) Superposition**

qubit q0

hadamard q0

measure all

**B) Bell State (entanglement)**

qubit q0

qubit q1

hadamard q0

cnot q0,q1

measure all

**C) Conditional Execution**

qubit a

qubit b

hadamard a

measure a

if a == 1 then x b

measure all

**D) Simple Grover Search**

qubit q0

qubit q1

hadamard q0

hadamard q1

oracle_mark 11

grover_diffusion

measure all

**🧾 Quick Reference**

  --------------------------------------------------------------------------
  **Category**   **Syntax Example**      **Meaning**
  -------------- ----------------------- -----------------------------------
  Declare        qubit q0                Create a new qubit in

  Single Gate    hadamard q0             Put qubit in superposition

  Multi Gate     cnot q0,q1              Control q0, target q1

  Measure        measure all             Collapse and output values

  Mode           mode probability        Show probabilities instead of
                                         random

  Shots          shots 1000              Repeat 1000 runs

  Conditional    if q0 == 1 then x q1    Apply only if q0 measured = 1

  Oracle         oracle_mark 010         Mark state for Grover

  Diffusion      grover_diffusion        Spread amplitude

  Comment        \# hello world          Ignored line
  --------------------------------------------------------------------------
