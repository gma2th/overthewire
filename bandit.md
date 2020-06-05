# Bandit

## Level 0 → Level 1

```bash
bandit0@bandit:~$ cat readme
boJ9jbbUNNfktd78OOpsqOltutMc3MY1
```

## Level 1 → Level 2

```bash
bandit1@bandit:~$ cat ./-
CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
```

## Level 2 → Level 3

```bash
bandit2@bandit:~$ cat spaces\ in\ this\ filename
UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
```

## Level 3 → Level 4

```bash
bandit3@bandit:~$ cat inhere/.hidden
pIwrPrtPN36QITSp3EQaw936yaFoFgAB
```

## Level 4 → Level 5

```bash
bandit4@bandit:~$ file inhere/*
inhere/-file00: data
inhere/-file01: data
inhere/-file02: data
inhere/-file03: data
inhere/-file04: data
inhere/-file05: data
inhere/-file06: data
inhere/-file07: ASCII text
inhere/-file08: data
inhere/-file09: data
bandit4@bandit:~$ cat inhere/-file07
koReBOKuIDDepwhWk7jZC0RTdopnAYKh
```

## Level 5 → Level 6

```bash
bandit5@bandit:~$ find inhere/ -size 1033c
inhere/maybehere07/.file2
bandit5@bandit:~$ cat inhere/maybehere07/.file2
DXjZPULLxYr17uwoI01bNLQbtFemEgo7
```

## Level 6 → Level 7

```bash
bandit6@bandit:~$ find / -user bandit7 -group bandit6 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs
```

## Level 7 → Level 8

```bash
bandit7@bandit:~$ cat data.txt | grep millionth
millionth	cvX2JJa4CFALtqS87jk27qwqGhBM9plV
```

## Level 8 → Level 9

```bash
bandit8@bandit:~$ cat data.txt | sort | uniq -u
UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR
```

## Level 9 → Level 10

```bash
bandit9@bandit:~$ strings data.txt | grep ==
========== the*2i"4
========== password
Z)========== is
&========== truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
```

## Level 10 → Level 11

```bash
bandit10@bandit:~$ cat data.txt | base64 -d
The password is IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR
```

## Level 11 → Level 12

```bash
bandit11@bandit:~$ cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
The password is 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu
```

## Level 12 → Level 13

```bash
bandit12@bandit:~$ mkdir /tmp/mg12/
bandit12@bandit:~$ xxd -r data.txt > /tmp/mg12/data
bandit12@bandit:~$ cd /tmpmg12/
bandit12@bandit:/tmp/mg12$ file data
data: gzip compressed data, was "data2.bin", last modified: Thu May  7 18:14:30 2020, max compression, from Unix
bandit12@bandit:/tmp/mg12$ mv data data.gz
bandit12@bandit:/tmp/mg12$ gzip -d data.gz
bandit12@bandit:/tmp/mg12$ file data
data: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/mg12$ mv data data.bz2
bandit12@bandit:/tmp/mg12$ bzip2 -d data.bz2
bandit12@bandit:/tmp/mg12$ file data
data: gzip compressed data, was "data4.bin", last modified: Thu May  7 18:14:30 2020, max compression, from Unix
bandit12@bandit:/tmp/mg12$ mv data data.gz
bandit12@bandit:/tmp/mg12$ gzip -d data.gz
bandit12@bandit:/tmp/mg12$ file data
data: POSIX tar archive (GNU)
bandit12@bandit:/tmp/mg12$ mv data data.tar
bandit12@bandit:/tmp/mg12$ tar xvf data.tar
data5.bin
bandit12@bandit:/tmp/mg12$ mv data5.bin data.tar
bandit12@bandit:/tmp/mg12$ tar xvf data.tar
data6.bin
bandit12@bandit:/tmp/mg12$ file data6.bin
data6.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/mg12$ mv data6.bin data.bz2
bandit12@bandit:/tmp/mg12$ bzip2 -d data.bz2
bandit12@bandit:/tmp/mg12$ file data
data: POSIX tar archive (GNU)
bandit12@bandit:/tmp/mg12$ mv data data.tar
bandit12@bandit:/tmp/mg12$ tar xvf data.tar
data8.bin
bandit12@bandit:/tmp/mg12$ tar xvf data.tar
data8.bin
bandit12@bandit:/tmp/mg12$ file data8.bin
data8.bin: gzip compressed data, was "data9.bin", last modified: Thu May  7 18:14:30 2020, max compression, from Unix
bandit12@bandit:/tmp/mg12$ mv data8.bin data.gz
bandit12@bandit:/tmp/mg12$ gzip -d data.gz
bandit12@bandit:/tmp/mg12$ file data
data: ASCII text
bandit12@bandit:/tmp/mg12$ cat data
The password is 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL
```

