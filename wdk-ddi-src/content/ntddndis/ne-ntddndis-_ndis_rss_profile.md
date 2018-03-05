---
UID: NE:ntddndis._NDIS_RSS_PROFILE
title: "_NDIS_RSS_PROFILE"
author: windows-driver-content
description: This enumeration is not supported.
old-location: netvista\ndis_rss_profile.htm
old-project: netvista
ms.assetid: 41A58C2C-8A25-41AC-9CBE-59AB38603A73
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PNDIS_RSS_PROFILE, NDIS_RSS_PROFILE, NDIS_RSS_PROFILE enumeration [Network Drivers Starting with Windows Vista], NdisRssProfileClosest, NdisRssProfileClosestStatic, NdisRssProfileConservative, NdisRssProfileMaximum, NdisRssProfileNuma, NdisRssProfileNumaStatic, _NDIS_RSS_PROFILE, netvista.ndis_rss_profile, ntddndis/NDIS_RSS_PROFILE, ntddndis/NdisRssProfileClosest, ntddndis/NdisRssProfileClosestStatic, ntddndis/NdisRssProfileConservative, ntddndis/NdisRssProfileMaximum, ntddndis/NdisRssProfileNuma, ntddndis/NdisRssProfileNumaStatic"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddndis.h
api_name:
-	NDIS_RSS_PROFILE
product: Windows
targetos: Windows
req.typenames: NDIS_RSS_PROFILE, *PNDIS_RSS_PROFILE
---

# _NDIS_RSS_PROFILE enumeration


## -description


This enumeration is not supported.


## -syntax


````
typedef enum _NDIS_RSS_PROFILE { 
  NdisRssProfileClosest        = 1,
  NdisRssProfileClosestStatic,
  NdisRssProfileNuma,
  NdisRssProfileNumaStatic,
  NdisRssProfileConservative,
  NdisRssProfileMaximum
} NDIS_RSS_PROFILE;
````


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

NDIS network drivers use the <b>NDIS_RSS_PROFILE</b> enumeration type to set the value of the <b>RssProfile</b> member of the <a href="..\ntddndis\ns-ntddndis-_ndis_rss_processor_info.md">NDIS_RSS_PROCESSOR_INFO</a> structure.




## -see-also

<a href="..\ndis\nf-ndis-ndisgetrssprocessorinformation.md">
   NdisGetRssProcessorInformation</a>



<a href="https://msdn.microsoft.com/0ea0d6f7-0dc5-40dd-a706-4712e19dbfdb">Standardized INF Keywords for RSS</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_rss_processor_info.md">NDIS_RSS_PROCESSOR_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RSS_PROFILE enumeration%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

