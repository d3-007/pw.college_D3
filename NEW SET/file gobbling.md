# matching *
so you can reffer to files with just its 1st few letters and then *
the system will list all the similar looking files when ls ex* is used and similarly 
will cd into the sepecific directry if that is the sole name in the home file 
```
This challenge resets your working directory to /home/hacker unless you change 
directory properly...
hacker@globbing~matching-with-:~$ touch /challnge 
This challenge resets your working directory to /home/hacker unless you change 
directory properly...
touch: cannot touch '/challnge': Permission denied
This challenge resets your working directory to /home/hacker unless you change 
directory properly...
This challenge resets your working directory to /home/hacker unless you change 
directory properly...
hacker@globbing~matching-with-:~$ cd /ch*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{EbSZW-rv4E3uwlv5pllPm3tmEIP.QXxIDO0wiN2QDN3EzW}
```

# matching ?
? fills in a single character 
```
This challenge resets your working directory to /home/hacker unless you change 
directory properly...
This challenge resets your working directory to /home/hacker unless you change 
directory properly...
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{wCIo-4y_s2u0FFJAsPXj1evi79U.QXyIDO0wiN2QDN3EzW}
```
# matching with []
[] is used when a set files must be accessed together 
```
hacker@globbing~matching-with-:~$ cd /challenge/files 
hacker@globbing~matching-with-:/challenge/files$ /challenge/run/file_[bash]
bash: /challenge/run/file_[bash]: Not a directory
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[bash]
You got it! Here is your flag!
pwn.college{Ar5gxIZNPLOl7CLp0Us1iespscE.QXzIDO0wiN2QDN3EzW}
```

# Gloabing matching path with []
```
hacker@globbing~matching-paths-with-:~$ cd /challenge/files 
hacker@globbing~matching-paths-with-:/challenge/files$ /challenge/run ~/file_[bash]
Error: please run with a working directory of /home/hacker!
hacker@globbing~matching-paths-with-:/challenge/files$ /challenge/run home/hacker/file_
[bash]
Error: please run with a working directory of /home/hacker!
hacker@globbing~matching-paths-with-:/challenge/files$ /challenge/run file_[bash]
Error: please run with a working directory of /home/hacker!
hacker@globbing~matching-paths-with-:/challenge/files$ cd ~
hacker@globbing~matching-paths-with-:~$ /challenge/run file_[bash]
Error: you will need to specify the path to the files as part of your glob 
argument, since they are in a different directory than your current working 
directory!
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[bash]
You got it! Here is your flag!
pwn.college{cjVL2oxkL0ZsuZBYd6bZTfRtK44.QX0IDO0wiN2QDN3EzW}
```

# Multiple globs
```
hacker@globbing~multiple-globs:~$ cd /challenge/files 
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run *p*
You got it! Here is your flag!
pwn.college{oRq_o1dxATeqez3Yb2RpR5_dIWk.0lM3kjNxwiN2QDN3EzW}
```

# gloabing mixing challenge

*[abc] will find words that end with abc 
[abc]* will find words that start with abc 

```
hacker@globbing~mixing-globs:~$ cd /challenge/files 
hacker@globbing~mixing-globs:/challenge/files$ ls
amazing      educational  incredible  magical     queenly    uplifting   youthful
beautiful    fantastic    jovial      nice        radiant    victorious  zesty
challenging  great        kind        optimistic  splendid   wonderful
delightful   happy        laughing    pwning      thrilling  xenial
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run happy
Error: you did not use a square bracket glob...
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run *[cep]
Your expansion did not expand to the requested files (challenging, educational, 
pwning). Instead, it expanded to:
fantastic incredible nice optimistic
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [acr]*
Your expansion did not expand to the requested files (challenging, educational, 
pwning). Instead, it expanded to:
amazing challenging radiant
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [cep]*
You got it! Here is your flag!
pwn.college{UE5LjOZWnOvsph3WfaoCcip_cmq.QX1IDO0wiN2QDN3EzW}
```
# globbing exclusionary
! or ^ is used to explude files that u dont want to search in the bracket
```
hacker@globbing~exclusionary-globbing:~$ cd /challenge/files 
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [!pwn]
Your expansion did not expand to the requested files (amazing beautiful 
challenging delightful educational fantastic great happy incredible jovial kind 
laughing magical optimistic queenly radiant splendid thrilling uplifting 
victorious xenial youthful zesty).
Instead, it expanded to:
[!pwn]
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [!pwn]*
You got it! Here is your flag!
pwn.college{c5fTy2dcy1gEkZwSxEPb6FWvSNp.QX2IDO0wiN2QDN3EzW}
```

# globbing tab
syntax: file/name<tab_key_until_results_are_given>
in this challege i tried passing the absolute path but it was an error then i passed the file  
as an argument and got the flag
```
hacker@globbing~tab-completion:~$ cd /challenge/pwncollege
bash: cd: /challenge/pwncollege: No such file or directory
hacker@globbing~tab-completion:~$ cat /challenge/pwncollege​ 
.bash_history  .lesshst       h              tmp/
.config/       a              not-the-flag   
hacker@globbing~tab-completion:~$ cat /challenge/pwncollege​ not-the-flag
pwn.college{4xl0tK90zlbv2leeFu6r6FiMdxT.0FN0EzNxwiN2QDN3EzW}
cat: not-the-flag: Permission denied
```
# goblling mupltiple options 
```
hacker@globbing~multiple-options-for-tab-completion:~$ cd  /challenfe/files
bash: cd: /challenfe/files: No such file or directory
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ ls
No ls for you in this level! Use tab-completion instead!
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ /challenge/files/pwn
pwn                    pwn-the-planet         pwncollege-flamingo    pwncollege-hacking
pwn-college            pwncollege-family      pwncollege-flyswatter    
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ /challenge/files/pwn-college
/challenge/files/pwn-college: line 1: No: command not found
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ cat /challenge/files/pwn-co
llege
No flag in this file!
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ cat /challenge/files/pwncollege-hacking
No flag in this file!
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ cat /challenge/files/pwncollege-
pwncollege-family      pwncollege-flamingo    pwncollege-hacking     
pwncollege-flag        pwncollege-flyswatter  
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ cat /challenge/files/pwncollege-flag
pwn.college{8NribABPxlgzJmcWPzlNNq9F4nx.0lN0EzNxwiN2QDN3EzW}
```

# tab completion on command 
even commands can be completed with a tab but u need to be careful ig
```
hacker@globbing~tab-completion-on-commands:~$ pwncollege-28383 
Correct! Here is your flag:
pwn.college{EH4nv_X73bqCCYJkdcj1pful_Eh.0VN0EzNxwiN2QDN3EzW}
```