## Level 13 → Level 14

```bash
bandit13@bandit:~$ ssh bandit14@localhost -i sshkey.private
```

## Level 14 → Level 15

```bash
bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e
bandit14@bandit:~$ echo 4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e | nc localhost 30000
Correct!
BfMYroe26WYalil77FoDi9qh59eK5xNr
```

## Level 15 → Level 16

```bash
bandit15@bandit:~$ cat /etc/bandit_pass/bandit15
BfMYroe26WYalil77FoDi9qh59eK5xNr
bandit15@bandit:~$ echo BfMYroe26WYalil77FoDi9qh59eK5xNr | openssl s_client -connect localhost:30001 --quiet
depth=0 CN = localhost
verify error:num=18:self signed certificate
verify return:1
depth=0 CN = localhost
verify return:1
Correct!
```

## Level 16 → Level 17

```bash
bandit16@bandit:~$ nmap --script ssl-enum-ciphers -p 31000-32000 localhost

Starting Nmap 7.40 ( https://nmap.org ) at 2020-06-05 09:07 CEST
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00025s latency).
Not shown: 996 closed ports
PORT      STATE SERVICE
31046/tcp open  unknown
31518/tcp open  unknown
| ssl-enum-ciphers:
|   TLSv1.0:
|     ciphers:
|       TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_AES_128_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_AES_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_128_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_SEED_CBC_SHA (rsa 1024) - A
|     compressors:
|       NULL
|     cipher preference: client
|     warnings:
|       Weak certificate signature: SHA1
|   TLSv1.1:
|     ciphers:
|       TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_AES_128_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_AES_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_128_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_SEED_CBC_SHA (rsa 1024) - A
|     compressors:
|       NULL
|     cipher preference: client
|     warnings:
|       Weak certificate signature: SHA1
|   TLSv1.2:
|     ciphers:
|       TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_CAMELLIA_128_CBC_SHA256 (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_CAMELLIA_256_CBC_SHA384 (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_CHACHA20_POLY1305_SHA256 (rsa 1024) - A
|       TLS_RSA_WITH_AES_128_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_AES_128_CBC_SHA256 (rsa 1024) - A
|       TLS_RSA_WITH_AES_128_CCM (rsa 1024) - A
|       TLS_RSA_WITH_AES_128_CCM_8 (rsa 1024) - A
|       TLS_RSA_WITH_AES_128_GCM_SHA256 (rsa 1024) - A
|       TLS_RSA_WITH_AES_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_AES_256_CBC_SHA256 (rsa 1024) - A
|       TLS_RSA_WITH_AES_256_CCM (rsa 1024) - A
|       TLS_RSA_WITH_AES_256_CCM_8 (rsa 1024) - A
|       TLS_RSA_WITH_AES_256_GCM_SHA384 (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_128_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_128_CBC_SHA256 (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_256_CBC_SHA256 (rsa 1024) - A
|       TLS_RSA_WITH_SEED_CBC_SHA (rsa 1024) - A
|     compressors:
|       NULL
|     cipher preference: client
|     warnings:
|       Weak certificate signature: SHA1
|_  least strength: A
31691/tcp open  unknown
31790/tcp open  unknown
| ssl-enum-ciphers:
|   TLSv1.0:
|     ciphers:
|       TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_AES_128_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_AES_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_128_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_SEED_CBC_SHA (rsa 1024) - A
|     compressors:
|       NULL
|     cipher preference: client
|     warnings:
|       Weak certificate signature: SHA1
|   TLSv1.1:
|     ciphers:
|       TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_AES_128_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_AES_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_128_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_SEED_CBC_SHA (rsa 1024) - A
|     compressors:
|       NULL
|     cipher preference: client
|     warnings:
|       Weak certificate signature: SHA1
|   TLSv1.2:
|     ciphers:
|       TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_CAMELLIA_128_CBC_SHA256 (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_CAMELLIA_256_CBC_SHA384 (rsa 1024) - A
|       TLS_ECDHE_RSA_WITH_CHACHA20_POLY1305_SHA256 (rsa 1024) - A
|       TLS_RSA_WITH_AES_128_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_AES_128_CBC_SHA256 (rsa 1024) - A
|       TLS_RSA_WITH_AES_128_CCM (rsa 1024) - A
|       TLS_RSA_WITH_AES_128_CCM_8 (rsa 1024) - A
|       TLS_RSA_WITH_AES_128_GCM_SHA256 (rsa 1024) - A
|       TLS_RSA_WITH_AES_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_AES_256_CBC_SHA256 (rsa 1024) - A
|       TLS_RSA_WITH_AES_256_CCM (rsa 1024) - A
|       TLS_RSA_WITH_AES_256_CCM_8 (rsa 1024) - A
|       TLS_RSA_WITH_AES_256_GCM_SHA384 (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_128_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_128_CBC_SHA256 (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_256_CBC_SHA (rsa 1024) - A
|       TLS_RSA_WITH_CAMELLIA_256_CBC_SHA256 (rsa 1024) - A
|       TLS_RSA_WITH_SEED_CBC_SHA (rsa 1024) - A
|     compressors:
|       NULL
|     cipher preference: client
|     warnings:
|       Weak certificate signature: SHA1
|_  least strength: A
31960/tcp open  unknown

Nmap done: 1 IP address (1 host up) scanned in 1.44 seconds

bandit16@bandit:~$ echo cluFn7wTiGryunymYOu4RcffSxQluehd | openssl s_client -connect localhost:31790 -quiet
depth=0 CN = localhost
verify error:num=18:self signed certificate
verify return:1
depth=0 CN = localhost
verify return:1
Correct!
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----

bandit16@bandit:~$ vim /tmp/key
bandit16@bandit:~$ # Copy ssh key
bandit16@bandit:~$ chmod 600 /tmp/key
bandit16@bandit:~$ ssh bandit17@localhost -i /tmp/key
```

