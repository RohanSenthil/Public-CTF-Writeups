# Telecommunciation [492 Points]
Hello MyNameIsFlagbot. Guess where I am and I will tell you where the rest of the survivors are.

## Solution
1. Using an OSINT enumeration tool, https://whatsmyname.app/, we search for MyNameIsFlagbot.
2. The only result is a telegram bot, following the link provided to the telegram bot there is a flag in the wrong format ```RCT{xipifsxw_ivvsv_syx}```.
3. Thought it was a decoy at first but it does look encrypted so we put it in dCode's cipher: https://www.dcode.fr/cipher-identifier
4. We try to decrypt it using the cipher algorithms suggested to us by dCode's analyser
5. It turns out to be encrypted using the Caesar/Shift Cipher.
6. Bruteforce decrypting it with dCode gives us the flag.
```
Flag: NYP{telebots_error_out}
```
