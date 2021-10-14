---
description: Tips for Nmap
---

# Nmap

Sintax:

```
kali@kali#sudo nmap -sV -v -p- --min-rate=10000 10.10.10.5
kali@kali#sudo nmap -sC -sV 10.10.10.5 -Pn
kali@kali#sudo nmap -sC -sS -sV -vv -A -oN nmapscan 10.10.10.5
kali@kali#sudo nmap -T4 -p- -A 10.10.10.5
```

## Initial Scan

```
nmap -sS -A 10.10.10.10 
nmap -script vuln -p(open ports from the first scan)
```

## TCP Commands







