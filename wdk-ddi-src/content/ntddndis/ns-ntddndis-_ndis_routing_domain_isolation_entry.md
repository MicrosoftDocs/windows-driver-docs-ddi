---
UID: NS:ntddndis._NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY
title: "_NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY"
author: windows-driver-content
description: The NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY structure is used by the OID_GEN_ISOLATION_PARAMETERS OID to return information relating to a single isolation ID within a routing domain entry for a Hyper-V extensible switch network adapter's port.
old-location: netvista\ndis_routing_domain_isolation_entry.htm
old-project: netvista
ms.assetid: 4297097D-4796-4714-B51C-3F477ABAF1E6
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PNDIS_ROUTING_DOMAIN_ISOLATION_ENTRY, NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY, NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY structure [Network Drivers Starting with Windows Vista], PNDIS_ROUTING_DOMAIN_ISOLATION_ENTRY, PNDIS_ROUTING_DOMAIN_ISOLATION_ENTRY structure pointer [Network Drivers Starting with Windows Vista], _NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY, netvista.ndis_routing_domain_isolation_entry, ntddndis/NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY, ntddndis/PNDIS_ROUTING_DOMAIN_ISOLATION_ENTRY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.40 and later.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddndis.h
api_name:
-	NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY
product: Windows
targetos: Windows
req.typenames: NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY, *PNDIS_ROUTING_DOMAIN_ISOLATION_ENTRY
---

# _NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY structure


## -description


The <b>NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY</b> structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/dn383690">OID_GEN_ISOLATION_PARAMETERS</a> OID to return information relating to a single isolation ID within a routing domain entry for a Hyper-V extensible switch network adapter's port.


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY</b>  structure. This member is formatted as an <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to <b>NDIS_OBJECT_TYPE_DEFAULT</b>. To specify the version of the <b>NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value: 





#### NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY_REVISION_1

Original version for NDIS 6.40 and later.

Set the <b>Size</b> member to <b>NDIS_SIZEOF_NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY_REVISION_1</b>.


### -field Flags

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.




### -field IsolationIdName

An <a href="https://msdn.microsoft.com/library/windows/hardware/dn383678">NDIS_ISOLATION_NAME</a> structure that contains the isolation ID name for the Hyper-V extensible switch network adapter.


### -field VirtualSubnetId

 


### -field VlanId

 


### -field IsolationId

 




#### - ( unnamed union )

The default virtual switch port ID or virtual local area network (VLAN) ID that will be set on all sent or received packets if untagged packets are allowed. (See the <b>AllowUntaggedTraffic</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn383679">NDIS_ISOLATION_PARAMETERS</a> structure.)



#### VirtualSubnetId

The virtual switch port ID.



#### VlanId

The virtual local area network (VLAN) ID.



#### IsolationId

The default isolation ID that will be set on all sent or received packets if untagged packets are allowed. (See the <b>AllowUntaggedTraffic</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn383679">NDIS_ISOLATION_PARAMETERS</a> structure.)


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn383678">NDIS_ISOLATION_NAME</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn383685">NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY_GET_NEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn383690">OID_GEN_ISOLATION_PARAMETERS</a>
 

 

