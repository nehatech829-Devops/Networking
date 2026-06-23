# Network Commands

This document explains commonly used Linux and Windows networking commands used for troubleshooting, monitoring, and network administration.

---

# Linux Commands

## 1. ip a

### Purpose

Displays all network interfaces and their IP addresses.

### Command

```bash
ip a
```

### What It Shows

* Interface names (eth0, ens33, wlan0)
* IPv4 addresses
* IPv6 addresses
* MAC addresses
* Interface status (UP/DOWN)

### Example Use

```bash
ip a
```

### Interview Question

**Q:** Which command is used to view IP addresses in Linux?

**A:** `ip a`

---

## 2. ip route

### Purpose

Displays the routing table.

### Command

```bash
ip route
```

### What It Shows

* Default gateway
* Destination networks
* Network routes
* Associated interfaces

### Example Output

```text
default via 192.168.1.1 dev ens33
192.168.1.0/24 dev ens33
```

### Interview Question

**Q:** How do you check the default gateway in Linux?

**A:** `ip route`

---

## 3. ping

### Purpose

Tests connectivity between devices.

### Command

```bash
ping google.com
```

### Uses

* Verify network connectivity
* Test internet access
* Measure latency
* Troubleshoot network issues

### Send Only 4 Packets

```bash
ping -c 4 google.com
```

---

## 4. traceroute

### Purpose

Shows the path packets take to reach a destination.

### Command

```bash
traceroute google.com
```

### Uses

* Identify routing problems
* Detect network delays
* Analyze packet paths

### Install on Ubuntu

```bash
sudo apt install traceroute
```

---

## 5. netstat

### Purpose

Displays network connections and listening ports.

### Command

```bash
netstat -tulnp
```

### Options

| Option | Description |
| ------ | ----------- |
| t      | TCP         |
| u      | UDP         |
| l      | Listening   |
| n      | Numeric     |
| p      | Process     |

### Example

```text
tcp 0 0 0.0.0.0:22 LISTEN
```

This indicates SSH is listening on Port 22.

---

## 6. ss

### Purpose

Modern replacement for netstat.

### Command

```bash
ss -tulnp
```

### Benefits

* Faster than netstat
* More detailed output
* Recommended on modern Linux systems

### Example

```text
tcp LISTEN 0 128 *:22
```

---

## 7. nslookup

### Purpose

Queries DNS servers and checks DNS resolution.

### Command

```bash
nslookup google.com
```

### Uses

* Verify DNS records
* Troubleshoot DNS issues
* Check domain resolution

### Example Output

```text
Name: google.com
Address: 142.250.x.x
```

---

## 8. dig

### Purpose

Advanced DNS lookup tool.

### Command

```bash
dig google.com
```

### Common Queries

Check MX Records:

```bash
dig google.com MX
```

Check Name Servers:

```bash
dig google.com NS
```

Check A Record:

```bash
dig google.com A
```

### Benefits

* Detailed DNS information
* Preferred by network administrators

---

# Windows Commands

## 1. ipconfig

### Purpose

Displays IP configuration details.

### Command

```cmd
ipconfig
```

### Useful Variants

Display Detailed Information:

```cmd
ipconfig /all
```

Release IP Address:

```cmd
ipconfig /release
```

Renew IP Address:

```cmd
ipconfig /renew
```

Flush DNS Cache:

```cmd
ipconfig /flushdns
```

### Uses

* View IP address
* Check subnet mask
* Verify gateway configuration

---

## 2. ping

### Purpose

Tests connectivity to another device.

### Command

```cmd
ping google.com
```

### Uses

* Verify internet access
* Test server reachability
* Measure response time

---

## 3. tracert

### Purpose

Windows version of traceroute.

### Command

```cmd
tracert google.com
```

### Uses

* Detect routing problems
* Identify network bottlenecks
* View packet path

---

## 4. nslookup

### Purpose

Checks DNS resolution.

### Command

```cmd
nslookup google.com
```

### Uses

* Verify DNS functionality
* Troubleshoot name resolution issues

---

## 5. netstat

### Purpose

Displays active connections and listening ports.

### Command

```cmd
netstat -ano
```

### Options

| Option | Description       |
| ------ | ----------------- |
| a      | All connections   |
| n      | Numeric addresses |
| o      | Process ID        |

### Uses

* Monitor active connections
* Identify open ports
* Find process IDs

---

## 6. arp -a

### Purpose

Displays the ARP table.

### Command

```cmd
arp -a
```

### ARP Stands For

Address Resolution Protocol

### What It Shows

* IP Address
* MAC Address Mapping

### Uses

* Troubleshoot LAN connectivity
* Verify MAC address mappings
* Inspect ARP cache

---

# Common Interview Questions

## What is the difference between ping and traceroute?

| Ping               | Traceroute                |
| ------------------ | ------------------------- |
| Tests connectivity | Shows packet path         |
| Measures latency   | Identifies routing issues |
| Uses ICMP Echo     | Uses multiple hops        |

---

## Why is ss preferred over netstat?

* Faster performance
* More detailed information
* Better support on modern Linux systems

---

## How do you check DNS resolution?

### Linux

```bash
nslookup google.com
```

or

```bash
dig google.com
```

### Windows

```cmd
nslookup google.com
```

---

## How do you check listening ports?

### Linux

```bash
ss -tulnp
```

### Windows

```cmd
netstat -ano
```

---

## Summary

These commands are essential for:

* Network Troubleshooting
* Linux Administration
* DevOps
* Cloud Computing
* System Administration
* Interview Preparation
