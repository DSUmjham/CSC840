# BGP Sub Prefix Hijacking

## General Information
* Author: Michael Ham
* Date: 2/8/2016
* Description: BGP has so much impact on the way we navigate the internet.  Unfortunately, it is vulnerable to a wide spectrum of attacks.  This module will focus on one particular type of attack called sub-prefix hijacking.

## Why You Should Care
We've previously covered the idea that BGP is *the* protocol that is used on the public internet.  Whether you are traversing large autonomous systems or simply hoping between local ISPs, your traffic touches BGP.  In the state of things, many ASes prove to be vulnerable to BGP attacks.

In a sub-prefix hijacking attack, an attacker will take advantage of a couple of weaknesses/features of BGP.  

1. BGP does not validate the origin AS of an update message.  You may trust your peers, but you don't have much in the way of validating their peers.  
2. A BGP router can announce a prefix for a network that it doesn't even own.
3. A network may intentionally or maliciously announce a subnet of another network's prefix rather than the entire subnet.
4. When it is time for packet forwarding, the router is going to send the traffic the way of the smaller prefix.

The four points listed out above enable us to carry out a BGP sub-prefix hijacking attack.  This could carry over to several different scenarios such as a malicious BGP peer on the internet advertising that it owns a prefix that really belongs to a financial institution.  Any AS that would select the attackers route instead, would send their data to the wrong destination.  From there on out, it is up to the attacker to figure out what he/she wants to do with the information.  The impact could be as simple as discarding the traffic in a DoS or carrying out MITM attacks. 

## Three Main Ideas
1. As we've seen before, BGP is an integral part of everyday communication across the internet.  This module is focused on a small subset of how BGP trusts a more-specific prefix over a larger one.
2. BGP hijacks are a common occurrence on the internet and instigated by malicious intent or even simple accidents.  These types of events happen daily.
3. When taking a look at a very specific type of hijack such as sub-prefix hijacking, the problem gets a little bit smaller and easier to manage.

## Future Direction
As this module was focused on one type of BGP hijacking, future modules may include different types of attacks such as hijacking a supernet of a network.  IT is important to study the scale and impact such events and also weigh the effectiveness of current defenses.  As an attacker, we want to understand both sides of the equation, offensively and defensively evaluating BGP for viability in the use of directed attacks.

## Stream of Topics
Additional topics related to this type of attack may include some of the following:
* Route redistribution attacks
* RPKI for authorizing route updates
* The scale and current state of BGP vulnerabilities
* BGP supernet prefix hijacking

## Additional Resources
* [Video Demonstration](https://youtu.be/_zamsdMnUUo)
* [BGP Stream](https://bgpstream.com)
* [Cisco BGP Threat Mitigations](http://www.cisco.com/c/en/us/about/security-center/protecting-border-gateway-protocol.html#5)
* [Installing Loki on Kali](https://forums.kali.org/showthread.php?4768-Installing-loki-on-kali-linux-amd64&p=7914#post7914)
* [Loki Packages](https://c0decafe.de/svn/codename_loki/packages/kali-1/)
* [Protecting BGP from Invalid Paths](https://www.cs.unm.edu/~treport/tr/07-08/pgbgp-adversary.pdf)

