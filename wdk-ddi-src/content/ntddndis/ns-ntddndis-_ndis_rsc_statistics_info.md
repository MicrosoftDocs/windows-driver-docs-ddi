---
UID: NS:ntddndis._NDIS_RSC_STATISTICS_INFO
title: "_NDIS_RSC_STATISTICS_INFO"
author: windows-driver-content
description: The NDIS_RSC_STATISTICS_INFO structure contains statistics that a miniport driver supplies in response to a query of the OID_TCP_RSC_STATISTICS OID.
old-location: netvista\ndis_rsc_statistics_info.htm
old-project: netvista
ms.assetid: 14911610-f2d6-4ad4-884f-3137eab143be
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_RSC_STATISTICS_INFO, NDIS_RSC_STATISTICS_INFO, NDIS_RSC_STATISTICS_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_RSC_STATISTICS_INFO, PNDIS_RSC_STATISTICS_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RSC_STATISTICS_INFO, netvista.ndis_rsc_statistics_info, ntddndis/NDIS_RSC_STATISTICS_INFO, ntddndis/PNDIS_RSC_STATISTICS_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
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
-	Ntddndis.h
api_name:
-	NDIS_RSC_STATISTICS_INFO
product: Windows
targetos: Windows
req.typenames: NDIS_RSC_STATISTICS_INFO, *PNDIS_RSC_STATISTICS_INFO
---

# _NDIS_RSC_STATISTICS_INFO structure


## -description


The <b>NDIS_RSC_STATISTICS_INFO</b> structure contains statistics that  a miniport driver supplies in response to a query of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451929">OID_TCP_RSC_STATISTICS</a> OID. 


## -struct-fields




### -field Header

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the NDIS_RSC_STATISTICS_INFO structure. Set the <b>Type</b> member of the structure that <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT.

To specify the version of the <b>NDIS_RSC_STATISTICS_INFO</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_RSC_STATISTICS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_RSC_STATISTICS_REVISION_1.


### -field CoalescedPkts

The total  number of packets that were coalesced.


### -field CoalescedOctets

The total number of bytes that were coalesced.


### -field CoalesceEvents

The total number of coalescing events. That is, the total number of packets that were formed from coalescing packets.


### -field Aborts

The total number of RSC abort events. That is, the number of exceptions other than the IP datagram length being exceeded. This count should include the cases where a packet is not coalesced because of insufficient hardware  resources.
 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451929">OID_TCP_RSC_STATISTICS</a>
 

 

