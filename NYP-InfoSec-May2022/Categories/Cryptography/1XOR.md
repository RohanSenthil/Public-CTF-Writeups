# 1XOR [489 Points]

You're trapped in the lab, and the doors are locked. The only hint you have is Decrypt: 4fb/1Pef/fDd7vzOys7c1v3v19I=

## Solution

1. Looking at the cipher text, there is a ```=``` at the back, could this be base64 encoded? But the challenge name is XOR. Perhaps both XOR and base64 was used to encrypt the flag.
2. We place base64 first, then XOR bruteforce in CyberChef to decrypt the cipher text.
3. Ctrl + F to search for the flag format among the bruteforce results.
```
Flag: NYP{X0R_rASaeasyR@x}
```
