# Crack The Code [103 Points]

One of the researchers left a link to a note before they were infected. The URL to the code is encrypted. Can you decrypt it to get the link?
OVTWOY3GHIXS6Y3OMZTXE33WMEXHAYT2F52WQVDTKM4XG4A=

# Solution
1. Using dCode's cipher identifier, we can identify the cipher is Base32.
2. We decrypt the cipher text using CyberChef, giving us the link ```uggcf://cnfgrova.pbz/uhTsS9sp```
3. When we search the link, we get a result on ROT13.
4. We decrypt the link ```uggcf://cnfgrova.pbz/uhTsS9sp``` with ROT13 in CyberChef, giving us the link ```https://pastebin.com/huGfF9fc```
5. Visting the link gives us the flag.
```
Flag: NYP{s1mp13_crypt0_ch3113ng3}
```
