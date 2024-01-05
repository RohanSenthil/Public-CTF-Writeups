# Reverse Numbers [359 Points]

Spot check! Another security question to prove that you’re not infected. Reverse the code and get the flag. The original output of file.py is [87, 151, 83, 152, 90, 93, 132, 129, 113, 87, 90, 147, 130, 53, 56, 113, 72, 137, 95, 121, 51]

Attached is a file.py file.
```
chars = "`1234567890-=qwertyuiop[]asdfghjkl;'zxcvbnm,./~!@#$%^&*()_+QWERTYUIOP{}|ASDFGHJKL:ZXCVBNM"
chars_num = {}
x = 0
for i in chars:
    chars_num[i] = x
    x += 1

flag = ""
sum_of_nums = 0
sum_of_nums_list = []
for i in flag:
    if sum_of_nums < 100:
        sum_of_nums += chars_num[i]
    elif sum_of_nums > 100:
        sum_of_nums -= chars_num[i]
    sum_of_nums_list.append(sum_of_nums)
print(sum_of_nums_list)
# sum_of_nums_list = [87, 151, 83, 152, 90, 93, 132, 129, 113, 87, 90, 147, 130, 53, 56, 113, 72, 137, 95, 121, 51]
```

## Solution

1. First we print out the chars_num dictionary to find out what is in it.
```
print(chars_num)
{'`': 0, '1': 1, '2': 2, '3': 3, '4': 4, '5': 5, '6': 6, '7': 7, '8': 8, '9': 9, '0': 10, '-': 11, '=': 12, 'q': 13, 'w': 14, 'e': 15, 'r': 16, 't': 17, 'y': 18, 'u': 19, 'i': 20, 'o': 21, 'p': 22, '[': 23, ']': 24, 'a': 25, 's': 26, 'd': 27, 'f': 28, 'g': 29, 'h': 30, 'j': 31, 'k': 32, 'l': 33, ';': 34, "'": 35, 'z': 36, 'x': 37, 'c': 38, 'v': 39, 'b': 40, 'n': 41, 'm': 42, ',': 43, '.': 44, '/': 45, '~': 46, '!': 47, '@': 48, '#': 49, '$': 50, '%': 51, '^': 52, '&': 53, '*': 54, '(': 55, ')': 56, '_': 57, '+': 58, 'Q': 59, 'W': 60, 'E': 61, 'R': 62, 'T': 63, 'Y': 64, 'U': 65, 'I': 66, 'O': 67, 'P': 68, '{': 69, '}': 70, '|': 71, 'A': 72, 'S': 73, 'D': 74, 'F': 75, 'G': 76, 'H': 77, 'J': 78, 'K': 79, 'L': 80, ':': 81, 'Z': 82, 'X': 83, 'C': 84, 'V': 85, 'B': 86, 'N': 87, 'M': 88}
```
2. We not have to find out how the output ```[87, 151, 83, 152, 90, 93, 132, 129, 113, 87, 90, 147, 130, 53, 56, 113, 72, 137, 95, 121, 51]``` is obtained.
3. Analysing the code, since ```sum_of_nums``` is ```0``` at first, ```sum_of_nums += chars_num[i]``` at the first occurence of the loop, in this case ```chars_num[i]``` is ```87```, based on the intended output. Thus, we can infer that the first letter of the string ```flag``` should be 'N'.
4. ```sum_of_nums``` is now ```87```, thus ```sum_of_nums += chars_num[i]```, which equals ```151``` based on intended output.
```
87 + chars_num[i] = 151
# Therefore chars_num[i] = 151 - 87 = 64 = Y (base on chars_num dictionary)
# Thus second letter of the string flag is 'Y'.
```
5. Repeat this process until the flag is obtained. Flag length is same as list length of the intended output.
```
Flag: NYP{R3v3rs3_tH3_nUms}
```
