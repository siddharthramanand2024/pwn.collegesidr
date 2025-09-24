# Module 5: File Globbing

## Challenge 1
** Matching with* **

Process:
since they have put condition on cd we have to use *(globbing) on the directory challenge and change directories.
* matches pattern.
then we run challenge run to get the flag.

```
This challenge resets your working directory to /home/hacker unless you change 
directory properly...
hacker@globbing~matching-with-:~$ cd /ch*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{kGRwIQzOxAT_1Be4U2mO11vdKZO.QXxIDO0wiMyAzNzEzW}
```

Flag:
> pwn.college{kGRwIQzOxAT_1Be4U2mO11vdKZO.QXxIDO0wiMyAzNzEzW}

## Challenge 2
** Matching with ? **

Process:
we have to use ? to change directory.
? works the same as * but matches only one character.

```
hacker@globbing~matching-with-:~$ cd /??a??enge/challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{4DbenQhpV3VYnsGrIMKsTaf-Mv_.QXyIDO0wiMyAzNzEzW}
```

Flag:
>pwn.college{4DbenQhpV3VYnsGrIMKsTaf-Mv_.QXyIDO0wiMyAzNzEzW}

## Challenge 3
** Matching with [] **

Process:
[] matches all the characters in its subset.

```
hacker@globbing~matching-with-:~$ cd /challenge/files
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[absh]
You got it! Here is your flag!
pwn.college{Q1pPDCkHepFAde10nhTKFbeqA0Y.QXzIDO0wiMyAzNzEzW}
```

Flag:
> pwn.college{Q1pPDCkHepFAde10nhTKFbeqA0Y.QXzIDO0wiMyAzNzEzW}

## Challenge 4
**Matching paths with []**
Globbing happens on path basis so we can enter paths as arguments as well.

```
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[absh]
You got it! Here is your flag!
pwn.college{c8AconTDQKdnqvyIVN4qk0cHGjy.QX0IDO0wiMyAzNzEzW}
```

Flag:
> pwn.college{c8AconTDQKdnqvyIVN4qk0cHGjy.QX0IDO0wiMyAzNzEzW}

## Challenge 5
**Multiple globs**

Process:
we can use multiple globbing too.

```
hacker@globbing~multiple-globs:~$ cd /challenge/files
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run *p*
You got it! Here is your flag!
pwn.college{EM4WGimVQ3zcs5Pcy5OrpvJP1di.0lM3kjNxwiMyAzNzEzW}
```

Flag:
>pwn.college{EM4WGimVQ3zcs5Pcy5OrpvJP1di.0lM3kjNxwiMyAzNzEzW}

## Challenge 6
**Mixing globs**

Process:
take starting letter of each of the three words and put it in the square bracket glob.

```
hacker@globbing~mixing-globs:/challenge/files$ cd /challenge/files
/challenge/run [cep]*
You got it! Here is your flag!
pwn.college{s4m8QxbhGhaLGYqT2u7QMz9tcj1.QX1IDO0wiMyAzNzEzW}
```

Flag:
> pwn.college{s4m8QxbhGhaLGYqT2u7QMz9tcj1.QX1IDO0wiMyAzNzEzW}

## Challenge 7
** Exclusionary Globbing**

Process:
use ! to negate the square brackets.
* requied to match all characters od the file as [] matches only single character.

```
hacker@globbing~exclusionary-globbing:~$ cd /challenge/files
hacker@globbing~exclusionary-globbing:/challenge/files$ cd /challenge/files
/challenge/run [!pwn]*
You got it! Here is your flag!
pwn.college{A76Sq1-DAeQYvBFbwrD45qHP_cz.QX2IDO0wiMyAzNzEzW}
```

Flag:
> pwn.college{A76Sq1-DAeQYvBFbwrD45qHP_cz.QX2IDO0wiMyAzNzEzW}

## Challenge 8
** Tab completion**

Process:
start entering the file path and press tab .. it will autocomplete and then enter to get the flag.

```
hacker@globbing~tab-completion:~$ cat /challenge/pwn<TAB>
pwn.college{UwIY5FFKgFTw8TCx-rYGaEKZVOe.0FN0EzNxwiMyAzNzEzW}
```

Flag:
> pwn.college{UwIY5FFKgFTw8TCx-rYGaEKZVOe.0FN0EzNxwiMyAzNzEzW}

## Challenge 9
**Multiple options for tab completion**

Process:
when pressing tab twice it will show all the multiple options.
choose the option which gives the flag.

```
hacker@globbing~multiple-options-for-tab-completion:~$ cd /challenge/files
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ cat /challenge/files/p<TAB><TAB>
pwn                    pwn-the-planet         pwncollege-flag        pwncollege-flyswatter  
pwn-college            pwncollege-family      pwncollege-flamingo    pwncollege-hacking     
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ cat /challenge/files/pwncollege-flag
pwn.college{QFJfYaXWfXld7uRoHZxhyj-tzyj.0lN0EzNxwiMyAzNzEzW}
```

Flag;
> pwn.college{QFJfYaXWfXld7uRoHZxhyj-tzyj.0lN0EzNxwiMyAzNzEzW}

## Challenge 10
** Tab completion for commands**

Process:
tab can also be used to autocomplete commands.

```
hacker@globbing~tab-completion-on-commands:~$ pwncollege<TAB>
$ pwncollege-11815 
Correct! Here is your flag:
pwn.college{IRm4PsVSnlxxr355lijRlUD6iFV.0VN0EzNxwiMyAzNzEzW}
```

Flag;
> pwn.college{IRm4PsVSnlxxr355lijRlUD6iFV.0VN0EzNxwiMyAzNzEzW}

