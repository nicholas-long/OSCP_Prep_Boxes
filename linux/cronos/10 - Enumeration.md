# nmap
```bash
└─$ rustscan -a $IP -- -A -sC -sV -Pn
.----. .-. .-. .----..---.  .----. .---.   .--.  .-. .-.
| {}  }| { } |{ {__ {_   _}{ {__  /  ___} / {} \ |  `| |
| .-. \| {_} |.-._} } | |  .-._} }\     }/  /\  \| |\  |
`-' `-'`-----'`----'  `-'  `----'  `---' `-'  `-'`-' `-'
The Modern Day Port Scanner.
________________________________________
: https://discord.gg/GFrQsGy           :
: https://github.com/RustScan/RustScan :
 --------------------------------------
🌍HACK THE PLANET🌍

[~] The config file is expected to be at "/home/coyote/.rustscan.toml"
[!] File limit is lower than default batch size. Consider upping with --ulimit. May cause harm to sensitive servers
[!] Your file limit is very small, which negatively impacts RustScan's speed. Use the Docker image, or up the Ulimit with '--ulimit 5000'. 
Open 10.129.30.241:22
Open 10.129.30.241:53
Open 10.129.30.241:80
[~] Starting Script(s)
[>] Script to be run Some("nmap -vvv -p {{port}} {{ip}}")

