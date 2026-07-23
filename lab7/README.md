# Lab 7: VHDL Modeling of Sequential Circuits – Flip-Flops

## 📖 Overview

This laboratory experiment demonstrates the design and simulation of **SR, D, JK, and T Flip-Flops** using **Behavioral VHDL**. Flip-flops are fundamental sequential logic circuits that store one bit of binary information and operate based on the clock signal. The circuits were simulated successfully, and their outputs were verified using **GTKWave**.

---

## 🎯 Objective

- To implement **SR, D, JK, and T Flip-Flops** using VHDL.
- To verify the behavior of sequential circuits using a clock signal.
- To simulate and analyze the operation of each flip-flop in GTKWave.

---

## 📚 Theory

A **flip-flop** is a sequential storage element capable of storing one bit of binary data. Unlike combinational logic circuits, the output of a flip-flop depends on both the current inputs and its previously stored state. In this experiment, all flip-flops are **positive-edge triggered**, meaning they change state only on the **rising edge of the clock**.

### 🔹 SR Flip-Flop

The **SR (Set-Reset) Flip-Flop** has two control inputs: **S (Set)** and **R (Reset)**. It can set, reset, or retain its previous state. When both inputs are HIGH simultaneously, the output becomes undefined.

| S | R | Next Q |
|:-:|:-:|:------:|
| 0 | 0 | Hold |
| 0 | 1 | Reset (0) |
| 1 | 0 | Set (1) |
| 1 | 1 | Invalid |

---

### 🔹 D Flip-Flop

The **D (Data) Flip-Flop** stores the value present at the **D input** whenever the clock changes from LOW to HIGH. It eliminates the invalid condition found in the SR Flip-Flop.

**Equation**

```text
Q(next) = D
```

---

### 🔹 JK Flip-Flop

The **JK Flip-Flop** is an improved version of the SR Flip-Flop. Instead of producing an invalid state when both inputs are HIGH, it toggles its output.

**Equation**

```text
Q(next) = JQ' + K'Q
```

| J | K | Next Q |
|:-:|:-:|:------:|
| 0 | 0 | Hold |
| 0 | 1 | Reset |
| 1 | 0 | Set |
| 1 | 1 | Toggle |

---

### 🔹 T Flip-Flop

The **T (Toggle) Flip-Flop** changes its output state on every positive clock edge whenever **T = 1**. If **T = 0**, the output remains unchanged.

**Equation**

```text
Q(next) = T ⊕ Q
```

| T | Next Q |
|:-:|:------:|
| 0 | Hold |
| 1 | Toggle |

---

## ▶️ Simulation Output

The VHDL designs were simulated successfully, and the generated waveform was examined using **GTKWave**. All input and output signals, together with the clock signal, were observed to verify the behavior of each flip-flop.

---

## 🔍 Observation

The simulation waveform verified the expected operation of all four flip-flops.

- The **SR Flip-Flop** correctly performed the **set**, **reset**, and **hold** operations for valid input combinations.
- The **D Flip-Flop** stored the input value at every positive clock edge.
- The **JK Flip-Flop** toggled its output correctly when both **J** and **K** were HIGH.
- The **T Flip-Flop** alternated its output whenever **T** was HIGH.
- In all cases, **QB** remained the complement of **Q**, confirming the correct operation of the circuits.

---

## ✅ Conclusion

This experiment successfully demonstrated the implementation and simulation of **SR, D, JK, and T Flip-Flops** using **Behavioral VHDL**. Each flip-flop responded correctly to the rising edge of the clock, and the generated waveforms matched the expected truth tables. A common testbench was used to verify all four designs, making it easy to compare their behavior. The experiment provided practical understanding of sequential logic circuits, which are widely used in digital systems such as **registers, counters, shift registers, and finite state machines**.

---

## 📷 Output

### GTKWave Waveform

![Simulation Waveform](Flipflops.png)

**Figure 7.1:** Simulation waveform of SR, D, JK, and T Flip-Flops observed in GTKWave.