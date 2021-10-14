---
description: Web Information Gathering
---

# Hunting Subdomains

## DNSDumpster

{% embed url="https://dnsdumpster.com" %}
dns recon 
{% endembed %}

## Sublist3r

## Crt.sh

{% embed url="https://crt.sh" %}
Certificate fingerprinter
{% endembed %}

## AMASS

{% embed url="https://github.com/OWASP/Amass" %}



The amass tool and all the subcommands show options using the **'-h'** and **'-help'** flags:

```
amass -help
```

Check the version by performing the following:

```
amass -version
```

The most basic use of the tool for subdomain enumeration:

```
amass enum -d example.com
```

Typical parameters for DNS enumeration:

```
$ amass enum -v -src -ip -brute -min-for-recursive 2 -share -d example.com
[Google] www.example.com
[VirusTotal] ns.example.com
...
```

### Command-line Usage Information

The amass tool has several subcommands shown below for handling your Internet exposure investigation.

| Subcommand | Description                                                                    |
| ---------- | ------------------------------------------------------------------------------ |
| intel      | Collect open source intelligence for investigation of the target organization  |
| enum       | Perform DNS enumeration and network mapping of systems exposed to the Internet |
| viz        | Generate visualizations of enumerations for exploratory analysis               |
| track      | Compare results of enumerations against common target organizations            |
| db         | Manage the graph databases storing the enumeration results                     |

{% embed url="https://github.com/OWASP/Amass/blob/master/doc/user_guide.md" %}
user guide
{% endembed %}

## Manual Script
