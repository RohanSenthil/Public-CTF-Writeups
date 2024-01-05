# Camp CyberCure: Namelist [442 Points]

Given a .txt file of a list of suspects as well as the following information:    

Person 1: Same first name and last name.    
Person 2: Same last name as a 2010 Rock and Roll Hall of Fame Inductee.     
Person 3: Digits of their phone number add up to 61    
Person 4: Oldest of three brothers.    

One of these four suspects has only one letter 'o' in their name.    

I am tasked to find the leader and use their **phone number as the password to unzip the zip file containing the flag**

## Solution

I decided to opt for a dictionary attack again as I was too lazy to go through the clues.

1. Using **crunch** I generated a wordlist for all 8 digit numbers (since all phone numbers in singapore are 8 digits)   
```
crunch 8 8 -t %%%%%% -o num.txt
```

2. Dictionary attack using **fcrackzip**   
```
fcrackzip -v -u -D -p num.txt flag_hp.zip
```

3. Unzip file using password obtained from above command to get flag
```
unzip -P 97475221 flag_hp.zip
```

4. View contents of unzipped file
```
cat flag_hp.txt
```
```
Flag: NYP{0h-0h-Armadeussss}
```
