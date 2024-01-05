# Intercepted 1 [369 Points]

We've intercepted this packet capture. Looks like someone has tried to unsuccessfully login to our admin account in this CTF platform. Put the flag in NYP{FLAG} format.

Attached is the packet capture.

## Solution
1. We open the packet capture using wireshark.
2. Since we are looking for the password, since it is suggested in the challenge description, we apply the filter ```http```.
3. Another way to arrive at this inference is by looking at the protocol hierachy, where HTML Form URL Encoded is of interest.
4. We click on the packet with POST, the one where information from the form is sent. In there we can find the password.
5. Wrap the password with the flag format and you get the flag.
```
Flag: NYP{n0tth3P@ssw0rd}
```
