Date: Apr 11

Tool: Nmap

Target: localhost

Findings: SSH (OpenSSH 9.7), HTTP (Apache 2.4.62), Modbus port 502 closed

Key learning: closed vs filtered — what it means for OT network segmentation
closed- Host is still up and port is reachable but no service is running to listen.
filtered- The port may be blocked by a firewall, or something between me and the host is dropping my packets. I can't confirm if the host is even up.
