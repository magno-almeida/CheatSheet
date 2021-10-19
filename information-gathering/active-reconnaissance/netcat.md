# Netcat

```
nc 10.10.27.43 PORT \\ Connect to IP/PORT
nc -lp 1234 \\ Open port 1234
nc -vnlp 1234 \\ Open port 1234 
```

| option | meaning                                                    |
| ------ | ---------------------------------------------------------- |
| -l     | Listen mode                                                |
| -p     | Specify the Port number                                    |
| -n     | Numeric only; no resolution of hostnames via DNS           |
| -v     | Verbose output (optional, yet useful to discover any bugs) |
| -vv    | Very Verbose (optional)                                    |
| -k     | Keep listening after client disconnects                    |



Notes:

* the option `-p` should appear just before the port number you want to listen on.
* the option `-n` will avoid DNS lookups and warnings.
* port numbers less than 1024 require root privileges to listen o