## Level 17 → Level 18

```bash
bandit17@bandit:~$ diff passwords.old passwords.new
42c42
< w0Yfolrc5bwjS4qw5mq1nnQi6mF03bii
---
> kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd
```

## Level 18 → Level 19

```bash
$ ssh bandit18@bandit.labs.overthewire.org -p 2220 "cat readme"
This is a OverTheWire game server. More information on http://www.overthewire.org/wargames

IueksS7Ubh8G3DCwVzrTd8rAVOwq3M5x
```

## Level 19 → Level 20

```bash
bandit19@bandit:~$ ./bandit20-do
Run a command as another user.
  Example: ./bandit20-do id
bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20
GbKksEFF4yrVs6il55v6gwY5aVje5f0j
```

## Level 20 → Level 21

```bash
bandit20@bandit:~$ echo GbKksEFF4yrVs6il55v6gwY5aVje5f0j | nc -l localhost -p 1234 &
[1] 24358
bandit20@bandit:~$ ./suconnect 1234
Read: GbKksEFF4yrVs6il55v6gwY5aVje5f0j
Password matches, sending next password
gE269g2h3mw3pwgrj0Ha9Uoqen1c9DGr
```

## Level 21 → Level 22

```bash
bandit21@bandit:~$ cat /etc/cron.d/cronjob_bandit22
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
bandit21@bandit:~$ cat /usr/bin/cronjob_bandit22.sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
bandit21@bandit:~$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
Yk7owGAcWjwMVRwrTesJEwB7WVOiILLI
```

## Level 22 → Level 23

```bash
bandit22@bandit:~$ cat /etc/cron.d/cronjob_bandit23
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
bandit22@bandit:~$ cat /usr/bin/cronjob_bandit23.sh
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget
bandit22@bandit:~$ echo I am user bandit23 | md5sum | cut -d ' ' -f 1
8ca319486bfbbc3663ea0fbe81326349
bandit22@bandit:~$ cat /tmp/8ca319486bfbbc3663ea0fbe81326349
jc1udXuA1tiHqjIsL8yaapX5XIAI6i0n
```

## Level 23 → Level 24

```bash
bandit23@bandit:~$ cat /etc/cron.d/cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:~$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname
echo "Executing and deleting all scripts in /var/spool/$myname:"
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

bandit23@bandit:~$ mkdir /tmp/mg23
bandit23@bandit:~$ cd /tmpmg23/
bandit23@bandit:/tmp/mg23$ echo "cat /etc/bandit_pass/bandit24 >> /tmp/mg23/pwd" > script.sh
bandit23@bandit:/tmp/mg23$ chmod -R 777 ./
bandit23@bandit:/tmp/mg23$ cp script.sh /var/spool/bandit24/
bandit23@bandit:/tmp/mg23$ cat pwd
UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ
```

