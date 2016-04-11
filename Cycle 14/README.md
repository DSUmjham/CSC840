# Software Defined Radio

## General Information
* Author: Michael Ham
* Date: 4/11/2016
* Description: Radio waves are all around us, and many of them are transmitted in the clear.  By controlling a simple radio with software, we are able to tune into those frequencies and have some fun, gather information, and hack the communication between devices.

## Why You Should Care
There are so many wireless technologies in use today, and many of those protocols are terribly insecure.  We often times focus on traditional wireless security in the 802.1X specs, but there are many things outside of that.  Think about what radio waves are surrounding your right now.  You may be able to pick up AM/FM radio, narrow-band FM from weather stations, satellite imagery, aircraft tracking beacons, tire pressure monitoring systems (TPMS), doorbells, key fobs, cellular traffic, etc.  This stuff is everywhere! 

With the radio transmissions the we rely upon, they can reveal some interesting or undesirable things about us.  Sometimes small things like a garage door opener can be triggered, or possibly a wireless doorbell remotely rang.  In the case of something a little more serious like a TPMS sensor, this may reveal our location or whereabouts.  Cellular communication can be a source of sensitive information disclosure or even locate missing persons. 

By simply configuring a radio to tune into the correct frequencies, much of the information listed above is easily accessible.

## Three Main Ideas
1. Radio waves are all around us and many of the transmission technologies that use them are insecure.
2. Software defined radios allow us to tune into different frequencies eliminating the need for specialized hardware.
3. By tuning into radio signals, we may gather information or use what we have "heard" in certain replay attacks.

## Future Direction
This module focused on some simple things that can be done with SDRs.  A great topic of direction would be exploring the transmitting side of the radios and replaying information that you have captured.

OpenBTS is a cellular model built upon an open-source of software and software defined radios.  This enables operators to quickly stand up cellular networks and do many cool things.  

## Stream of Topics
Additional topics related to this type of attack may include some of the following:
* OpenBTS
* Replaying captured signals
* Decoding information received

## Additional Resources
* [Video Demonstration](https://youtu.be/C8bykbrprao)
* [Dangerous Prototypes](http://dangerousprototypes.com/tag/hackrf/)
* [FCC ID Device Lookup](https://fccid.io)
* [Getting Started with Software Defined Radio]()
* [OpenBTS](http://openbts.org) - Free book available!
* [rfcat](https://bitbucket.org/atlas0fd00m/rfcat)