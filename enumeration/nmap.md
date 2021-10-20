---
description: Tips for Nmap
---

# Nmap

### Sintax

```
kali@kali#sudo nmap -sV -v -p- --min-rate=10000 10.10.10.5
kali@kali#sudo nmap -sC -sV 10.10.10.5 -Pn
kali@kali#sudo nmap -sC -sS -sV -vv -A -oN nmapscan 10.10.10.5
kali@kali#sudo nmap -T4 -p- -A 10.10.10.5
```

### Types of Scan

* list: `MACHINE_IP scanme.nmap.org example.com` will scan 3 IP addresses.
* range: `10.11.12.15-20` will scan 6 IP addresses: `10.11.12.15`, `10.11.12.13.16`,… and `10.11.12.13.20`.
* subnet: `MACHINE_IP/30` will scan 4 IP addresses. (If this is ambiguous, you might want to join the [Networking](https://tryhackme.com/room/bpnetworking) room, although it is not critical to complete this module.)
* You can also provide a file as input for your list of targets, `nmap -iL list_of_hosts.txt`.

## Initial Scan

```
nmap -sS -A 10.10.10.10 
nmap -script vuln -p(open ports from the first scan)
```

## TCP Commands







