# STP Hijacking

## General Information
* Author: Michael Ham
* Date: 1/20/2016
* Description: This is a presentation that covers the basics of pwning the Data Link layer with STP hijacking using **yersinia** in Kali 2.0.

## Why You Should Care
As common practice, the majority of traffic in a given enterprise network traverses a switch at some port.  Switch ports exist in a single broadcast domain.  This means that if a host sends out a broadcast packet, the switch will forward the broadcast out every single port *except* the one that it received it on.  No problems there.  

Where the problem comes into place is that switch fabric is often redundant to provide for greater uptime and reliability.  When switches are redundantly linked (two or more cables interconnecting a set of switches), a loop may be introduced.  The result of a switching loop may be a broadcast storm in which broadcast traffic is continually forwarded between switches in the loop, eventually leading to a DoS.  To combat this, the Spanning Tree Protocol (STP) was introduced. 

Spanning tree is a protocol in which a root bridge (master switch) is elected within a network based off of its priority and MAC address.  This root bridge gathers information about all of the participants and the links they have in a network through Bridge Protocol Data Unit (BPDU) packets.  Once the root bridge has learned the network topology, it asks switches to disable specific ports that would cause switching loops.  

Since STP is enabled out of the box on Cisco devices, it is often left alone by administrators since it is functional and an essential part of the network.  This opens the possibility of an attacker taking over the root bridge role by sending malicious/unauthorized BPDU packets.   The result can be devastating depending on the attacker's internet, but typically leads to a DoS of some sort.

## Three Main Ideas
1. Switches are a huge part of most enterprise networks, and because of their role are often times connected via redundant links.  This may lead to broadcast storms, hence the need for STP.
2. Often times STP is not configured past the defaults which allows any device capable of sending a BPDU packet across the network to do so.  This can affect the root bridge election process and other STP dependencies.
3. By specially crafting BPDU packets, an attacker may assume the role of root bridge on the network and control port states or consume network resources resulting in a DoS.

## Future Direction
This topic could be further explored for determining the viability and vetting of defense mechanisms.  Cisco recommends that users implement BPDU Guard to mitigate such risks.  This attack may be a little stealthier in the context of intercepting a BPDU packet and using the information gained to become the root role.  A methodology for detecting such malicious packets would be quite interesting to review.

## Stream of Topics
Additional topics related to this type of network-based attack may include some of the following which Yersinia also has attacks written for:
* VLAN Trunking Protocol Attacks (VTP) 
* Cisco Discovery Protocol (CDP)
* IEEE 802.1X attacks
* Inter-Switch Link Protocol (ISL) 

## Additional Resources
* [Video Demonstration](https://youtu.be/EZriUy4qynM)
* [Broadcast Storm](http://www.omnisecu.com/cisco-certified-network-associate-ccna/what-is-broadcast-storm.php)
* [Cisco Attacking the Spanning Tree Protocol](http://www.ciscopress.com/articles/article.asp?p=1016582&seqNum=2)
* [Cisco Spanning Tree Walkthrough](http://www.cisco.com/image/gif/paws/10556/spanning_tree1.swf)
* [Spanning Tree Protocol](http://www.cisco.com/c/en/us/tech/lan-switching/spanning-tree-protocol/index.html)
* [Yersinia](http://www.yersinia.net)


