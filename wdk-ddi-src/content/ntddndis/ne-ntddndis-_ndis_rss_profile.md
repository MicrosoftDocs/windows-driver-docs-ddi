---
UID: NE:ntddndis._NDIS_RSS_PROFILE
title: _NDIS_RSS_PROFILE (ntddndis.h)
description: This enumeration is not supported.
old-location: netvista\ndis_rss_profile.htm
tech.root: netvista
ms.assetid: 41A58C2C-8A25-41AC-9CBE-59AB38603A73
ms.date: 05/02/2018
ms.keywords: "*PNDIS_RSS_PROFILE, NDIS_RSS_PROFILE, NDIS_RSS_PROFILE enumeration [Network Drivers Starting with Windows Vista], NdisRssProfileClosest, NdisRssProfileClosestStatic, NdisRssProfileConservative, NdisRssProfileMaximum, NdisRssProfileNuma, NdisRssProfileNumaStatic, _NDIS_RSS_PROFILE, netvista.ndis_rss_profile, ntddndis/NDIS_RSS_PROFILE, ntddndis/NdisRssProfileClosest, ntddndis/NdisRssProfileClosestStatic, ntddndis/NdisRssProfileConservative, ntddndis/NdisRssProfileMaximum, ntddndis/NdisRssProfileNuma, ntddndis/NdisRssProfileNumaStatic"
ms.topic: enum
f1_keywords:
 - "ntddndis/NDIS_RSS_PROFILE"
req.header: ntddndis.h
req.include-header: Ntddndis.h, Ntddndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddndis.h
api_name:
- NDIS_RSS_PROFILE
product:
- Windows
targetos: Windows
req.typenames: NDIS_RSS_PROFILE, *PNDIS_RSS_PROFILE
---

# _NDIS_RSS_PROFILE enumeration


## -description


This enumeration is not supported.


## -enum-fields




### -field NdisRssProfileClosest

Default behavior is consistent with that of Windows Server 2008 R2.


### -field NdisRssProfileClosestStatic

No dynamic load balancing. Distribute but don't load-balance at runtime.


### -field NdisRssProfileNuma

Assign RSS CPUs on a round-robin basis across every NUMA node to enable applications that are running on NUMA servers to scale well.


### -field NdisRssProfileNumaStatic

RSS processor selection is the same as for NUMA scalability without dynamic load-balancing.


### -field NdisRssProfileConservative

RSS uses as few processors as possible to sustain the load. This option helps reduce the number of interrupts.


### -field NdisRssProfileMaximum

This enumeration  value is reserved. Do not use.


## -remarks



The <b>NDIS_RSS_PROFILE</b> enumeration type specifies the current  RSS load balancing profile.

NDIS network drivers use the <b>NDIS_RSS_PROFILE</b> enumeration type to set the value of the <b>RssProfile</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_rss_processor_info">NDIS_RSS_PROCESSOR_INFO</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_rss_processor_info">NDIS_RSS_PROCESSOR_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisgetrssprocessorinformation">
   NdisGetRssProcessorInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/standardized-inf-keywords-for-rss">Standardized INF Keywords for RSS</a>
 

 

