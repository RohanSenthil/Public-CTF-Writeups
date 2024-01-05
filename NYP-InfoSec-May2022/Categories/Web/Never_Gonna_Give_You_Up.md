# Never Gonna Give You Up [379 Points]

You have been walking for a few hours. Zombies are everywhere. Are you the only survivor now? Should you give up?

http://giveup.nypinfsecctf.tk

## Solution

1. Inspect element to view where the link leads to.
```
<a href="flag.html">here</a>
```
2. Going to the link http://giveup.nypinfsecctf.tk/flag.html redirects to a rick roll, thus we use curl instead to get the flag.
```
curl http://giveup.nypinfsecctf.tk/flag.html
```
```
Flag: NYP{r1ck_r0ll3d}
```