## Level 24 → Level 25

```bash
bandit24@bandit:~$ for i in {0..10000} ; do echo UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ $i ; done | nc localhost 30002 | grep -v Wrong
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Correct!
The password of user bandit25 is uNG9O58gUE7snukf3bvZ0rxhtnjzSGzG

Exiting.
```

## Level 25 → Level 26

```bash
bandit25@bandit:~$ cat /etc/passwd | grep bandit26
bandit26:x:11026:11026:bandit level 26:/home/bandit26:/usr/bin/showtext
bandit25@bandit:~$ cat /usr/bin/showtext
#!/bin/sh

export TERM=linux

more ~/text.txt
exit 0
bandit25@bandit:~$ ssh -i bandit26.sshkey bandit26@localhost
v
:set shell=/bin/bash
:shell
```

## Level 26 → Level 27

```bash
bandit26@bandit:~$ ls
bandit27-do  text.txt
bandit26@bandit:~$ ./bandit27-do cat /etc/bandit_pass/bandit27
3ba3118a22e93127a4ed485be72ef5ea
```

## Level 27 → Level 28

```bash
bandit27@bandit:~$ mkdir /tmp/mg27
bandit27@bandit:~$ cd /tmp/mg27
bandit27@bandit:/tmp/mg27$ git clone ssh://bandit27-git@localhost/home/bandit27-git/repo
...
bandit27@bandit:/tmp/mg27$ cat repo/README
The password to the next level is: 0ef186ac70e04ea33b4c1853d2526fa2
```

## Level 28 → Level 29

```bash
bandit28@bandit:~$ mkdir /tmp/mg28
bandit28@bandit:~$ cd /tmp/mg28
bandit28@bandit:/tmp/mg28$ git clone  ssh://bandit28-git@localhost/home/bandit28-git/repo
...
bandit28@bandit:/tmp/mg28$ cd repo
bandit28@bandit:/tmp/mg28$ git log -p
...
-- password: bbc96594b4e001778eee9975372716b2
+- password: xxxxxxxxxx
...
```

## Level 29 → Level 30

```bash
bandit29@bandit:~$ mkdir /tmp/mg29
bandit29@bandit:~$ cd /tmp/mg29
bandit29@bandit:/tmp/mg29$ git clone ssh://bandit29-git@localhost/home/bandit29-git/repo
...
bandit29@bandit:/tmp/mg29$ cd repo/
bandit29@bandit:/tmp/mg29/repo$ git rev-list --all | xargs git grep password
bc833286fca18a3948aec989f7025e23ffc16c07:README.md:- password: 5b90576bedb2cc04c86a9e924ce42faf
...
```

## Level 30 → Level 31

```bash
bandit30@bandit:~$ mkdir /tmp/mg30
bandit30@bandit:~$ cd /tmp/mg30
bandit30@bandit:/tmp/mg30$ git clone ssh://bandit30-git@localhost/home/bandit30-git/repo
...
bandit30@bandit:/tmp/mg30/repo$ git log
...
bandit30@bandit:/tmp/mg30/repo$ git branch
* master
bandit30@bandit:/tmp/mg30/repo$ git tag
secret
bandit30@bandit:/tmp/mg30/repo$ git show secret
47e603bb428404d265f59c42920d81e5
```

## Level 31 → Level 32

```bash
bandit31@bandit:~$ mkdir /tmp/mg31
bandit31@bandit:~$ cd /tmp/mg31
bandit31@bandit:/tmp/mg31$ git clone ssh://bandit31-git@localhost/home/bandit31-git/repo
...
bandit31@bandit:/tmp/mg31$ cd repo/
bandit31@bandit:/tmp/mg31$ cat README.md
...
bandit31@bandit:/tmp/mg31/repo$ echo 'May I come in?' > key.txt
bandit31@bandit:/tmp/mg31/repo$ git add key.txt
The following paths are ignored by one of your .gitignore files:
key.txt
Use -f if you really want to add them.
bandit31@bandit:/tmp/mg31/repo$ git add -f key.txt
bandit31@bandit:/tmp/mg31/repo$ git commit -m "mg28"
bandit31@bandit:/tmp/mg31/repo$ git push
...
remote: Well done! Here is the password for the next level:
remote: 56a9bf19c63d650ce78e6ec0354ee45e
...
```

## Level 32 → Level 33

```bash
>> $0
$ cat /etc/bandit_pass/bandit33
c9c3199ddf4121b10cf581a98d51caee
```
