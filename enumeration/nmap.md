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

| Port Scan Type   | Example Command               |
| ---------------- | ----------------------------- |
| TCP Connect Scan | `nmap -sT 10.10.103.184`      |
| TCP SYN Scan     | `sudo nmap -sS 10.10.103.184` |
| UDP Scan         | `sudo nmap -sU 10.10.103.184` |

These scan types should get you started discovering running TCP and UDP services on a target host.

| Option                  | Purpose                                  |
| ----------------------- | ---------------------------------------- |
| `-p-`                   | all ports                                |
| `-p1-1023`              | scan ports 1 to 1023                     |
| `-F`                    | 100 most common ports                    |
| `-r`                    | scan ports in consecutive order          |
| `-T<0-5>`               | -T0 being the slowest and T5 the fastest |
| `--max-rate 50`         | rate <= 50 packets/sec                   |
| `--min-rate 15`         | rate >= 15 packets/sec                   |
| `--min-parallelism 100` | at least 100 probes in parallel          |



## Advanced Scans

| Port Scan Type                 | Example Command                                          |
| ------------------------------ | -------------------------------------------------------- |
| TCP Null Scan                  | `sudo nmap -sN 10.10.118.138`                            |
| TCP FIN Scan                   | `sudo nmap -sF 10.10.118.138`                            |
| TCP Xmas Scan                  | `sudo nmap -sX 10.10.118.138`                            |
| TCP Maimon Scan                | `sudo nmap -sM 10.10.118.138`                            |
| TCP ACK Scan                   | `sudo nmap -sA 10.10.118.138`                            |
| TCP Window Scan                | `sudo nmap -sW 10.10.118.138`                            |
| Custom TCP Scan                | `sudo nmap --scanflags URGACKPSHRSTSYNFIN 10.10.118.138` |
| Spoofed Source IP              | `sudo nmap -S SPOOFED_IP 10.10.118.138`                  |
| Spoofed MAC Address            | `--spoof-mac SPOOFED_MAC`                                |
| Decoy Scan                     | `nmap -D DECOY_IP,ME 10.10.118.138`                      |
| Idle (Zombie) Scan             | `sudo nmap -sI ZOMBIE_IP 10.10.118.138`                  |
| Fragment IP data into 8 bytes  | `-f`                                                     |
| Fragment IP data into 16 bytes | `-ff`                                                    |

| Option                   | Purpose                                  |
| ------------------------ | ---------------------------------------- |
| `--source-port PORT_NUM` | specify source port number               |
| `--data-length NUM`      | append random data to reach given length |

These scan types rely on setting TCP flags in unexpected ways to prompt ports for a reply. Null, FIN, and Xmas scan provoke a response from closed ports, while Maimon, ACK, and Window scans provoke a response from open and closed ports.

| Option     | Purpose                               |
| ---------- | ------------------------------------- |
| `--reason` | explains how Nmap made its conclusion |
| `-v`       | verbose                               |
| `-vv`      | very verbose                          |
| `-d`       | debugging                             |
| `-dd`      | more details for debugging            |

