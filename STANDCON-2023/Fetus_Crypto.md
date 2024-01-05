# Fetus Crypto [50 Points]
*Solved By r0han*

My friend Timmy told me about this cool encryption! What is it behind this message?    

## Solution

Looks like some kind of ROT or Shift. Since we know first few letters is STANDCON, we can derive that it is a ROT47 cipher which uses a 94 ascii character set.
I solved it using Python but you could easily do so using Cyberchef aswell.

```
encrypted = "$%p}sr~}LE_52J0x0=62C?E023@FE0#~%cfPPPN"
new = ""
for char in encrypted:
    if ord(char) + 47 <= 125:
        new += chr(ord(char) + 47)
    else:
        new += chr((ord(char) + 47) - 94)

print(new)
```
```
Flag: STANDCON{t0day_I_learnt_about_ROT47!!!}
```
