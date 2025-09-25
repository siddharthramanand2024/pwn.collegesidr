# Module 10: Untangling Users

##  Challenge 1 
 **Becoming root with su**

Process:
su is an old command to become root. 
it asks for password and hence it is not used anymore.
In this challenge we become root using su and then find the flag using ls.
```
hacker@users~becoming-root-with-su:~$ su
Password: 
root@users~becoming-root-with-su:/home/hacker# ls
COLLEGE  PWN  instructions  not-the-flag  the-flag
Desktop  a    myflag        pwn_output    the-flag.
root@users~becoming-root-with-su:/home/hacker# cat PWN
COLLEGE
root@users~becoming-root-with-su:/home/hacker# cat not-the-flag
pwn.college{4uZV0CvsfQARguHluP-yEE-I4W8.QX1UDN1wiMyAzNzEzW}
```
Flag:
> pwn.college{4uZV0CvsfQARguHluP-yEE-I4W8.QX1UDN1wiMyAzNzEzW}


##  Challenge 2 
 **Other users using su**

Process:
we can switch some other user using su and if we know their password.
```
hacker@users~other-users-with-su:~$ su zardus
Password: 
zardus@users~other-users-with-su:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{QVHp_F8dusRmlpfAqnzfeXQqKTK.QX2UDN1wiMyAzNzEzW}
```
Flag:
> pwn.college{QVHp_F8dusRmlpfAqnzfeXQqKTK.QX2UDN1wiMyAzNzEzW}

##  Challenge 3
 **Cracking passwords using su **

Process:

if shadow where password are stored gets leaked we can crack the passwords of the users using john the ripper method.

```
hacker@users~cracking-passwords:~$ john /challenge/shadow-leak
Created directory: /home/hacker/.john
Loaded 1 password hash (crypt, generic crypt(3) [?/64])
Press 'q' or Ctrl-C to abort, almost any other key for status
aardvark         (zardus)
1g 0:00:00:20 100% 2/3 0.04866g/s 283.3p/s 283.3c/s 283.3C/s Johnson..buzz
Use the "--show" option to display all of the cracked passwords reliably
Session completed
hacker@users~cracking-passwords:~$ su zardus
Password: 
zardus@users~cracking-passwords:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{IltY6zUYxltOOK5C8VwsoXCnkF6.QX3UDN1wiMyAzNzEzW}

```
Flag:
> pwn.college{IltY6zUYxltOOK5C8VwsoXCnkF6.QX3UDN1wiMyAzNzEzW}

##  Challenge 4
 **Using sudo**

Process:
sudo is the new way of accessing root instead of su.
it does not use passwords and gives access depending upon policies.

```
hacker@users~using-sudo:~$ sudo ls
COLLEGE  PWN  instructions  not-the-flag  the-flag
Desktop  a    myflag        pwn_output    the-flag.

hacker@users~using-sudo:~$ sudo cat not-the-flag
pwn.college{kqUdX_WslA_3wzJWx-kYjX8BLnQ.QX4UDN1wiMyAzNzEzW}
```
Flag:
> pwn.college{kqUdX_WslA_3wzJWx-kYjX8BLnQ.QX4UDN1wiMyAzNzEzW}
