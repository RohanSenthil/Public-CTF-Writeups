# Intercepted 2 [448 Points]

Congrats! If you can see this, you’ve successfully solved our previous challenge. However, it looks like we’ve intercepted another packet capture. Can you find out what’s hidden in here?

Attached is the packet capture.

## Solution
1. We open the packet capture using wireshark.
2. By looking at the protocol hierachy, FTP is of interest as we could recover a file.
3. We then apply the filter ```FTP```.
4. Looking at the packets we can see that the password ```n0tth3P@ssw0rd``` was used to login, this come be of use later.
5. We then find a packet with flag-encrypted.pdf in its info, however this does not contain the file and is merely a request
6. We search for the pdf file by applying the filter ```frame contains "%PDF-"```
7. There is only one packet, we right click that packet and select follow TCP stream.
8. Change from show data as ASCII to show data as Raw.
9. Then click save as, name the file anything and save it any folder.
10. When trying to open the pdf file we just saved, we are prompted with a password, by using the password we got from the ftp packet captures we are able to view the pdf file contents which contains the flag.
```
Flag: NYP{wir3sh4rk_exp0rt_0bjects}
```
