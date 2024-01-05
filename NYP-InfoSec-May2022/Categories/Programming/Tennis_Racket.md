# Tennis Racket [489 Points]

I am tasked to connect to a server and use Racket to obtain the flag hidden in the server.

## Solution

1. Connect to Server
```
nc tennis1.nypinfsecctf.tk 8010
```

2. List contents of current directory       
```
(directory-list)
```     
   
* A file called "flag" is found, thought it was a directory at first but when trying to navigate to it, it gives a system error stating that flag is not a directory. Thus, it could only be a file.

3. List contents of flag file to obtain flag
```
(file->list "flag")    
```
```
Flag: NYP{lisp_or_scheme_idk_anymore}
```
