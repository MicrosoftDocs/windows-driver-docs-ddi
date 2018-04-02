---
UID: NE:ntddndis._NDIS_PM_PROTOCOL_OFFLOAD_TYPE
title: "_NDIS_PM_PROTOCOL_OFFLOAD_TYPE"
author: windows-driver-content
description: The NDIS_PM_PROTOCOL_OFFLOAD_TYPE enumeration identifies the type of a protocol offload for NDIS network adapter power management.
old-location: netvista\ndis_pm_protocol_offload_type.htm
old-project: netvista
ms.assetid: ab9f98d3-1792-43be-b838-f9dd3953889c
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_PM_PROTOCOL_OFFLOAD_TYPE, NDIS_PM_PROTOCOL_OFFLOAD_TYPE, NDIS_PM_PROTOCOL_OFFLOAD_TYPE enumeration [Network Drivers Starting with Windows Vista], NdisPMProtocolOffload80211RSNRekey, NdisPMProtocolOffloadIdIPv4ARP, NdisPMProtocolOffloadIdIPv6NS, NdisPMProtocolOffloadIdMaximum, NdisPMProtocolOffloadIdUnspecified, PNDIS_PM_PROTOCOL_OFFLOAD_TYPE, PNDIS_PM_PROTOCOL_OFFLOAD_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_PM_PROTOCOL_OFFLOAD_TYPE, miniport_power_management_ref_5fcdc741-9efa-48ff-8b03-017859bf80c0.xml, netvista.ndis_pm_protocol_offload_type, ntddndis/NDIS_PM_PROTOCOL_OFFLOAD_TYPE, ntddndis/NdisPMProtocolOffload80211RSNRekey, ntddndis/NdisPMProtocolOffloadIdIPv4ARP, ntddndis/NdisPMProtocolOffloadIdIPv6NS, ntddndis/NdisPMProtocolOffloadIdMaximum, ntddndis/NdisPMProtocolOffloadIdUnspecified, ntddndis/PNDIS_PM_PROTOCOL_OFFLOAD_TYPE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddndis.h
req.include-header: Ntddndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
-	NDIS_PM_PROTOCOL_OFFLOAD_TYPE
product:
- Windows
targetos: Windows
req.typenames: NDIS_PM_PROTOCOL_OFFLOAD_TYPE, *PNDIS_PM_PROTOCOL_OFFLOAD_TYPE
---

# _NDIS_PM_PROTOCOL_OFFLOAD_TYPE enumeration


## -description


The <b>NDIS_PM_PROTOCOL_OFFLOAD_TYPE</b> enumeration identifies the type of a protocol offload for NDIS
  network adapter power management.


## -enum-fields




### -field NdisPMProtocolOffloadIdUnspecified

The offloaded protocol is not specified.


### -field NdisPMProtocolOffloadIdIPv4ARP

An IPv4 ARP protocol offload. The parameters for this protocol offload type are specified in the 
     <b>IPv4ARPParameters</b> member of the 
     <a href="https://msdn.microsoft.com/1ae68e5c-f9ea-4454-b015-82e3af0f7ccd">
     NDIS_PM_PROTOCOL_OFFLOAD</a> structure.


### -field NdisPMProtocolOffloadIdIPv6NS

An IPv6 Neighbor Solicitation (NS) protocol offload. The parameters for this protocol offload type
     are specified in the 
     <b>IPv6NSParameters</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566760">NDIS_PM_PROTOCOL_OFFLOAD</a> structure.


### -field NdisPMProtocolOffload80211RSNRekey

An IEEE 802.11i Robust Security Network (RSN) 4-way and 2-way handshake protocol offload. This
     protocol offload type is specified in the 
     <b>Dot11RSNRekeyParameters</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566760">NDIS_PM_PROTOCOL_OFFLOAD</a> structure.


### -field NdisPMProtocolOffloadIdMaximum

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks



The <b>NDIS_PM_PROTOCOL_OFFLOAD_TYPE</b> enumeration is used in the 
    <b>ProtocolOffloadType</b> member of the 
    <a href="https://msdn.microsoft.com/1ae68e5c-f9ea-4454-b015-82e3af0f7ccd">
    NDIS_PM_PROTOCOL_OFFLOAD</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566760">NDIS_PM_PROTOCOL_OFFLOAD</a>
 

 

