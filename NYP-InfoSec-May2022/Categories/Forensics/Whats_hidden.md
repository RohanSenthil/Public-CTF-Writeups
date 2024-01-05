# Whats hidden? [492 Points]
Are there any more survivors who are not vaccinated yet? You look at this image and hope to find some clues…

Attached is a .jpg file

## Solution
1. We use xxd to create a hexdump of the .jpg file
```
xxd challenge.jpg
```
3. The hexdump contains a base64 encoded string ```TllQe3NpbXBsMy1zdDNnby05NDcxM30=```
4. Decoding it in CyberChef gives us the flag.
```
Flag: NYP{simpl3-st3go-94713}
```
