# ODYSSEY ENIGMA (Enigma Machine Simulator)

A Python-based implementation of the historic Enigma cipher machine, allowing users to encrypt messages using a mechanism inspired by the machines used during World War II. [page:35]

**Video Demo:**  
[YouTube](https://youtu.be/9F7QoQ1kr0s)

---

## Overview

Odyssey Enigma is a command-line Enigma machine simulator written in Python. It models the core components of the machine — rotors, reflector, and plugboard — and reproduces authentic rotor stepping, including the double-step behavior. [page:35]

This project was originally built as my **CS50x final project**, and it has since grown into a personal passion project for exploring historical cryptography and software design. [page:35]

---

## Features

- Multiple rotor models: Supports rotors I–VIII, BETA, and GAMMA with historically inspired wiring configurations. [page:35]
- Configurable reflectors: Includes reflector models B, C, BT, and CT. [page:35]
- Plugboard support: Up to 10 character-pair swaps for additional encryption layers. [page:35]
- Authentic rotor stepping: Notch-based stepping, including the classic double-step behavior. [page:35]
- Real-time encryption: Interactive, keyboard-driven interface for live message encryption. [page:35]

---

## Usage

Run the Enigma machine simulator with:

```bash
sudo python3 enigma.py -R [rotor models] -M [starting positions] --reflector [reflector model] [plugboard swaps]
```

### Arguments

- `-R, --rotors`  
  Rotor models from left to right (required).  
  Available: `I`, `II`, `III`, `IV`, `V`, `VI`, `VII`, `VIII`, `BETA`, `GAMMA`. [page:35]

- `-M, --mode`  
  Initial rotor window positions (required). Must be one letter (A–Z) per rotor, matching the number of rotors specified. [page:35]

- `--reflector`  
  Reflector model (required).  
  Available: `B`, `C`, `BT`, `CT`. [page:35]

- `Plugs`  
  Optional plugboard swaps, specified as pairs (e.g., `AB CD EF` for A↔B, C↔D, E↔F). Maximum 10 swaps. [page:35]

### Examples

```bash
# Basic setup with three rotors
sudo python3 enigma.py -R I II III -M A A A --reflector B

# With plugboard configuration
sudo python3 enigma.py -R I II III -M Q E V --reflector B AB CD EF

# With rotors VI, VII, VIII
sudo python3 enigma.py -R VI VII VIII -M A A A --reflector C GH IJ KL MN OP QR
```

[page:35]

---

## How It Works

When you press a key:

1. Plugboard: The character is optionally swapped according to plugboard pairs. [page:35]  
2. Rotor stepping: Rotors step according to their notch positions (rightmost always steps; middle double-steps in some cases). [page:35]  
3. Forward path: Signal passes through the rotors from right to left. [page:35]  
4. Reflection: The reflector sends the signal back. [page:35]  
5. Backward path: Signal passes back through the rotors from left to right using inverse wiring. [page:35]  
6. Plugboard output: Final character passes through the plugboard again and is displayed. [page:35]

With the same rotor/reflector/plugboard settings, encryption and decryption are identical — typing the ciphertext with the same configuration yields the original message. [page:35]

---

## Components

- **Rotor** – Implements wiring, notch positions, and forward/backward transformations. [page:35]  
- **Reflector** – Provides symmetric mapping to send signals back through the rotors. [page:35]  
- **Plugboard** – Adds a configurable substitution layer. [page:35]  
- **EnigmaCircuit** – Orchestrates rotor stepping and the full encryption pipeline. [page:35]

---

## About This Project

This project is both my **CS50x final project** and a **personal passion project** exploring cryptography, historical machines, and Python software architecture. [page:35]

If you are learning about Enigma or cryptography, you are welcome to **read** and **study** this code for understanding. However, please **do not copy this code** for coursework, problem sets, or final projects that you will submit as your own work. Writing your own implementation is not only required for academic integrity but also the best way to actually learn.

---

## Copyright

**© 2026 Syed Navid Nowroz (Twoki). All rights reserved.**

All software rights for this project are reserved for **Twoki**.

No permission is granted to use, copy, modify, merge, publish, distribute, sublicense, or sell copies of this software, in whole or in part, without **explicit written consent** from the copyright holder.

If you are interested in using this project or its code in any capacity beyond personal study, please contact me first.

---

## Contact

For permission requests, questions, or collaboration:

- GitHub: [@navid-nowroz](https://github.com/navid-nowroz)
- Email: [Email me here](mailto:twokiii@zohomail.com)
