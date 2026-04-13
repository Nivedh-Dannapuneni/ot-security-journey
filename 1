# Date: Apr 11

Tool: Nmap

Target: localhost
### Commands I ran
- nmap localhost
- nmap -sV localhost
- nmap -sV -p 502 localhost

### What I found
- Port 22: OpenSSH 9.7p1 — SSH server running
- Port 80: Apache 2.4.62 — web server running
- Port 502: closed — Modbus port reachable but no service listening

### Key learning: 
closed vs filtered — what it means for OT network segmentation
closed- Host is still up and port is reachable but no service is running to listen.
filtered- The port may be blocked by a firewall, or something between me and the host is dropping my packets. I can't confirm if the host is even up.
Port 502 closed on a PLC in a real OT network = dangerous, means it's reachable and unprotected even if nothing is running





# Date: Apr 12

Today I went deeper into IP addressing and subnetting, mapped out my actual home network using Nmap, and learned the different ways Nmap can scan a target. 
### Nmap scan types
Today I learned that there isn't just one way to scan — different 
scan types give different results and have different levels of 
visibility on the network.

### Default connect scan
Completes the full TCP 3-way handshake on every port. It works 
but it's loud — the target OS logs every connection. Not ideal 
when you're trying to stay quiet.

### SYN stealth scan (-sS)
This one is clever. Instead of completing the handshake, Nmap 
sends SYN, gets SYN-ACK back, then immediately sends RST to 
kill the connection before it fully establishes. The result is 
that many older systems and firewalls never log it because no 
full connection was made. Attackers use this specifically to 
map OT networks without triggering alerts on legacy devices.

```bash
sudo nmap -sS [target]
```

### UDP scan (-sU)
Everything I've done so far was TCP. But important services run 
on UDP too — DNS (53), DHCP (67), and most importantly SNMP (161). 
SNMP is huge in OT environments because it's used to manage and 
monitor devices, and if it's left open and unprotected it can 
leak the entire configuration of a device to anyone who queries it.

UDP scanning is slower because there's no handshake — Nmap has 
to guess port state from responses or silence:
- Open = service sends a UDP response
- Closed = ICMP port unreachable comes back
- Filtered = nothing — could be open or blocked, can't tell

```bash
sudo nmap -sU --top-ports 20 [target]
```

### Version detection (-sV)
Goes beyond finding open ports — actually probes the service to 
identify the exact software and version. That's how I identified 
Dropbear SSH 2022.83 on [DEVICE-1]. Once you have a version 
number you can look it up in CVE databases to find known 
vulnerabilities.

### OS detection (-O)
Nmap analyzes subtle differences in how packets are constructed 
— TTL values, TCP window sizes, timing — to fingerprint the 
operating system. Really useful for identifying unknown PLCs 
and HMIs when you're mapping an OT network and don't know 
what you're looking at.

### The combined analyst scan
When I want everything at once:
```bash
sudo nmap -sS -sV -O -T4 [target]
```
Stealth scan + version detection + OS fingerprinting at fast 
timing. This is how a real analyst approaches an unknown host.

### Biggest lesson today

I found a real high severity vulnerability on my own home network 
on day two. Telnet open on a router is something that would get 
flagged in any professional security audit. The fact that I found 
it by running a basic Nmap scan shows how much information is 
sitting in plain sight on networks that nobody has looked at.
