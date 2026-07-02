# Packet Capture and Network Traffic Analysis

## Overview

This project demonstrates the configuration of a VirtualBox home lab to capture and analyse network traffic using both Linux and Windows operating systems. Network interfaces were configured, conne[...]

---

## Objectives

The objectives of this project were to:

- Configure network settings in Linux and Windows.
- Explore network interfaces and IP configuration.
- Capture network traffic using **tcpdump**.
- Analyse captured packets using **Wireshark**.
- Develop a practical understanding of packet capture and network troubleshooting.

---

## Lab Environment

### Hypervisor

- Oracle VirtualBox

### Operating Systems

- Kali Linux
- Windows 10
- Ubuntu

### Tools Used

- Linux Terminal
- Windows PowerShell
- tcpdump
- Wireshark

---

## Part 1 – Network Configuration in Linux

Linux networking commands were used to explore the system's network configuration and verify communication between virtual machines.

### Viewing Network Interfaces

The `ip a` command was used to identify available network interfaces, including assigned IP addresses, MAC addresses and subnet information. This information was used to determine the active netwo[...]

![Network Interfaces](1.jpg)

---

### Hostname Resolution

The `/etc/hosts` file was modified to create a local hostname entry for the Windows virtual machine. This allowed communication using a hostname rather than an IP address, demonstrating how local [...]

![Hostname Resolution Setup](2.jpg)

![Hosts File Configuration](3.jpg)

---

### Connectivity Testing

Connectivity between the Kali Linux and Windows virtual machines was verified using ICMP echo requests (`ping`). Successful replies confirmed that hostname resolution and network communication wer[...]

![Ping Test 1](4.jpg)

![Ping Test 2](5.jpg)

![Ping Test 3](6.jpg)

---

## Part 2 – Capturing Traffic with tcpdump

Traffic capture was performed using **tcpdump** within the Kali Linux virtual machine.

### Listing Network Interfaces

Available capture interfaces were identified using:

```bash
tcpdump -D
```

![tcpdump Interface Listing](7.jpg)

This confirmed the available interfaces prior to beginning packet capture.

---

### Capturing Network Traffic

Traffic was captured on individual interfaces and across all interfaces using various tcpdump options.

Commands used included:

```bash
tcpdump -i eth0
```

![tcpdump eth0 Capture](8.jpg)

```bash
tcpdump -i any
```

![tcpdump Any Interface Capture](9.jpg)

```bash
tcpdump -i any -c 5
```

![tcpdump 5 Packet Limit](10.jpg)

These captures demonstrated how tcpdump can monitor live network traffic and limit captures to specific numbers of packets.

---

### Filtering Traffic

Traffic filtering was performed using host-based filters to isolate communications from specific devices.

Example:

```bash
tcpdump -i any host <IP_Address>
```

Additional filtering techniques using source, destination and logical operators were explored to reduce unnecessary traffic and focus packet analysis.

![tcpdump Filtering Example](28.jpg)

---

## Part 3 – Packet Analysis with Wireshark

Captured traffic was examined using Wireshark to better understand network communications between virtual machines.

Packet analysis included identifying common protocols such as:

- **ICMP** (Internet Control Message Protocol)
- **DNS** (Domain Name System)
- **TCP** (Transmission Control Protocol)

Wireshark provided detailed packet information including source and destination addresses, protocol types and packet contents, demonstrating how captured traffic can be analysed during network tr[...]

![Wireshark Packet Analysis 1](11.jpg)

![Wireshark Packet Analysis 2](12.jpg)

---

## Skills Demonstrated

- Linux network configuration
- Windows network configuration
- Packet capture techniques
- Packet filtering and analysis
- Wireshark packet analysis
- Network troubleshooting
- TCP/IP fundamentals
- DNS configuration
- Linux command-line administration
- Virtual machine networking

---

## Key Takeaways

This project provided practical experience configuring virtual machine networking, capturing live traffic and analysing network packets using industry-standard tools. Working with both **tcpdump*[...]

The ability to capture and analyze network traffic is fundamental to network security, incident response, and troubleshooting—critical skills for any cybersecurity professional.
