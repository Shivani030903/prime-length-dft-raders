# Prime-Length DFT Optimization using Rader’s Algorithm

A computational and visualization study of prime-length Discrete Fourier Transform (DFT) using Rader’s Algorithm and Bluestein’s Transform to eliminate zero-padding artifacts and improve spectral accuracy.

---

## Project Overview

Traditional FFT algorithms (Cooley–Tukey) require signal lengths to be powers of two.  
For prime-length signals, zero-padding is commonly used — but this introduces:

- Spectral leakage
- Phase distortion
- False frequency peaks

This project implements and compares:

1. **Brute-Force DFT (O(N²))**
2. **Zero-Padded FFT (O(N log N))**
3. **Prime-Length DFT using Rader’s Algorithm (O(N log N))**

The optimized method converts the prime-length DFT into a circular convolution using primitive roots of unity and computes it efficiently via FFT.

---

## Core Concepts Implemented

- Complex Roots of Unity
- Euler’s Formula
- Primitive Roots (Number Theory)
- Circular Convolution
- Bluestein’s Chirp Z-Transform
- Spectral Leakage Analysis
- Phase & Magnitude Spectrum Visualization

---

## Architecture

Python (Algorithm Engine)
    ↳ Rader’s Algorithm
    ↳ Primitive Root Generator
    ↳ FFT-based Convolution

JavaScript (Visualization Layer)
    ↳ Signal Simulation
    ↳ Runtime Benchmarking
    ↳ HTML5 Canvas Spectrum Rendering

---

## Tech Stack

- Python 3.10+
- NumPy
- JavaScript (ES6)
- HTML5 Canvas
- Tailwind CSS

---

## Performance Results

| Method | Complexity | Runtime (N = 9973) |
|--------|------------|-------------------|
| Brute-Force | O(N²) | ~1846 ms |
| Zero Padding | O(M log M) | ~3.6 ms |
| Rader’s Algorithm | O(N log N) | ~30.9 ms |

✔ Rader’s method maintains spectral accuracy  
✔ Eliminates zero-padding distortion  
✔ Achieves logarithmic scaling  

---

## Why This Matters

In real-world applications such as:

- Seismic signal monitoring
- ECG signal analysis
- Radar systems
- Biomedical sensing

Signal lengths are often prime and cannot be processed efficiently using traditional radix-2 FFT methods without zero-padding.

This project demonstrates a mathematically rigorous and computationally efficient alternative that preserves spectral accuracy.

## Key Results

- Rader’s Algorithm achieves O(N log N) performance for prime-length signals.
- Produces spectra identical to brute-force DFT (within floating-point tolerance).
- Eliminates spectral leakage caused by zero-padding.
- Demonstrates practical application of number theory in DSP.

## How to Run (Python Backend)

```bash
**pip install numpy
python rader_algorithm.py

