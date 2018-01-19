---
UID: NS:windot11._DOT11_SUPPORTED_DSSS_CHANNEL
title: _DOT11_SUPPORTED_DSSS_CHANNEL
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_supported_dsss_channel.htm
old-project: netvista
ms.assetid: a8c3fe52-2e5f-4212-9b52-10240d1abb86
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DOT11_SUPPORTED_DSSS_CHANNEL, *PDOT11_SUPPORTED_DSSS_CHANNEL, DOT11_SUPPORTED_DSSS_CHANNEL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_SUPPORTED_DSSS_CHANNEL
req.alt-loc: windot11.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: *PDOT11_SUPPORTED_DSSS_CHANNEL, DOT11_SUPPORTED_DSSS_CHANNEL
req.product: Windows 10 or later.
---

# _DOT11_SUPPORTED_DSSS_CHANNEL structure



## -description

## -syntax

````
typedef struct _DOT11_SUPPORTED_DSSS_CHANNEL {
  ULONG uChannel;
} DOT11_SUPPORTED_DSSS_CHANNEL, *PDOT11_SUPPORTED_DSSS_CHANNEL;
````


## -struct-fields

### -field uChannel

A ULONG value, which represents a frequency channel that the 802.11 station can operate with.
     Valid channel numbers are as defined in 15.4.6.2 of 
     <i>IEEE Std. 802.11-1997</i> for the following PHY types:
     

<ul>
<li>
Direct-sequence spread spectrum (DSSS) PHY.

</li>
<li>
High-rate DSSS (HRDSSS) PHY.

</li>
<li>
Extended-rate PHY (ERP).

</li>
<li>
High-throughput (HT) 802.11n PHY when operating in the 2.4-GHz band.

</li>
</ul>

## -remarks


## -see-also
<dl>
<dt>
<a href="..\windot11\ns-windot11-_dot11_supported_dsss_channel_list.md">
   DOT11_SUPPORTED_DSSS_CHANNEL_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_SUPPORTED_DSSS_CHANNEL structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

