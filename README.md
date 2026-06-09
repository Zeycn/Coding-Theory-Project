# Coding-Theory-Project

# EE431 Project: Concatenated Coding System Analysis

**Author:** Zeynep Canoğlu

## About the Project
In this project, I designed a digital communication system to test how well we can fix errors in data when it's sent over a noisy channel. The goal was to see if combining two different error-correction techniques (concatenated coding) is better than using them one by one.

## What I Did
I wrote a Python simulation from scratch to test how the system handles noise. I built three main parts:
* **Hamming (7,4) Code:** To fix single-bit errors in blocks.
* **Convolutional Code & Viterbi Decoder:** To handle and clean random errors.
* **Noisy Channel:** A simulator that adds noise to the data to see if the system can still recover the original message.

I compared these three setups:
1. System with only Hamming code.
2. System with only Viterbi decoding.
3. My concatenated system (using both).

## How to Run
Everything is written in Python. To see the results:

1. Make sure you have Python installed.
2. Download all the files to your computer.
3. Open a terminal (or command prompt) in the folder where the files are.
4. Simply run the code by typing:
   `python main.py`

When the code runs, it will test the system with different noise levels and print the error rates (BER) to the terminal so we can compare them.

## Results Summary
My simulation shows that the concatenated system works perfectly with **0 errors** at low noise levels. However, when the noise gets very high (like p=0.15), the system fails. I found that this happens because the Viterbi decoder starts making "error bursts" at high noise, and the Hamming code isn't strong enough to fix those grouped errors, so the whole thing breaks.
