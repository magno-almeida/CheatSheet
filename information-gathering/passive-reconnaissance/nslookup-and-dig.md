# nslookup and dig

## nslookup`  -  `Name Server Look Up

Find the IP address of a domain name using `nslookup:`

``

```
nslookup OPTIONS DOMAIN_NAME SERVER
nslookup -type=A tryhackme.com 1.1.1.1
nslookup -type=MX tryhackme.com
```

#### Options:

| Query type | Result             |
| ---------- | ------------------ |
| A          | IPv4 Addresses     |
| AAAA       | IPv6 Addresses     |
| CNAME      | Canonical Name     |
| MX         | Mail Servers       |
| SOA        | Start of Authority |
| TXT        | TXT Records        |



## dig



For more advanced DNS queries and additional functionality, you can use `dig`, the acronym for “Domain Information Groper,” if you are curious. Let’s use `dig` to look up the MX records and compare them to `nslookup`. We can use `dig DOMAIN_NAME`, but to specify the record type, we would use `dig DOMAIN_NAME TYPE`. Optionally, we can select the server we want to query using `dig @SERVER DOMAIN_NAME TYPE`.

* SERVER is the DNS server that you want to query.
* DOMAIN_NAME is the domain name you are looking up.
* TYPE contains the DNS record type, as shown in the table provided earlier.

```shell-session
user@TryHackMe$ dig tryhackme.com MX

; <<>> DiG 9.16.19-RH <<>> tryhackme.com MX
;; global options: +cmd
;; Got answer:
;; ->>HEADER<
```

A quick comparison between the output of `nslookup` and `dig` shows that `dig` returned more information, such as the TTL (Time To Live) by default. If you want to query a `1.1.1.1` DNS server, you can execute `dig @1.1.1.1 tryhackme.com MX`.
