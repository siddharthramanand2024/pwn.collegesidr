# Module 3: Comprehending commands


##  Challenge 1 
**In this challenge, I will copy the flag to the flag file in your home directory (where your shell starts). Go read it with cat!**

Process:
using $ cat flag command in the terminal to obtain the flag since it already placed in home.

```
$ cat flag
pwn.college{ga8siYw3n0X8vWHQGZZIuToGmJh.QXxcTN0wiMyAzNzEzW}
```
Flag:
> pwn.college{ga8siYw3n0X8vWHQGZZIuToGmJh.QXxcTN0wiMyAzNzEzW}

##  Challenge 2 
**reading flag with absolute path**

Process:
passing absolute path  of flag as argument to cat.
```
$ cat /flag
pwn.college{87sCeFEkwC4S7npoPAAYQ0-N4pq.QX5ETO0wiMyAzNzEzW}
```

Flag:
> pwn.college{87sCeFEkwC4S7npoPAAYQ0-N4pq.QX5ETO0wiMyAzNzEzW}

##  Challenge 3
 **reading file from a given directory** 
 
Process :
we pass the directory where flag is placed as arguments.
given directory of flag:/usr/include/drm/flag

```
~$ cat /usr/include/drm/flag
pwn.college{021HynsHTaor98Js2Hk6ZixJ3Wu.QXwITO0wiMyAzNzEzW}
```

Flag:
> pwn.college{021HynsHTaor98Js2Hk6ZixJ3Wu.QXwITO0wiMyAzNzEzW}


##  Challenge 4
 **using grep to find for a line in a file**


Process :
for grep pass string to be searched along with destination of file as arguments.

```
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep "pwn.college"  /challenge/data.txt
pwn.college{QREfiu85a_ecMPS-8PzCJvDFQCL.QX3EDO0wiMyAzNzEzW}
```
Flag:
> pwn.college{QREfiu85a_ecMPS-8PzCJvDFQCL.QX3EDO0wiMyAzNzEzW}

## Challenge 5
**use diff to find difference between two files**

Process:
pass two files destinations as arguments to files

```
$ diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt 
93a94 (differnce between two files)
> pwn.college{UltqwNFuI_mTaAlVznc9Pp1pYfk.01MwMDOxwiMyAzNzEzW}
```
Flag:
> pwn.college{UltqwNFuI_mTaAlVznc9Pp1pYfk.01MwMDOxwiMyAzNzEzW}


## Challenge 6
**finding and listing files**

Process:
```
~$ cd /challenge
hacker@commands~listing-files:/challenge$ ls
11791-renamed-run-24845  DESCRIPTION.md
hacker@commands~listing-files:/challenge$ cat 11791-renamed-run-24845
./11791-renamed-run-24845
Yahaha, you found me! Here is your flag:
pwn.college{U7hZFalBQL83rQqJIvSY3qbhqh-.QX4IDO0wiMyAzNzEzW}
```
Flag:
> pwn.college{U7hZFalBQL83rQqJIvSY3qbhqh-.QX4IDO0wiMyAzNzEzW}

## Challenge 7
**It's that simple! In this level, please create two files: /tmp/pwn and /tmp/college, and run /challenge/run to get your flag!**

Process:
use touch command to create two new files.

```
 ~$ touch /tmp/pwn
 hacker@commands~touching-files:~$ touch /tmp/college
hacker@commands~touching-files:~$ /challenge/run
Success! Here is your flag:
pwn.college{wEtEc4JIqRl3mfBUIHiin83c__1.QXwMDO0wiMyAzNzEzW}
```
Flag :
> pwn.college{wEtEc4JIqRl3mfBUIHiin83c__1.QXwMDO0wiMyAzNzEzW}



## Challenge 8
**This challenge will create a delete_me file in your home directory! Delete it, then run /challenge/check, which will make sure you've deleted it and then give you the flag!**

Process:
use rm command to delete the delete_me file.

 ``` 
 hacker@commands~removing-files:~$ rm delete_me
 hacker@commands~removing-files:~$ ls
   Desktop  a  not-the-flag
  hacker@commands~removing-files:~$ /challenge/check
   Excellent removal. Here is your reward:
  pwn.college{EeG1-4SsquPS0gtHUYo7O8ortxJ.QX2kDM1wiMyAzNzEzW}
```
Flag:
> pwn.college{EeG1-4SsquPS0gtHUYo7O8ortxJ.QX2kDM1wiMyAzNzEzW}

## Challenge 9

**This challenge wants you to move the /flag file into /tmp/hack-the-planet (do it)! When you're done, run /challenge/check, which will check things out and give the flag to you.**

Process:
use mv command to move the file to the desired location.

```
mv /flag /tmp/hack-the-planet
Correct! Performing 'mv /flag /tmp/hack-the-planet'.
hacker@commands~moving-files:~$ /challenge/check
Congrats! You successfully moved the flag to /tmp/hack-the-planet! Here it is:
pwn.college{0Ck3tUJCuMHzA3xIsZvp6boySH8.0VOxEzNxwiMyAzNzEzW}
```

