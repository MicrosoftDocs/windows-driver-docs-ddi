---
UID: NS:ntddndis._NDIS_RSC_STATISTICS_INFO
title: _NDIS_RSC_STATISTICS_INFO
author: windows-driver-content
description: The NDIS_RSC_STATISTICS_INFO structure contains statistics that a miniport driver supplies in response to a query of the OID_TCP_RSC_STATISTICS OID.
old-location: netvista\ndis_rsc_statistics_info.htm
old-project: netvista
ms.assetid: 14911610-f2d6-4ad4-884f-3137eab143be
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_RSC_STATISTICS_INFO, NDIS_RSC_STATISTICS_INFO, *PNDIS_RSC_STATISTICS_INFO
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
req.alt-api: NDIS_RSC_STATISTICS_INFO
req.alt-loc: Ntddndis.h
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
req.typenames: NDIS_RSC_STATISTICS_INFO, *PNDIS_RSC_STATISTICS_INFO
---

# _NDIS_RSC_STATISTICS_INFO structure



## -description
The <b>NDIS_RSC_STATISTICS_INFO</b> structure contains statistics that  a miniport driver supplies in response to a query of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451929">OID_TCP_RSC_STATISTICS</a> OID. 



## -syntax

````
typedef struct _NDIS_RSC_STATISTICS_INFO {
  NDIS_OBJECT_HEADER Header;
  ULONG64            CoalescedPkts;
  ULONG64            CoalescedOctets;
  ULONG64            CoalesceEvents;
  ULONG64            Aborts;
} NDIS_RSC_STATISTICS_INFO, *PNDIS_RSC_STATISTICS_INFO;
````


## -struct-fields

### -field Header

The <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the NDIS_RSC_STATISTICS_INFO structure. Set the <b>Type</b> member of the structure that <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT.

To specify the version of the <b>NDIS_RSC_STATISTICS_INFO</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 




### -field NDIS_RSC_STATISTICS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_RSC_STATISTICS_REVISION_1.

</dd>
</dl>

### -field CoalescedPkts

The total  number of packets that were coalesced.


### -field CoalescedOctets

The total number of bytes that were coalesced.


### -field CoalesceEvents

The total number of coalescing events. That is, the total number of packets that were formed from coalescing packets.


### -field Aborts

The total number of RSC abort events. That is, the number of exceptions other than the IP datagram length being exceeded. This count should include the cases where a packet is not coalesced because of insufficient hardware  resources.
 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451929">OID_TCP_RSC_STATISTICS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RSC_STATISTICS_INFO structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

