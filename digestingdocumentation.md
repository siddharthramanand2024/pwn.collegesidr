# Module 4: Digesting Documentation

## Challenge 1
**The program for this challenge is /challenge/challenge, and you'll need to invoke it properly in order for it to give you the flag using the given documentation.**

Process:

Run `/challenge/challenge --giveflag` to get the flag as given in the documentation.

```
hacker@man~learning-from-documentation:~$  /challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{oE5P8vkpu-BN-CJoWeI-W8lSRmp.QX0ITO0wiMyAzNzEzW}
```

Flag:
>pwn.college{oE5P8vkpu-BN-CJoWeI-W8lSRmp.QX0ITO0wiMyAzNzEzW}


## Challenge 2
**Learning Complex Usage**

Process:

`--printfile` is used to print arbitary files on the terminal. The argument to it is the file path we wanna read. 

type `/challenge/challenge --printfile /flag` to get the flag

```
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{wnAb6G0y6yYgJOkEWmrDNsFbYG9.QX1ITO0wiMyAzNzEzW}
```
Flag :
>pwn.college{wnAb6G0y6yYgJOkEWmrDNsFbYG9.QX1ITO0wiMyAzNzEzW}

## Challenge 3
**Reading Manuals**

Process:

man is used to get infortmation about the command we pass as argument.

type  `man challenge` to get the description of the challenge command.

From the description see the command that will give the flag which is skyomz num in this case.

type /challenge/challenge --skyomz174 to get the flag.

```
hacker@man~reading-manuals:~$ man challenge
hacker@man~reading-manuals:~$ /challenge/challenge --skyomz 174
Correct usage! Your flag: pwn.college{s1UkyTQRoAJm7X48DzJJhJOHgJp.QX0EDO0wiMyAzNzEzW}
```
Flag:
>pwn.college{s1UkyTQRoAJm7X48DzJJhJOHgJp.QX0EDO0wiMyAzNzEzW}

## Challenge 4
**Searching Manuals**

Process:

We can search the man page of the command using `/`.

from there we find the argument ll which will print the flag

type command /challenge/challenge --ll to get the flag.

```
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ /challenge/challenge --ll
Initializing...
Correct usage! Your flag: pwn.college{0VTL_7_b5JC7ZK0enoscvJiILOk.QX1EDO0wiMyAzNzEzW}
```
Flag : 
>pwn.college{0VTL_7_b5JC7ZK0enoscvJiILOk.QX1EDO0wiMyAzNzEzW}

## Challenge 5
**Searching for manuals**
 
Process:

we first use man man  read about man.

then we use k challenge to search for manpages mentioning challenge.

upon doing this we get aduezswnmk (1)       - print the flag! which is the random manpage for challenge.

then we give man aduezswnmk to find the argument to get flag which is asuezs in this case.

```
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ man -k challenge
aduezswnmk (1)       - print the flag!
hacker@man~searching-for-manuals:~$ man aduezswnmk
hacker@man~searching-for-manuals:~$ /challenge/challenge --aduezs 696
Correct usage! Your flag: pwn.college{U6adAu9ZWPezswnmFkr6myFDpKE.QX2EDO0wiMyAzNzEzW}
```

Flag:
>pwn.college{U6adAu9ZWPezswnmFkr6myFDpKE.QX2EDO0wiMyAzNzEzW}


## Challenge 6
**Helpful commands** 

Process:

Run `/challenge/challenge --help` to get the arguments.

from the list we can see that --p gives the secret value using which we can pass --g along with that value to get the flag.

```
hacker@man~helpful-programs:~$ challenge --help
bash: challenge: command not found
hacker@man~helpful-programs:~$ flag --help
bash: flag: command not found
hacker@man~helpful-programs:~$ /challenge/challenge --help
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give you the flag
hacker@man~helpful-programs:~$ /challenge/challenge --p
The secret value is: 708
hacker@man~helpful-programs:~$ /challenge/challenge --g 708
Correct usage! Your flag: pwn.college{Q7B-XUBVdifr0r85qosU2Wg_NhD.QX3IDO0wiMyAzNzEzW}
```
Flag: 
>pwn.college{Q7B-XUBVdifr0r85qosU2Wg_NhD.QX3IDO0wiMyAzNzEzW}


## Challenge 7
**Help for Builtins**

Process:

all shell builtins can be running the help builtin.

we can also search a particular builtin using help which we do in this case by passing help challenge where challenge is a builtin.

then we choose the necessary arguments to get the flag.

```
hacker@man~help-for-builtins:~$ help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!
    
    Options:
      --fortune         display a fortune
      --version         display the version
      --secret VALUE    prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "oC0DHP9C".

hacker@man~help-for-builtins:~$ challenge --secret "oC0DHP9C"
Correct! Here is your flag!
pwn.college{oC0DHP9CwYkyCKRV8PmRMAJjFi3.QX0ETO0wiMyAzNzEzW}
```
Flag:
>{oC0DHP9CwYkyCKRV8PmRMAJjFi3.QX0ETO0wiMyAzNzEzW}
