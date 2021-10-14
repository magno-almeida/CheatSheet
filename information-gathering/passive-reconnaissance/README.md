---
description: >-
  In passive reconnaissance, you rely on publicly available knowledge. It is the
  knowledge that you can access from publicly available resources without
  directly engaging with the target.
---

# Passive Reconnaissance

Passive reconnaissance activities include many activities, for instance:

* Looking up DNS records of a domain from a public DNS server.
* Checking job ads related to the target website.
* Reading news articles about the target company.
* `whois` to query WHOIS servers
* `nslookup` to query DNS servers
* `dig` to query DNS servers

## Summary

| Purpose                             | Commandline Example                       |
| ----------------------------------- | ----------------------------------------- |
| Lookup WHOIS record                 | `whois tryhackme.com`                     |
| Lookup DNS A records                | `nslookup -type=A tryhackme.com`          |
| Lookup DNS MX records at DNS server | `nslookup -type=MX tryhackme.com 1.1.1.1` |
| Lookup DNS TXT records              | `nslookup -type=TXT tryhackme.com`        |
| Lookup DNS A records                | `dig tryhackme.com A`                     |
| Lookup DNS MX records at DNS server | `dig @1.1.1.1 tryhackme.com MX`           |
| Lookup DNS TXT records              | `dig tryhackme.com TXT`                   |
