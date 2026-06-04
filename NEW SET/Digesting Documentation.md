# Learning from Documentation 
how to pass an argument 
```
hacker@man~learning-from-documentation:~$ cd /
hacker@man~learning-from-documentation:/$ ls -a
.  ..  .dockerenv  bin  boot  challenge  dev  etc  flag  home  lib  lib64  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@man~learning-from-documentation:/$ /challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{gyF7C4hLPy999dgYchzEiGHB2px.QX0ITO0wiN2QDN3EzW}

```

# learning complex usage 
how to pass an argument 
```
hacker@man~learning-complex-usage:~$ cd /
hacker@man~learning-complex-usage:/$ ls -a
.   .dockerenv  boot       dev  flag  lib    media  nix  proc  run   srv  tmp  var
..  bin         challenge  etc  home  lib64  mnt    opt  root  sbin  sys  usr
hacker@man~learning-complex-usage:/$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{09xDDBtf4SH4q_ffYDvajTxSqKc.QX1ITO0wiN2QDN3EzW}

```

# reading manuals 
man command retives the info on the linux cmd its like a manual 
```
hacker@man~reading-manuals:~$ cd /
hacker@man~reading-manuals:/$ man challenge 

CHALLENGE(1)         Challenge Commands         CHAL
LENGE(1)

NAME
       /challenge/challenge - print the flag!

SYNOPSIS
       challenge OPTION

DESCRIPTION
       Output the flag when called with the right arguments.

       --fortune
              read a fortune

       --version
              output version information and exit

       --sszwha NUM
              print the flag if NUM is 172

AUTHOR
       Written by Zardus.

REPORTING BUGS
hacker@man~reading-manuals:/$ /challenge/challenge --sszwha 172
Correct usage! Your flag: pwn.college{YsICszw1MJ7YhRaYuSLtQ2U66ga.QX0EDO0wiN2QDN3EzW}
```

# seaarching Manuals 
how to navigate a manual using keys
--nhck This argument will give you the flag! 903
```
hacker@man~searching-manuals:~$ man challenge 
hacker@man~searching-manuals:~$ man challenge 
hacker@man~searching-manuals:~$ /challenge/challenge --nhck
Initializing...
Correct usage! Your flag: pwn.college{QWoXWHEwOhYwb22rnEqU1KRpmFz.QX1EDO0wiN2QDN3EzW}

```
  
# Searchinf for manual 
solved using gemini, 
The documentation states that the -K or --global-apropos flag allows you to search for a specific text string across all manual pages by doing a brute-force search through their sources.
man man is sued to get more info
```
UYzfBnBRjbTmKHnwbrQJHx-I4t1.QX2EDO0wiN2QDN3EzW
--zfnjbm NUM
              print the flag if NUM is 412q
```
# helpful program 
help --help or --h is used when certain cmds are not there in the manual

```
hacker@man~helpful-programs:~$ cd /
hacker@man~helpful-programs:/$ /challenge/challenge --help
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]

options:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give you the flag
hacker@man~helpful-programs:/$ /challenge/challenge --give-the-flag GIVE_THE_FLAG
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]
a challenge to make you ask for help: error: argument -g/--give-the-flag: invalid int value: 'GIVE_THE_FLAG'
hacker@man~helpful-programs:/$ /challenge/challenge -g GIVE_THE_FLAG -p
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]
a challenge to make you ask for help: error: argument -g/--give-the-flag: invalid int value: 'GIVE_THE_FLAG'
hacker@man~helpful-programs:/$ /challenge/challenge -g -p
You passed -p as an argument to -g! Please read the usage
carefully: -g takes *its own* numerical argument.
hacker@man~helpful-programs:/$ /challenge/challenge -v -g -p
You passed -p as an argument to -g! Please read the usage
carefully: -g takes *its own* numerical argument.
hacker@man~helpful-programs:/$ /challenge/challenge -v
I'm exactly the version I need to be!
hacker@man~helpful-programs:/$ /challenge/challenge -p
The secret value is: 640
hacker@man~helpful-programs:/$ /challenge/challenge -g 640
Correct usage! Your flag: pwn.college{w6SvU4UOIbdJGY0zv6_bYIFTErI.QX3IDO0wiN2QDN3EzW}
```

# help for built in 
is is a built in help cmd 
syntax [ help cmd_as_arrgument ]
```
hacker@man~help-for-builtins:~$ help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!
    
    Options:
      --fortune         display a fortune
      --version         display the version
      --secret VALUE    prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "Q0HDr1B7".
hacker@man~help-for-builtins:~$ /challenge/challenge -secret Q0HDr1B7
bash: /challenge/challenge: No such file or directory
hacker@man~help-for-builtins:~$ challenge -secret Q0HDr1B7
Incorrect usage! Please read the help page for the challenge builtin!
hacker@man~help-for-builtins:~$ challenge --secret Q0HDr1B7
Correct! Here is your flag!
pwn.college{Q0HDr1B7R8-6xqqE19CEFWix2Y5.QX0ETO0wiN2QDN3EzW}
```
