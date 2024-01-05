# Camp CyberCure: Lunch Time [280 Points]

Given an image of a restaurant and the general location (near Jurong East MRT), I am tasked to find the **postal code** of the building to use as the **password for a zip folder containing the flag**.     

## Solution

After searching around Jurong East MRT on goolge maps, I decided to bruteforce the zip file password instead.

1. Using **crunch** I generated a wordlist for all 6 digit numbers (since all postal codes in singapore are 6 digits)   
```
crunch 6 6 -t %%%%%% -o postal.txt
```

2. Dictionary attack using **fcrackzip**   
```
fcrackzip -v -u -D -p postal.txt flag_restaurant.zip
```

3. Unzip file using password obtained from above command to get flag
```
unzip -P 609079 flag_restaurant.zip
```

4. View contents of unzipped file
```
cat flag_restaurant.txt
```
```
Flag: NYP{S0m3_g00d_f00d_on_THE_WAY}
```