Flag:
> pwn.college{0Ck3tUJCuMHzA3xIsZvp6boySH8.0VOxEzNxwiMyAzNzEzW}


## Challenge 10
**Now, it's your turn! Go find the flag, hidden as a dot-prepended file in /.**

Process:
use ls -a command to list the files starting with  a .
then use cat on various files until the flag is found.

```
~$ ls -a
.  ..  .ICEauthority  .bash_history  .cache  .config  .lesshst  .local  Desktop  a  not-the-flag
hacker@commands~hidden-files:~$ cat a
pwn.college{AOBKfipznCAJHc2erR-Z3OBdRaW.QXzMDO0wiMyAzNzEzW}
```
Flag:
> pwn.college{AOBKfipznCAJHc2erR-Z3OBdRaW.QXzMDO0wiMyAzNzEzW}
 
## Challenge 11
**In this challenge, I have hidden the flag! Here, you will use ls and cat to follow my breadcrumbs and find it.**

Process:
use combination of cat,ls and ls -a to find various clues and get the flag.

```
hacker@commands~an-epic-filesystem-quest:~$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls
SECRET  boot       dev  flag  lib    lib64   media  nix  proc  run   srv  tmp  var
bin     challenge  etc  home  lib32  libx32  mnt    opt  root  sbin  sys  usr
hacker@commands~an-epic-filesystem-quest:/$ cat SECRET
Great sleuthing!
The next clue is in: /usr/local/lib/python3.8/dist-packages/tinycss2

hacker@commands~an-epic-filesystem-quest:/$ cd /usr/local/lib/python3.8/dist-packages/tinycss2
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/tinycss2$ ls
REVELATION    ast.py  bytes.py  color3.py  nth.py  parser.py  serializer.py  tokenizer.py
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/tinycss2$ cat REVELATION
Lucky listing!
The next clue is in: /usr/share/icons/Adwaita/22x22/status
The next clue is hidden--- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.

hacker@commands~an-epic-fileystem-quest:/usr/local/lib/python3.8/dist-packages/tinycss2$ cd /usr/share/icons/Adwaita/22x22/status
hacker@commands~an-epic-filesystem-quest:/usr/share/icons/Adwaita/22x22/status$ ls -a
.  ..  .WHISPER  avatar-default.png
hacker@commands~an-epic-filesystem-quest:/usr/share/icons/Adwaita/22x22/status$ cat .WHISPER
Tubular find!
The next clue is in: /usr/share/doc/libnss3
Watch out! The next clue is trapped. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!

hacker@commands~an-epic-filesystem-quest:/usr/share/icons/Adwaita/22x22/status$ ls /usr/share/doc/libnss3
BLUEPRINT-TRAPPED  changelog.Debian.gz  copyright
hacker@commands~an-epic-filesystem-quest:/usr/share/icons/Adwaita/22x22/status$ cat /opt/libslub/.git/logs/refs/heads/TIP-TRAPPED
Tubular find!
The next clue is in: /opt/linux/linux-5.4/include/config/randomize/memory/physical
The next clue is delayed--- it will not become readable until you enter the directory with 'cd'.

hacker@commands~an-epic-filesystem-quest:/usr/share/icons/Adwaita/22x22/status$ cd /opt/linux/linux-5.4/include/config/randomize/memory/physical
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/randomize/memory/physical$ ls
CLUE  padding.h
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/randomize/memory/physical$ cat CLUE
Lucky listing!
The next clue is in: /opt/linux/linux-5.4/include/config/inline
 The next clue is hidden --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.

hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/randomize/memory/physical$ cd /opt/linux/linux-5.4/include/config/inline
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/inline$  ls -a
.  ..  .DOSSIER  read  spin  write
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/inline$ cat .DOSSIER
Lucky listing!
The next clue is in: /opt/linux/linux-5.4/arch/xtensa/lib
The next clue is delayed --- it will not become readable until you enter the directory with 'cd'.

hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/inline$ cd /opt/linux/linux-5.4/arch/xtensa/lib
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/xtensa/lib$ ls
CUE  Makefile  checksum.S  memcopy.S  memset.S  pci-auto.c  strncpy_user.S  strnlen_user.S  usercopy.S
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/xtensa/lib$ cat CUE
Yahaha, you found me!
The next clue is in: /opt/linux/linux-5.4/arch/sh/boards/mach-r2d

hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/xtensa/lib$  cd /opt/linux/linux-5.4/arch/sh/boards/mach-r2d
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/sh/boards/mach-r2d$ ls
Kconfig  MEMO  Makefile  irq.c  setup.c
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/sh/boards/mach-r2d$ cat MEMO
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{0xpOM0r6sc38ZE-aVrAbfw7zQNe.QX5IDO0wiMyAzNzEzW}
```

Flag:
> pwn.college{0xpOM0r6sc38ZE-aVrAbfw7zQNe.QX5IDO0wiMyAzNzEzW}


