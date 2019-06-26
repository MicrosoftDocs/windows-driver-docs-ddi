---
UID: NS:ntddndis._NDIS_PM_PACKET_PATTERN
title: _NDIS_PM_PACKET_PATTERN (ntddndis.h)
description: The NDIS_PM_PACKET_PATTERN structure specifies a wake-up pattern, which, when detected by a network adapter that has pattern-match enabled, causes the network adapter to signal a power-management wake-up event.
old-location: netvista\ndis_pm_packet_pattern.htm
tech.root: netvista
ms.assetid: dfda0b5f-06fc-4e94-b14c-6bd32c2c138a
ms.date: 05/02/2018
ms.keywords: "*PNDIS_PM_PACKET_PATTERN, 212pnpoid_bfc58374-2745-4c29-a2ac-b7ef864aa710.xml, NDIS_PM_PACKET_PATTERN, NDIS_PM_PACKET_PATTERN structure [Network Drivers Starting with Windows Vista], PNDIS_PM_PACKET_PATTERN, PNDIS_PM_PACKET_PATTERN structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PM_PACKET_PATTERN, netvista.ndis_pm_packet_pattern, ntddndis/NDIS_PM_PACKET_PATTERN, ntddndis/PNDIS_PM_PACKET_PATTERN"
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NDIS_PM_PACKET_PATTERN (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NDIS_PM_PACKET_PATTERN (NDIS   5.1)) in Windows XP.
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
- NDIS_PM_PACKET_PATTERN
product:
- Windows
targetos: Windows
req.typenames: NDIS_PM_PACKET_PATTERN, *PNDIS_PM_PACKET_PATTERN
---

# _NDIS_PM_PACKET_PATTERN structure


## -description


The NDIS_PM_PACKET_PATTERN structure specifies a wake-up pattern, which, when detected by a network adapter that
  has pattern-match enabled, causes the network adapter to signal a power-management wake-up event.


## -struct-fields




### -field Priority

This member is reserved.


### -field Reserved

This member is reserved.


### -field MaskSize

Specifies the size in bytes of the pattern mask that immediately follows the
     NDIS_PM_PACKET_PATTERN structure in the 
     <i>InformationBuffer</i>.


### -field PatternOffset

Specifies in bytes the offset from the beginning of the 
     <i>InformationBuffer</i> to the start of the wake-up pattern.


### -field PatternSize

Specifies in bytes the size of the wake-up pattern.


### -field PatternFlags

These flags are reserved.


## -remarks



NDIS_PM_PACKET_PATTERN is supplied in the 
    <i>InformationBuffer</i> of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure for following
    OIDs:

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-pnp-add-wake-up-pattern">OID_PNP_ADD_WAKE_UP_PATTERN</a>


A protocol driver sends this OID to a miniport driver to specify a wake-up pattern. The wake-up
      pattern, along with its mask, is described by an NDIS_PM_PACKET_PATTERN structure.

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-pnp-remove-wake-up-pattern">
       OID_PNP_REMOVE_WAKE_UP_PATTERN</a>


A protocol driver sends this OID to a miniport driver to delete a wake-up pattern that it previously
      specified with an OID_PNP_ADD_WAKE_UP_PATTERN request. The wake-up pattern, along with its mask, is
      described by an NDIS_PM_PACKET_PATTERN structure.

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-pnp-wake-up-pattern-list">OID_PNP_WAKE_UP_PATTERN_LIST</a>


A protocol uses this OID to request a list of the wake-up patterns currently set for the miniport
      driver's network adapter. Each wake-up pattern, along with its mask, is described by an NDIS_PM_PACKET_PATTERN
      structure.

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-pnp-add-wake-up-pattern">OID_PNP_ADD_WAKE_UP_PATTERN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-pnp-remove-wake-up-pattern">OID_PNP_REMOVE_WAKE_UP_PATTERN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-pnp-wake-up-pattern-list">OID_PNP_WAKE_UP_PATTERN_LIST</a>
 

 

