# Silver Head [442 Points]

Congrats! You managed to reach here. Now you have to activate the self-destruct system. Only Silver Head know what the password is. The only information you know about Silver Head is that it is not a living human...

http://silver.nypinfsecctf.tk

## Solution

1. Description and website hints that silver head is a robot and that only he knows the password so we visit ```http://silver.nypinfsecctf.tk/robots.txt```
```
User-Agent: *
Disallow: /NYPCTFflag.html
````
2. We can then obtain the flag by visiting ```http://silver.nypinfsecctf.tk/NYPCTFflag.html```
```
Flag: NYP{danger!this_action_is_irreversible}
```
