# EzBof [413 Points]

The government has set up a buffer zone to separate the zombies and the survivors, but the buffer zone is overflowing with the survivors and zombies! What should you do now?

nc ezbof.nypinfsecctf.tk 8009

Attached is source.c file
```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <signal.h>

#define FLAGSIZE_MAX 64

char flag[FLAGSIZE_MAX];

void sigsegv_handler(int sig) {
  fprintf(stderr, "%s\n", flag);
  fflush(stderr);
  exit(1);
}

void vuln(char *input){
  char buf[128];
  strcpy(buf, input);
}

int main(int argc, char **argv){

  FILE *f = fopen("flag.txt","r");
  char user_input[160];

  if (f == NULL) {
    printf("Flag File is Missing\n");
    exit(0);
  }
  fgets(flag,FLAGSIZE_MAX,f);
  signal(SIGSEGV, sigsegv_handler);

  gid_t gid = getegid();
  setresgid(gid, gid, gid);

  printf("Please enter a user input: ");
  fgets(user_input, 160, stdin);

  if (strlen(user_input)==1){
    printf("Please provide an input next time\n");
  } else {
    vuln(user_input);
    printf("You entered: %s", user_input);
  }

  return 0;
}
```

## Solution

1. When connecting to the server, we are prompted to input something. Since the challenge description hints at a buffer overflow, we will try that.
2. Inspecting the code,```user_input``` is defined as a char array of size 160. When getting the user input, only the first 160 characters are read, hence a buffer overflow will not work here. However, the ```user_input``` is later passed through the ```vuln()``` function/
3. Inspecting the ```vuln()``` function, we realise that ```user_input``` is copied to ```buf```, a char array of size 128. ```strcpy()```  returns a pointer to the destination string dest. Thus the output printed will be that stored in ```buf```.
```
void vuln(char *input){
  char buf[128];
  strcpy(buf, input);
}
```
4. Thus, we can now execute a buffer overflow by simply inputing anything with more than 128 characters to obtain the flag.
```
Please enter a user input: AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA
```
```
Flag: NYP{B0f_i5_3A5y}
```


