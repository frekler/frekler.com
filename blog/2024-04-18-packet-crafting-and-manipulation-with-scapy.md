---
title: Packet crafting and manipulation with Scapy
description: The Post about packet crafting and manipulation with Scapy
slug: packet-crafting-and-manipulation-with-scapy
tags: [Scapy]
hide_table_of_contents: false
---

# Packet crafting and manipulation with Scapy

Packet crafting and manipulation with Scapy is a powerful technique that allows to simulate various types of network traffic and test the reliability and security of network infrastructure. With Python syntax and wide range of features, Scapy is a valuable tool for network administrators and security professionals.

<!-- truncate -->

:::danger[Disclaimer]
The content provided is for educational and informational purposes only.
I does not support or encourage any illegal.
:::

(This article is currently being supplemented)

Packet crafting is the process of manually creating network packets and sending them to a target network device or application. This technique is commonly used by network administrators and security professionals to test the reliability and security of network infrastructure.
By crafting custom packets, users can simulate various types of network traffic and test how network devices and applications respond to different network scenarios. Scapy provides an interface for crafting custom packets.
With Scapy can create, modify, and send packets using a Python syntax.

## Here are the basic steps for crafting a packet with Scapy:

### 1. Import the Scapy library

Before you can use Scapy, you need to import the library into your Python script.

```sh
from scapy.all import *
```

### 2. Create the packet

Once you have imported Scapy, you can start creating your custom packet.
Scapy provides a range of built-in packet types, including Ethernet, IP, TCP, UDP, and more.
Here's an example of creating an IP packet:

```sh
pkt = IP(dst="192.168.0.1")/TCP(dport=80, flags="S")
```

In this example, we are creating an IP packet with a destination address of 192.168.0.1 and a TCP segment with a destination port of 80 and the SYN flag set.

### 3. Send the packet

After you have created the packet, you can send it to the target network device or application using the send() method.

Here's an example:

```sh
send(pkt)
```

In this example, we are sending the packet we created in step 2 to its destination.

## Advanced packet crafting with Scapy

Scapy provides a wide range of features that allow for more advanced packet crafting.
Some of the most commonly used features include:

- Packet sniffing: Scapy can be used to capture and analyze network traffic, as well as to filter packets based on specific criteria.
- Packet manipulation: Scapy provides a range of tools for manipulating packet fields, including changing protocol headers, adding or removing fields, and more.
- Packet replay: Scapy can be used to replay previously captured packets, which is useful for testing network devices and applications under different conditions.
- Network scanning: Scapy can be used to scan for open ports and vulnerable services on target systems.


### Here are some more advanced examples of packet crafting with Scapy

#### Crafting an ICMP echo request packet

ICMP echo request packets, also known as ping packets, are used to test network connectivity. Here's an example of crafting an ICMP echo request packet with Scapy:

```sh
from scapy.all import *
pkt = IP(dst='192.168.0.1')/ICMP()
```

In this example, we are creating an IP packet with a destination address of 192.168.0.1 and an ICMP payload. The ICMP payload is left empty, which means that the packet is an ICMP echo request packet.

#### Crafting a DNS query packet

DNS query packets are used to resolve domain names to IP addresses. Here's an example of crafting a DNS query packet with Scapy:

```sh
from scapy.all import *
pkt = IP(dst="8.8.8.8")/UDP(dport=53)/DNS(rd=1,qd=DNSQR(qname="example.com"))
```
In this example, we are creating an IP packet with a destination address of 8.8.8.8 and a UDP payload with a destination port of 53 (the standard DNS port). The UDP payload contains a DNS query with a recursion desired flag set (rd=1) and a question section containing a DNS query for the domain "example.com".

#### Crafting a TCP SYN flood packet

TCP SYN flood is a common network attack where an attacker floods a target system with TCP SYN packets, which can overwhelm the system and cause a denial-of-service (DoS) condition. Here's an example of crafting a TCP SYN flood packet with Scapy:

```sh
from scapy.all import *
pkt = IP(dst="192.168.0.1")/TCP(dport=80, flags="S")
send(pkt, loop=1, inter=0.01)
```

