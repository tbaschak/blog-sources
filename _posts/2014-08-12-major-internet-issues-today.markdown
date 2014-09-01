---
layout: post
title: "Major Internet Issues Today"
date: 2014-08-12 18:37:56 -0500
comments: false
categories: 
- BGP
- Networking
- ISP
- Network Monitoring
- System Administration
---
There has been a lot of noise in Canada about the widespread network issues Shaw was experiencing, and also a lot of speculation about what the cause of those issues were. Simultaneously, the number of IPv4 routes advertised in the global routing table went over 512k, triggering memory overflows and crashes for some providers who had their heads in the sand about this problem that has been well known since 2007.

<!--more-->

### Shaw Problems

I downed BGP with Shaw around 10am this morning. Connectivity into Shaw without Shaw BGP up seemed better than on Shaw's network itself. Epic Information Solutions turned up MTS Allstream BGP in place of Shaw around 4pm. 

The Shaw issues were so widespread that [The Register](http://www.theregister.co.uk/2014/08/12/nationwide_outage_at_canadian_isp_shaw/) reported "Canadian ISP Shaw stumbles around internet with mystery 'routing' sickness".

<img src='/images/2014-08-12-shaw-outages.png'>

(from [http://canadianoutages.com/status/shaw/map/](http://canadianoutages.com/status/shaw/map/))

### BGP Routes/Updates

I don't have a graph of the BGP updates from a Shaw peering session specifically, but I do have graphs for sessions with Hurricane Electric.

Global BGP Routes:

<img src='/images/2014-08-12-bgp-routes.png'>

BGP Updates:

<img src='/images/2014-08-12-bgp-update-spike.png'>

You can see the spike of updates around the time that the routes hit 510k (where I was monitoring at least). This caused some routers to crash, and generally not operate as intended. Prefixes were withdrawn, and came back, and there was a lot of churn in the global routing table at this time. The other spikes of updates were a result of emergency unscheduled/un-coordinated changes to reboot and increase limits by numerous providers with affected equipment.

