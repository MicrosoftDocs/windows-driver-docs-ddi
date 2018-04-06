---
UID: NE:ntddndis._NDIS_ARP_HEADER_FIELD
title: "_NDIS_ARP_HEADER_FIELD"
author: windows-driver-content
description: The NDIS_ARP_HEADER_FIELD enumeration identifies the type of a field in an Address Resolution Protocol (ARP) header.
old-location: netvista\ndis_arp_header_field.htm
old-project: netvista
ms.assetid: 63DA6329-C673-48A0-8E36-67035E2DB4C9
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_ARP_HEADER_FIELD, NDIS_ARP_HEADER_FIELD, NDIS_ARP_HEADER_FIELD enumeration [Network Drivers Starting with Windows Vista], NdisARPHeaderFieldMaximum, NdisARPHeaderFieldOperation, NdisARPHeaderFieldSPA, NdisARPHeaderFieldTPA, NdisARPHeaderFieldUndefined, PNDIS_ARP_HEADER_FIELD, PNDIS_ARP_HEADER_FIELD enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_ARP_HEADER_FIELD, netvista.ndis_arp_header_field, ntddndis/NDIS_ARP_HEADER_FIELD, ntddndis/NdisARPHeaderFieldMaximum, ntddndis/NdisARPHeaderFieldOperation, ntddndis/NdisARPHeaderFieldSPA, ntddndis/NdisARPHeaderFieldTPA, ntddndis/NdisARPHeaderFieldUndefined, ntddndis/PNDIS_ARP_HEADER_FIELD"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	NDIS_ARP_HEADER_FIELD
product:
- Windows
targetos: Windows
req.typenames: NDIS_ARP_HEADER_FIELD, *PNDIS_ARP_HEADER_FIELD
---

# _NDIS_ARP_HEADER_FIELD enumeration


## -description


The <b>NDIS_ARP_HEADER_FIELD</b> enumeration identifies the type of a field in an Address Resolution Protocol (ARP) header.


## -enum-fields




### -field NdisARPHeaderFieldUndefined

An undefined ARP header field.


### -field NdisARPHeaderFieldOperation

The ARP operation field.


### -field NdisARPHeaderFieldSPA

The ARP source protocol address (SPA) field.


### -field NdisARPHeaderFieldTPA

The ARP target protocol address (TPA) field.


### -field NdisARPHeaderFieldMaximum

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks



The <b>NDIS_ARP_HEADER_FIELD</b> enumeration is used in the 
    <a href="https://msdn.microsoft.com/3d387fe9-a7cc-4034-b31e-ba1359db2ae1">
    NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/3d387fe9-a7cc-4034-b31e-ba1359db2ae1">
   NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a>
 

 

