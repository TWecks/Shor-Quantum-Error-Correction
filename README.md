# Quantum Error Correction

This project is an investigation into quantum error correcting codes, beginning with 
3-qubit bit-flip and phase-flip codes and culminating in a full 
implementation of the 9-qubit Shor code, capable of correcting 
arbitrary single-qubit errors.

## Overview

The goal of this project is to demonstrate how quantum error correcting 
codes can be constructed and simulated using [Qiskit](https://github.com/Qiskit), building from 
simple single-error codes up to the full 9-qubit [Shor code](https://journals.aps.org/pra/abstract/10.1103/PhysRevA.52.R2493). The 
investigation covers bit-flip (X) errors, phase-flip (Z) errors, and 
finally their combination into a single code capable of correcting both.

This was as much an exploration as a presentation — the notebooks are 
organized to reflect that progression, with each building directly on 
the last. 

Instead of reducing the error correcting code to its simplest form, which has been 
well established by other literature and can be read about elsewhere,
I elected instead to keep things in a shape where their structure was clear and
traceable from previous expressions, even if it meant sacrificing some efficiency. 

With that said, I hope you enjoy!

## Notebooks

| Notebook | Description |
|----------|-------------|
| `01_bit_flip_code.ipynb` | 3-qubit repetition code for correcting single bit-flip (X) errors, including syndrome extraction and Toffoli-based correction |
| `02_phase_flip_code.ipynb` | Hadamard-rotated 3-qubit code for correcting single phase-flip (Z) errors, introducing phase kickback and ancilla preparation in the \|+⟩ state |
| `03_full_shor_code.ipynb` | Complete 9-qubit Shor code combining both codes, with parameterized error injection and output distribution plots demonstrating successful correction |

## Background

The Shor code, introduced by Peter Shor in 1995, was the first quantum 
error correcting code capable of protecting against arbitrary single-qubit 
errors. It works by concatenating two 3-qubit codes: an inner bit-flip 
code and an outer phase-flip code, encoding one logical qubit across 9 
physical qubits plus 2 ancilla qubits for syndrome extraction.

## Requirements

```bash
pip install qiskit qiskit-aer matplotlib numpy
```

## Results

Output distributions from the final Shor code circuit, run on the Aer 
simulator with no noise model. Each case injects a different error onto 
a single physical qubit; successful correction returns the output to the 
original encoded state in all cases.


## References

- IBM Quantum. *Foundations of Quantum Error Correction*. 
  IBM Quantum Learning. https://quantum.cloud.ibm.com/learning
- Shor, P.W. (1995). Scheme for reducing decoherence in quantum computer 
  memory. *Physical Review A*, 52(4), R2493.

## License

MIT