In this example, we are creating an IP packet with a destination address of 192.168.0.1 and a TCP payload with a destination port of 80 and the SYN flag set. We are using the send() method with the loop and inter parameters to send the packet repeatedly with a small delay between each packet, which can simulate a TCP SYN flood attack.

#### Crafting a custom packet with Raw data

Scapy provides the ability to include raw data as a payload in a packet. Here is an example of crafting a custom packet with Raw data:

```sh
from scapy.all import *
pkt = IP(dst="192.168.0.1")/Raw(b"\x01\x02\x03\x04")
```

In this example, we are creating an IP packet with a destination address of 192.168.0.1 and a Raw payload containing the bytes "\x01\x02\x03\x04".

#### Crafting an IPv6 packet

Scapy supports the creation of IPv6 packets. Here is an example of crafting an IPv6 packet:

```sh
from scapy.all import *
pkt = IPv6(dst="2001:db8::1")/ICMPv6EchoRequest()
```

In this example, we are creating an IPv6 packet with a destination address of 2001:db8::1 and an ICMPv6 payload. The ICMPv6 payload is left empty, which means that the packet is an ICMPv6 echo request packet.

#### Crafting an SSH packet

Secure Shell (SSH) is a popular protocol for secure remote access and file transfer. Here's an example of crafting an SSH packet with Scapy:

```sh
from scapy.all import *
pkt = IP(dst="192.168.0.1")/TCP(dport=22)/Raw(b"SSH-2.0-OpenSSH_7.9p1 Ubuntu-10")
```

In this example, we are creating an IP packet with a destination address of 192.168.0.1 and a TCP payload with a destination port of 22 (the standard SSH port). The TCP payload contains a Raw payload with the SSH version string.

#### Crafting an HTTP request packet

Hypertext Transfer Protocol (HTTP) is the primary protocol used for transmitting data over the World Wide Web. Here's an example of crafting an HTTP request packet with Scapy:

```sh
from scapy.all import *
pkt = IP(dst="www.example.com")/TCP(dport=80)/Raw(b"GET /index.html HTTP/1.1\r\nHost: www.example.com\r\n\r\n")
```

In this example, we are creating an IP packet with a destination address of www.example.com and a TCP payload with a destination port of 80 (the standard HTTP port). The TCP payload contains a Raw payload with an HTTP GET request for the file /index.html.

#### Crafting an ARP packet

Address Resolution Protocol (ARP) is used to map a network address (such as an IP address) to a physical address (such as a MAC address). Here's an example of crafting an ARP packet with Scapy:

```sh
from scapy.all import *
pkt = Ether(dst="ff:ff:ff:ff:ff:ff")/ARP(op=1, pdst="192.168.0.1", hwdst="00:11:22:33:44:55")
```

In this example, we are creating an Ethernet packet with a destination address of ff:ff:ff:ff:ff:ff (the broadcast address) and an ARP payload. The ARP payload is a request (op=1) to map the IP address 192.168.0.1 to the MAC address 00:11:22:33:44:55.

#### Crafting a DHCP packet

Dynamic Host Configuration Protocol (DHCP) is used to assign IP addresses and other network configuration parameters to devices on a network. Here's an example of crafting a DHCP packet with Scapy:

```sh
from scapy.all import *
pkt = Ether(dst="ff:ff:ff:ff:ff:ff")/IP(src="0.0.0.0", dst="255.255.255.255")/UDP(sport=68, dport=67)/BOOTP(chaddr="00:11:22:33:44:55")/DHCP(options=[("message-type", "discover"), "end"])
```

In this example, we are creating an Ethernet packet with a destination address of ff:ff:ff:ff:ff:ff and an IP payload with a source address of 0.0.0.0 and a destination address of 255.255.255.255. The IP payload contains a UDP payload with a source port of 68 (the standard DHCP client port) and a destination port of 67 (the standard DHCP server port). The UDP payload contains a BOOTP payload with a client hardware address of 00:11:22:33:44:55 and a DHCP payload with a message type of "discover".

These are just a few examples of the advanced packet crafting capabilities provided by Scapy. With its extensive range of packet manipulation and analysis tools, Scapy is a powerful tool for testing network infrastructure and simulating network attacks.

By using Scapy to craft custom packets, users can gain a deeper understanding of how network devices and applications behave in different network scenarios, as well as identify potential vulnerabilities and security risks.
