# NetApp FAS6210
---
 
- [Introduction](#introduction)
- [Questions and Recommendations](#question-and-recommendation)
  - [HA Configuration](#ha-configuration)
  - [VLANs](#vlans)
  - [Trunks](#trucks)
  - [Storage Configuration](#storage-configuration)
  - [e0M Port](#e0m=port)
  - [Random Errors](#random-error)
  
<span id="introduction"></span>
## Introduction
The NetApp FAS6210 system is a High Availability (HA) pair of storage controllers that will eventually be used to address a majority of the college's storage needs. At this time the NetApp FAS6210 system has not been fully implemented, and is still being documented, and configured.

<span id="question-and-recommendation"></span>
## Questions and Recommendations

<span id="ha-configuration"></span>
#### HA Configuration

NetApp specifies four different possible HA configurations using their storage controllers. It is likely that we are configured as a "Standard HA Pair" or a "Mirrored HA pair" as the other two configurations deal more with multi-site HA. I need to figure out which HA pair configuration was intended for our system when it was setup. A Standard HA Pair seems yield more available storage over a Mirrored HA pair.

[Jonathan Windle](https://wikiwiki.bellevuecollege.edu/wiki/User:Jwindle) 15:08, 14 August 2012 (PDT)


#### From NetApp & Groupware meeting on 2012-10-10

We are configured as a Standard HA Pair.

[Jonathan Windle](https://wikiwiki.bellevuecollege.edu/wiki/User:Jwindle) 08:11, 11 October 2012 (PDT)
<span id="vlans"></span>
#### VLANs
All networks coming into the storage controllers are configured as untagged. It is my recommendation that all networks (if possible) are configured as tagged.

[Jonathan Windle](https://wikiwiki.bellevuecollege.edu/wiki/User:Jwindle) 15:08, 14 August 2012 (PDT)


From NetApp & Groupware meeting on 2012-10-10

There is no problem configuring interfaces as one large trunk and exposing the controllers to different networks via VLANs.

[Jonathan Windle](https://wikiwiki.bellevuecollege.edu/wiki/User:Jwindle) 08:11, 11 October 2012 (PDT)

<span id="trucks"></span>
#### Trunks
Recommend removing trunk configuration for the e0a and e0b interfaces and making them as invisible to the configuration as possible. These are 1GBit interfaces and should probably never be used.

Jonathan Windle 15:08, 14 August 2012 (PDT)

<span id="storage-configuration"></span>
##### Storage Configuration
It appears to me that currently the total available disks have been split in half between the two storage controllers creating four total disk pools (or as NetApp calls them "Aggreggates). This seems to me to add management overhead and complexity as I assume that we must manually decide which controller/disk-pool to host individual LUNs/Shares/Exports on.

[Jonathan Windle](https://wikiwiki.bellevuecollege.edu/wiki/User:Jwindle) 15:08, 14 August 2012 (PDT)


From NetApp & Groupware meeting on 2012-10-10

There are many benefits to having storage split between the controllers that outweighs the extra management overhead. Some of those benefits are active/active hardware, and more total IOPS being available.

[Jonathan Windle](https://wikiwiki.bellevuecollege.edu/wiki/User:Jwindle) 08:11, 11 October 2012 (PDT)

<span id="e0m=port"></span>
e0M Port
The e0M port is a 100Mbit eithernet port intended for hosting management services. NetApp's network documentation eludes to the fact that this port can be disabled and services can be hosted from high speed ports. More research is needed but I'm wondering at this point if we wouldn't be better off removing the e0M port from our configuration.

[Jonathan Windle](https://wikiwiki.bellevuecollege.edu/wiki/User:Jwindle) 15:08, 14 August 2012 (PDT)


##### From NetApp & Groupware meeting on 2012-10-10

There is no problem disabling the e0M port and not using it.

[Jonathan Windle](https://wikiwiki.bellevuecollege.edu/wiki/User:Jwindle) 08:11, 11 October 2012 (PDT)

<span id="random-error"></span>
##### Random Errors
Tue Aug 14 11:00:00 PDT [netapp2:raid.root.unmirrored:error]: Root volume is not mirrored. A takeover of this filer may not be possible in case of a disaster.


This is evidently a bug http://support.netapp.com/NOW/cgi-bin/bol?Type=Detail&Display=496375

[Jonathan Windle](https://wikiwiki.bellevuecollege.edu/wiki/User:Jwindle) 15:55, 15 August 2012 (PDT)