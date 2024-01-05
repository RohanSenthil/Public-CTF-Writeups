# Lockdown [388 Points]

The first step to contain the virus is to avoid the zombies from leaving the laboratory. To lock down the entire laboratory, you have to decode the encrypted password. You understand that the key is important! Hurry up!
 
Attached is a .txt file that reads: 
```
emgbzgg!yhkw_dbcr_wuxv_kdi_ytvr_mw
```

## Solution

1. The challenge description hints to us that the cipher text is encrypted with an encryption algorithm that uses a key, with the key being important
2. Using dCode to identify the cipher and trying to decrypt using the different recommended algorithms with the key important does not gives us any results for the first few suggested algorithms.
3. Eventually the last option, Vigenere Cipher gives us a clear text. Wrap it with the flag format to obtain the flag.
```
Flag: NYP{warning!lock_only_when_you_have_to}
```
