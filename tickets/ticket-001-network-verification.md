# Ticket 001 - Network Verification

## Objective

Verify that the Windows 11 Help Desk Lab virtual machine has working network connectivity and DNS resolution.

## Environment

- Host: Dell OptiPlex 7060
- Hypervisor: Oracle VirtualBox
- Guest OS: Windows 11 Pro
- VM Memory: 6 GB
- VM CPUs: 4
- Virtual Disk: 80 GB
- Network Mode: NAT

## Investigation

### IP Configuration

Command:

```text
ipconfig
Result:
- IPv4 Address: 10.0.2.15
- Subnet Mask: 255.255.255.0
- Default Gateway: 10.0.2.2
```
Gateway Test

Command:
ping 10.0.2.2
```

Result:
- 4 packets sent
- 4 packets received
- 0% packet loss
### Internet Connectivity Test
Command:
```text

ping 8.8.8.8

Result:
- 4 packets sent
- 4 packets received
- 0% packet loss
- Average time: 22 ms
### DNS Test
Command:
ping google.com
```

Result:
- Google.com successfully resolved to an IP address
- 4 packets sent
- 4 packets received
- 0% packet loss
DNS Lookup
Command:
```
nslookup google.com
  
Result:
- DNS server: dns01.comcast.net
- DNS server address: 75.75.75.75
- Google.com successfully resolved to multiple IP addresses
Diagnosis
The virtual machine has a valid IPv4 configuration, can reach its default gateway, can reach an external IP address, and can resolve domain names through DNS.
Resolution
No network configuration changes were required. The VM was configured with NAT networking in VirtualBox, and connectivity and DNS resolution were verified successfully.
Verification
Network connectivity and DNS resolution were successfully confirmed using ipconfig, ping, and nslookup.
```
Skills Demonstrated
- Windows IP configuration
- IPv4 addressing
- Subnet masks
- Default gateways
- Network connectivity testing
- DNS troubleshooting
- ipconfig
- ping
- nslookup
- VirtualBox NAT networking