## Challenge 12
**create a /tmp/pwn directory and make a college file in it! Then run /challenge/run, which will check your solution and give you the flag!**

Process:
use mkdir command to create a new directory .
then use cd tot raverse that directory.
then use touch to create a new file college in it .
then run /challenge/run to get the flag.

```
hacker@commands~making-directories:~$ mkdir /tmp/pwn
hacker@commands~making-directories:~$ cd /tmp/pwn
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Success! Here is your flag:
pwn.college{gLFdtGYBevjFUpPUmHjTG_XZHsG.QXxMDO0wiMyAzNzEzW}
```

Flag:
> pwn.college{gLFdtGYBevjFUpPUmHjTG_XZHsG.QXxMDO0wiMyAzNzEzW}

## Challenge 13
[**  I've hidden the flag in a random directory on the filesystem. It's still called flag. Go find it!**]

Process:
find / -name flag 
find /: Tells the command to start searching .
-name flag: Specifies that you are looking for a file with the exact name flag.
then use cat to read the files in the given paths and see which of them generates the flag.
```
hacker@commands~finding-files:~$ find / -name flag
find: ‘/root’: Permission denied
find: ‘/etc/ssl/private’: Permission denied
find: ‘/tmp/tmp.TpSOPGOVKK’: Permission denied
/usr/local/lib/python3.8/dist-packages/pwnlib/flag
/usr/share/doc/python3-markupsafe/flag

find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/cache/private’: Permission denied
find: ‘/var/log/private’: Permission denied
find: ‘/var/log/apache2’: Permission denied
find: ‘/var/log/mysql’: Permission denied
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/mysql-keyring’: Permission denied
find: ‘/var/lib/php/sessions’: Permission denied
find: ‘/var/lib/private’: Permission denied
find: ‘/var/lib/mysql-files’: Permission denied
find: ‘/var/lib/mysql’: Permission denied
find: ‘/run/mysqld’: Permission denied
find: ‘/run/sudo’: Permission denied
find: ‘/proc/tty/driver’: Permission denied
find: ‘/proc/1/task/1/fd’: Permission denied
find: ‘/proc/1/task/1/fdinfo’: Permission denied
find: ‘/proc/1/task/1/ns’: Permission denied
find: ‘/proc/1/fd’: Permission denied
find: ‘/proc/1/map_files’: Permission denied
find: ‘/proc/1/fdinfo’: Permission denied
find: ‘/proc/1/ns’: Permission denied
find: ‘/proc/7/task/7/fd’: Permission denied
find: ‘/proc/7/task/7/fdinfo’: Permission denied
find: ‘/proc/7/task/7/ns’: Permission denied
find: ‘/proc/7/fd’: Permission denied
find: ‘/proc/7/map_files’: Permission denied
find: ‘/proc/7/fdinfo’: Permission denied
find: ‘/proc/7/ns’: Permission denied
/opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
/nix/store/7ns27apnvn4qj4q5c82x0z1lzixrz47p-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/5z3sjp9r463i3siif58hq5wj5jmy5m98-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/5n5lp1m8gilgrsriv1f2z0jdjk50ypcn-rizin-0.7.3/share/rizin/flag
/nix/store/h88mxp2mbgyj06vypwmqpy05idhwimnp-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag
/nix/store/s8b49lb0pqwvw0c6kgjbxdwxcv2bp0x4-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/bnlabj2vsbljhp597ir29l51nrqhm89w-rizin-0.7.4/share/rizin/flag
/nix/store/1hyxipvwpdpcxw90l5pq1nvd6s6jdi5m-python3.12-pwntools-4.14.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/5qz6hgb1qzpvjrsw20wyiylx5zw8b9bk-pwntools-4.14.0/lib/python3.13/site-packages/pwnlib/flag

hacker@commands~finding-files:~$ cat /usr/share/doc/python3-markupsafe/flag
pwn.college{cW8fPHPyORGyY6tEjuzCLpSjBji.QXyMDO0wiMyAzNzEzW}
```
Flag:
> pwn.college{cW8fPHPyORGyY6tEjuzCLpSjBji.QXyMDO0wiMyAzNzEzW}

## Challenge 14
**In this level the flag is, as always, in /flag, but /challenge/catflag will instead read out /home/hacker/not-the-flag. Use the symlink, and fool it into giving you the flag!**

Process:
rm /home/hacker/not-the-flag
to delete the existing file that the program is trying to read.
ln -s /flag /home/hacker/not-the-flag
creating a symbolic link (symlink) at the same location, but making it point to the real flag.
/challenge/catflag
to get the flag.

```
hacker@commands~linking-files:~$ rm /home/hacker/not-the-flag
hacker@commands~linking-files:~$ ln -s /flag /home/hacker/not-the-flag
hacker@commands~linking-files:~$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{kw9GVI7_zXum2dDBXa3if_YjG5F.QX5ETN1wiMyAzNzEzW}
```

Flag:
> pwn.college{kw9GVI7_zXum2dDBXa3if_YjG5F.QX5ETN1wiMyAzNzEzW}

