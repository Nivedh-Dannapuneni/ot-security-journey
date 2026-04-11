# Date: Apr 11

Tool: Nmap

Target: localhost
## Commands I ran
- nmap localhost
- nmap -sV localhost
- nmap -sV -p 502 localhost

## What I found
- Port 22: OpenSSH 9.7p1 — SSH server running
- Port 80: Apache 2.4.62 — web server running
- Port 502: closed — Modbus port reachable but no service listening

## Key learning: 
closed vs filtered — what it means for OT network segmentation
closed- Host is still up and port is reachable but no service is running to listen.
filtered- The port may be blocked by a firewall, or something between me and the host is dropping my packets. I can't confirm if the host is even up.
Port 502 closed on a PLC in a real OT network = dangerous, means it's reachable and unprotected even if nothing is running
