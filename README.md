# 🧩 Prime-Gap Entropy Generator  
### *Deterministic Unpredictability for Cryptographic Randomness*

This repository contains the Python implementation and simulation scripts used in the paper:  
**“Primes Don’t Play Fair”** 
by **Joshua Sanctus (2025)**.

---

## 🔍 Overview  
This project explores how the **irregular spacing between consecutive prime numbers** can serve as a natural source of computational entropy.  
Although prime numbers follow deterministic laws, their **gaps** display short-range unpredictability.  
This property can strengthen cryptographic key generation, password hashing, and entropy pooling in decentralized systems.  

The core idea is that **mathematical irregularity can mimic stochastic randomness**, providing strong entropy without relying on external hardware.

---

## 🧠 Core Concept  

For consecutive primes \( p_n \):
\[
g_n = p_{n+1} - p_n
\]

Normalized gaps:
\[
G_i = \frac{g_i}{\max(g_i)}
\]

These normalized gaps are concatenated with a user password and hashed with **SHA-256** to form an *augmented entropy seed*.  

---

## ⚙️ Features  

- Prime-gap–driven entropy generation from deterministic mathematics  
- Augmented SHA-256 hashing for password or key derivation  
- Shannon entropy \(H_p\) and normalized entropy \(H_p^*\) computation  
- Randomness evaluation with **NIST SP 800-22 Monobit** and **Chi-squared** tests  
- Visual analysis of prime-gap irregularity using Matplotlib  

---

## 📊 Example Output  

```
Enter a password: Sheldon$31

=== PRIME-GAP ENTROPY DEMONSTRATION ===
Entropy (H_p): 2.9868 bits
Normalized Entropy (H_p*): 0.7467

Standard SHA-256: bdbad66c936d148504c093aeb65ac7ddf104b7981d3a6112a9e45daba4d82730
Augmented Hash  : ace43caef664dfc65ad4296a9ca45aaf75a2bbadd45e56a9381e766194c8b9f7

=== RANDOMNESS COMPARISON (NIST + CHI²) ===
Standard SHA-256:
  Monobit p-value     : 0.7077 (PASS)
  Chi² p-value        : 0.7077 (PASS)
  Ones proportion     : 48.83%

Prime-Gap Augmented SHA-256:
  Monobit p-value     : 0.2113 (PASS)
  Chi² p-value        : 0.2113 (PASS)
  Ones proportion     : 53.91%
```

---

## 🧪 Installation

```bash
git clone https://github.com/<your-username>/prime-gap-entropy.git
cd prime-gap-entropy
pip install -r requirements.txt
```

**Requirements:**
```
sympy
numpy
matplotlib
```

---

## ▶️ Usage

Run the main script:

```bash
python prime_gap_simulation.py
```

Optional arguments can be added inside the code to change:
- `n_primes`: number of primes sampled (default = 500)
- `password`: input string for augmented hashing

---

## 📈 Visualization

The tool automatically generates and saves a plot:

```
prime_gap_entropy_plot.png
```

which visualizes the **normalized prime-gap irregularity**:
- X-axis: Index of prime pair  
- Y-axis: Normalized gap value \(G_i\)

---

## 📚 Citation

If you use this work, please cite:

```
@article{sanctus2025primeentropy,
  title   = {Primes Don’t Play Fair: Deterministic Entropy from Prime-Gap Irregularity in Cryptographic Hashing},
  author  = {Joshua Sanctus},
  year    = {2025},
  journal = {Preprint},
  url     = {https://github.com/<your-username>/prime-gap-entropy}
}
```



---

> *“The primes are deterministic — their gaps are not.  
> Between order and chaos lies entropy.”* — *Joshua Sanctus*