Host discovery disabled (-Pn). All addresses will be marked 'up' and scan times will be slower.
[~] Starting Nmap 7.91 ( https://nmap.org ) at 2021-06-10 15:29 CDT
NSE: Loaded 153 scripts for scanning.
NSE: Script Pre-scanning.
NSE: Starting runlevel 1 (of 3) scan.
Initiating NSE at 15:29
Completed NSE at 15:29, 0.00s elapsed
NSE: Starting runlevel 2 (of 3) scan.
Initiating NSE at 15:29
Completed NSE at 15:29, 0.00s elapsed
NSE: Starting runlevel 3 (of 3) scan.
Initiating NSE at 15:29
Completed NSE at 15:29, 0.00s elapsed
Initiating Parallel DNS resolution of 1 host. at 15:29
Completed Parallel DNS resolution of 1 host. at 15:29, 0.01s elapsed
DNS resolution of 1 IPs took 0.01s. Mode: Async [#: 1, OK: 0, NX: 1, DR: 0, SF: 0, TR: 1, CN: 0]
Initiating Connect Scan at 15:29
Scanning 10.129.30.241 [3 ports]
Discovered open port 22/tcp on 10.129.30.241
Discovered open port 80/tcp on 10.129.30.241
Discovered open port 53/tcp on 10.129.30.241
Completed Connect Scan at 15:29, 0.04s elapsed (3 total ports)
Initiating Service scan at 15:29
Scanning 3 services on 10.129.30.241
Completed Service scan at 15:30, 6.11s elapsed (3 services on 1 host)
NSE: Script scanning 10.129.30.241.
NSE: Starting runlevel 1 (of 3) scan.
Initiating NSE at 15:30
Completed NSE at 15:30, 8.31s elapsed
NSE: Starting runlevel 2 (of 3) scan.
Initiating NSE at 15:30
Completed NSE at 15:30, 0.20s elapsed
NSE: Starting runlevel 3 (of 3) scan.
Initiating NSE at 15:30
Completed NSE at 15:30, 0.00s elapsed
Nmap scan report for 10.129.30.241
Host is up, received user-set (0.044s latency).
Scanned at 2021-06-10 15:29:56 CDT for 15s

PORT   STATE SERVICE REASON  VERSION
22/tcp open  ssh     syn-ack OpenSSH 7.2p2 Ubuntu 4ubuntu2.1 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 18:b9:73:82:6f:26:c7:78:8f:1b:39:88:d8:02:ce:e8 (RSA)
| ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCkOUbDfxsLPWvII72vC7hU4sfLkKVEqyHRpvPWV2+5s2S4kH0rS25C/R+pyGIKHF9LGWTqTChmTbcRJLZE4cJCCOEoIyoeXUZWMYJCqV8crflHiVG7Zx3wdUJ4yb54G6NlS4CQFwChHEH9xHlqsJhkpkYEnmKc+CvMzCbn6CZn9KayOuHPy5NEqTRIHObjIEhbrz2ho8+bKP43fJpWFEx0bAzFFGzU0fMEt8Mj5j71JEpSws4GEgMycq4lQMuw8g6Acf4AqvGC5zqpf2VRID0BDi3gdD1vvX2d67QzHJTPA5wgCk/KzoIAovEwGqjIvWnTzXLL8TilZI6/PV8wPHzn
|   256 1a:e6:06:a6:05:0b:bb:41:92:b0:28:bf:7f:e5:96:3b (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBKWsTNMJT9n5sJr5U1iP8dcbkBrDMs4yp7RRAvuu10E6FmORRY/qrokZVNagS1SA9mC6eaxkgW6NBgBEggm3kfQ=
|   256 1a:0e:e7:ba:00:cc:02:01:04:cd:a3:a9:3f:5e:22:20 (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIHBIQsAL/XR/HGmUzGZgRJe/1lQvrFWnODXvxQ1Dc+Zx
53/tcp open  domain  syn-ack ISC BIND 9.10.3-P4 (Ubuntu Linux)
| dns-nsid: 
|_  bind.version: 9.10.3-P4-Ubuntu
80/tcp open  http    syn-ack Apache httpd 2.4.18 ((Ubuntu))
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-server-header: Apache/2.4.18 (Ubuntu)
|_http-title: Apache2 Ubuntu Default Page: It works
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel


```

# dns
* note: had to use box's original IP in 10.10.10.0/24 range, even though that isn't its IP now... shouldn't have these issues in the labs
```bash
└─$ dnsrecon -d asdf -n $IP -a -t rvl -r 10.10.10.1/24      
[*] Reverse Look-up of a Range
[*] Performing Reverse Lookup from 10.10.10.0 to 10.10.10.255
[+] PTR ns1.cronos.htb 10.10.10.13
[+] 1 Records Found
```
## hostnames
* cronos.htb
* ns1.cronos.htb
* admin.cronos.htb  ( [vhosts](#vhosts) enumeration )
 ![main_site.png](main_site.png)
 ![admin_site.png](admin_site.png)

# gobuster
```bash
└─$ gobuster dir -u http://cronos.htb/ -w /usr/share/seclists/Discovery/Web-Content/raft-medium-directories.txt -t 100
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://cronos.htb/
[+] Method:                  GET
[+] Threads:                 100
[+] Wordlist:                /usr/share/seclists/Discovery/Web-Content/raft-medium-directories.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2021/06/10 16:01:56 Starting gobuster in directory enumeration mode
===============================================================
/js                   (Status: 301) [Size: 305] [--> http://cronos.htb/js/]
/css                  (Status: 301) [Size: 306] [--> http://cronos.htb/css/]
/server-status        (Status: 403) [Size: 298]                             
Progress: 23268 / 30001 (77.56%)                                           [ERROR] 2021/06/10 16:02:14 [!] parse "http://cronos.htb/error\x1f_log": net/url: invalid control character in URL
                                                                            
===============================================================
2021/06/10 16:02:17 Finished
===============================================================

```

```bash
└─$ gobuster dir -u http://cronos.htb/ -w /usr/share/seclists/Discovery/Web-Content/raft-medium-files.txt -x php -t 100 -b 404,403
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://cronos.htb/
[+] Method:                  GET
[+] Threads:                 100
[+] Wordlist:                /usr/share/seclists/Discovery/Web-Content/raft-medium-files.txt
[+] Negative Status codes:   403,404
[+] User Agent:              gobuster/3.1.0
[+] Extensions:              php
[+] Timeout:                 10s
===============================================================
2021/06/10 16:02:52 Starting gobuster in directory enumeration mode
===============================================================
/index.php            (Status: 200) [Size: 2319]
/favicon.ico          (Status: 200) [Size: 0]   
/web.config           (Status: 200) [Size: 914] 
/robots.txt           (Status: 200) [Size: 24]  
                                                
===============================================================
2021/06/10 16:03:11 Finished
===============================================================
```

## vhosts 
```bash
└─$ gobuster vhost -u http://cronos.htb/ -w /usr/share/seclists/Discovery/DNS/subdomains-top1million-110000.txt -t 100
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:          http://cronos.htb/
[+] Method:       GET
[+] Threads:      100
[+] Wordlist:     /usr/share/seclists/Discovery/DNS/subdomains-top1million-110000.txt
[+] User Agent:   gobuster/3.1.0
[+] Timeout:      10s
===============================================================
2021/06/10 16:07:30 Starting gobuster in VHOST enumeration mode
===============================================================
Found: admin.cronos.htb (Status: 200) [Size: 2580]
                                                  
===============================================================
2021/06/10 16:08:54 Finished
===============================================================

```

## web.config
```xml
<configuration>
  <system.webServer>
    <rewrite>
      <rules>
        <rule name="Imported Rule 1" stopProcessing="true">
          <match url="^(.\*)/$" ignoreCase="false" />
          <conditions>
            <add input="{REQUEST\_FILENAME}" matchType="IsDirectory" ignoreCase="false" negate="true" />
          </conditions>
          <action type="Redirect" redirectType="Permanent" url="/{R:1}" />
        </rule>
        <rule name="Imported Rule 2" stopProcessing="true">
          <match url="^" ignoreCase="false" />
          <conditions>
            <add input="{REQUEST\_FILENAME}" matchType="IsDirectory" ignoreCase="false" negate="true" />
            <add input="{REQUEST\_FILENAME}" matchType="IsFile" ignoreCase="false" negate="true" />
          </conditions>
          <action type="Rewrite" url="index.php" />
        </rule>
      </rules>
    </rewrite>
  </system.webServer>
</configuration>
```

