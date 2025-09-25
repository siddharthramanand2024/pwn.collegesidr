# Module 7 : Shell variables

##  Challenge 1 
 **Printing Variables**

Process:

Prepending a `$` before the arguement for `echo` indicates that `echo` is supposed to printa varibale.
In this challenge, `echo $FLAG` prints variable `FLAG` which gives us the flag.

```
hacker@variables~printing-variables:~$ echo $FLAG
pwn.college{4lfabnkE_FyUurvCAw69aKRCpGf.QX3UTN0wiMyAzNzEzW}
```
Flag:
> pwn.college{4lfabnkE_FyUurvCAw69aKRCpGf.QX3UTN0wiMyAzNzEzW}


##  Challenge 2 
 **Setting Variables**

Process:

we can set a variable value using = .

in this we set PWN equal to  the value COLLEGE and print it using echo command.

```
hacker@variables~setting-variables:~$ PWN=COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{csVnwyk8HBM1t9i4VWd5bcgW0AC.QX5UTN0wiMyAzNzEzW}
```
Flag:
> pwn.college{csVnwyk8HBM1t9i4VWd5bcgW0AC.QX5UTN0wiMyAzNzEzW}

##  Challenge 3 
 **Setting MULTI WORD Variables**

Process:

we cant use spaaces for as shell intreprets it as a command.

hence we have to use quotes to assign multi words value to variables.
```
hacker@variables~multi-word-variables:~$ PWN="COLLEGE YEAH"
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{oSX74xNG5g2XWeAA3N_32svMwJP.QXwYTN0wiMyAzNzEzW}
```
Flag:
> pwn.college{oSX74xNG5g2XWeAA3N_32svMwJP.QXwYTN0wiMyAzNzEzW}

##  Challenge 4 
 **Exporting Variables**

Process:

we can export variables using the export command .
in this challenge we export PWN but not college variable to get the flag.

```
hacker@variables~exporting-variables:~$ export PWN=COLLEGE
You've set the PWN variable to the proper value!
hacker@variables~exporting-variables:~$ COLLEGE=PWN
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ /challenge/run
CORRECT!
You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. Great 
job! Here is your flag:
pwn.college{A3FkFzTFTEOWK3vbIBCSAynEDcI.QXyYTN0wiMyAzNzEzW}
```
Flag:
> pwn.college{A3FkFzTFTEOWK3vbIBCSAynEDcI.QXyYTN0wiMyAzNzEzW}

## Challenge 5 
 **Printing Exported Variables**

Process:

we can  print all the exported variables using the env command .
then we find the flag variable by grepping through the output and use.

```
hacker@variables~printing-exported-variables:~$ env
SHELL=/run/dojo/bin/bash
HOSTNAME=variables~printing-exported-variables
PWD=/home/hacker
MANPATH=/run/dojo/share/man:
DOJO_AUTH_TOKEN=823e75ecfc35bea2e4db6237096c4b362a68de124a2bd8a6821bb16856fd56c9
HOME=/home/hacker
LANG=C.UTF-8
FLAG=pwn.college{QonO95XJxgONUYkjYCEwQ1mLnDs.QX4UTN0wiMyAzNzEzW}
TERMINFO=/run/dojo/share/terminfo
TERM=xterm-256color
SHLVL=2
LC_CTYPE=C.UTF-8
SSL_CERT_FILE=/run/dojo/etc/ssl/certs/ca-bundle.crt
PATH=/run/challenge/bin:/run/dojo/bin:/root/.cargo/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
DEBIAN_FRONTEND=noninteractive
_=/run/dojo/bin/env
hacker@variables~printing-exported-variables:~$ cat $FLAG
cat: pwn.college{QonO95XJxgONUYkjYCEwQ1mLnDs.QX4UTN0wiMyAzNzEzW}
```
Flag:
> pwn.college{QonO95XJxgONUYkjYCEwQ1mLnDs.QX4UTN0wiMyAzNzEzW}

## Challenge 6
 **Storing output**

Process:

we can store command output using $() .

```
hacker@variables~storing-command-output:~$ PWN=$(/challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out 
and submit it!
hacker@variables~storing-command-output:~$ echo $PWN
pwn.college{Uy3esX7heMV_XKs4ympUrC1z-Ut.QX1cDN1wiMyAzNzEzW}
```
Flag:
> pwn.college{Uy3esX7heMV_XKs4ympUrC1z-Ut.QX1cDN1wiMyAzNzEzW}

## Challenge 7
 **Reading input**

Process:
we can read user input using read command .

```
hacker@variables~reading-input:~$ read PWN
COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{8UWYBxH7nIE4lE8FuwT1H3bAkPf.QX4cTN0wiMyAzNzEzW}
```
Flag:
> pwn.college{8UWYBxH7nIE4lE8FuwT1H3bAkPf.QX4cTN0wiMyAzNzEzW}


## Challenge 8
 **Reading files**

Process:
we can read files by redirecting them and then using read command .

```
hacker@variables~reading-files:~$ read PWN < /challenge/read_me
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{EMHp2whA_X7RjyGGdsulRdbDPpC.QXwIDO0wiMyAzNzEzW}
```
Flag:
> pwn.college{EMHp2whA_X7RjyGGdsulRdbDPpC.QXwIDO0wiMyAzNzEzW}


