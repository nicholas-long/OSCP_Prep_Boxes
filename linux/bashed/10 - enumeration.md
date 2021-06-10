# nmap
```bash
PORT   STATE SERVICE REASON  VERSION
80/tcp open  http    syn-ack Apache httpd 2.4.18 ((Ubuntu))
|_http-favicon: Unknown favicon MD5: 6AA5034A553DFA77C3B2C7B4C26CF870
| http-methods: 
|_  Supported Methods: POST OPTIONS GET HEAD
|_http-server-header: Apache/2.4.18 (Ubuntu)
|_http-title: Arrexel's Development Site

```

```bash
└─$ gobuster dir -u http://$IP/ -w /usr/share/seclists/Discovery/Web-Content/raft-medium-directories.txt -t 100                        
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.129.166.176/
[+] Method:                  GET
[+] Threads:                 100
[+] Wordlist:                /usr/share/seclists/Discovery/Web-Content/raft-medium-directories.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2021/06/10 00:10:40 Starting gobuster in directory enumeration mode
===============================================================
/dev                  (Status: 301) [Size: 314] [--> http://10.129.166.176/dev/]
/php                  (Status: 301) [Size: 314] [--> http://10.129.166.176/php/]
/fonts                (Status: 301) [Size: 316] [--> http://10.129.166.176/fonts/]
/css                  (Status: 301) [Size: 314] [--> http://10.129.166.176/css/]  
/js                   (Status: 301) [Size: 313] [--> http://10.129.166.176/js/]   
/images               (Status: 301) [Size: 317] [--> http://10.129.166.176/images/]
/uploads              (Status: 301) [Size: 318] [--> http://10.129.166.176/uploads/]
/server-status        (Status: 403) [Size: 302]                                     
Progress: 23735 / 30001 (79.11%)                                                   [ERROR] 2021/06/10 00:10:58 [!] parse "http://10.129.166.176/error\x1f_log": net/url: invalid control character in URL
                                                                                    
===============================================================
2021/06/10 00:11:01 Finished
===============================================================

```



![[Pasted image 20210610001147.png]]

![[Pasted image 20210610001349.png]]