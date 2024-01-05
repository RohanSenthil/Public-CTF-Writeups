# Walking In The Dead - 2 [486 Points]

"I got the code...What's next?" You decoded the cipher. You looked around in the room and guessing what you could do with the code. There's an email sent to you, with an image attached...

Attached is a .jpg file

## Solution
1. We use steghide to extract whatever is hidden in the .jpg image. 
```
steghide extract -sf X2steg.jpg
```
2. When prompted with the passphrase, we use the passphrase obtained as the flag from the first Walking In The Dead challenge: ```1420KEYRDSEATLANTAYOUFOUNDTHE1LCODE```
3. A new .txt file is the created, we then view the contents of the file to obtain the flag. (Wrap the flag with the flag format)
```
cat steganopayload3800413.txt
```
Output:
```
"YOU ARE HERE..DO U NOW STILL THINK IT IS JUST A COINCIDENCE?"
FLAG- "YOUFOUNDTHECODEL2CODE_DRIVE?"


Are u able to find the doc?

sharing&ouid=115932714019779054721&rtpof=true&sd=true%    
```
```
Flag: NYP{YOUFOUNDTHECODEL2CODE_DRIVE?}
```
