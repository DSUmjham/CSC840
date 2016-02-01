# BGP Path Prepending

## General Information
* Author: Michael Ham
* Date: 2/1/2016
* Description: An overview of BGP hijacking attacks in one of the most important protocols on the internet.  In this, path prepending is covered along with some BGP basics to set up future topics.

## Why You Should Care
The Border Gateway Protocol (BGP) is *the* public routing protocol used on the internet.  Everyone uses it, regardless if we think of it consciously or even heard of it to begin with.  As a result, you are (and probably have been) susceptible to the varying types of attacks performed against BGP routed networks.  

Whether you are a home user connecting to your ISP, or a large business/corporation such as YouTube, some of your internet traffic will pass through a device speaking the BGP protocol.  Most often, ISPs use this external routing protocol to exchange information about the networks they can reach with their peers.  Each of these entities is typically referred to as an Autonomous System (AS).  When you want to send traffic to a internet device residing in another AS, your traffic is routed there with BGP.

BGP is a path-decor routing protocol. This means that unlike some of its internal counterparts (EIGRP and OSPF), it doesn't necessarily care about speed or reliability, but rather the amount of ASes that the traffic has to travers.  The shorter the path, the better the route. Attackers have found a way to perform a legitimate act called "prepending" in a malicious way.  Prepending is a way for system administrators to force one path to be desired over another by extending the length of the AS path.  Attackers have used this same technique to make legitimate routes less desirable, and gain control of network traffic.

There are numerous documented attacks seen and some of which are very high profile.  Services like YouTube, Bitcoin mining operations, and even Internet for entire countries have been rerouted or wiped off of the map.  The worst part is, we really have no other alternatives at the current moment, so it's important to look at monitoring to react, but also keeping a open eye for ways to proactively mitigate these risks.  

## Three Main Ideas
1. Every person relies upon BGP at some point or another while connecting to remote internet devices.  BGP is *the* public routing protocol used on the Internet today.
2. Due to some flaws or vulnerabilities within the BGP specifications, attackers have been able to perform some very impactful attacks.  These entities range from single users up to nation states.
3. There really aren't any good alternatives to BGP at the moment, or at least none that are very practical.  We need to take a look at securing what we have and move our efforts into proactive defenses.

## Future Direction
This is a really huge topic and as you can probably see, we just hit the very tip of the iceberg.  The path prepending attack is just one example out of many in ways that adversaries and offensive security folks are taking advantage of the protocol we rely upon.  This may lead into the exploration of other attacks being seen, profiling some of the well documented attacks, and focusing on remediation efforts.

## Stream of Topics
Additional topics related to this type of attack may include some of the following:
* Sub-prefix hijacking attacks
* Route redistribution attacks
* RPKI for authorizing route updates
* The scale and current state of BGP vulnerabilities

## Additional Resources
* [Video Demonstration](https://youtu.be/SucGk2ZWxCs)
* [Arin - RPKI](https://www.arin.net/resources/rpki/)
* [BGPMon](http://www.bgpmon.net/)
* [BGPMon - The Canadian Bitcoin Hijack](http://www.bgpmon.net/the-canadian-bitcoin-hijack/)
* [CNET - Pakistan YouTube Attack](http://www.cnet.com/news/how-pakistan-knocked-youtube-offline-and-how-to-make-sure-it-never-happens-again/)
* [Evil Routers - Using AS path prepending to influence inbound routing](http://evilrouters.net/2009/03/07/using-as-path-prepending-to-influence-inbound-routing/)
* [Network Lessons - How to configure BGP AS Path Prepending](https://networklessons.com/bgp/how-to-configure-bgp-as-path-prepending/)
*[What Is My ASN](http://www.whatismyasn.org)

