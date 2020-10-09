---
UID: NS:ntddndis._NDIS_LINK_SPEED
title: _NDIS_LINK_SPEED (ntddndis.h)
description: The NDIS_LINK_SPEED structure specifies transmit and receive link speeds.
old-location: netvista\ndis_link_speed.htm
tech.root: netvista
ms.assetid: d11155a3-b455-4c6e-83b8-7a86d8fd2aa1
ms.date: 05/02/2018
keywords: ["NDIS_LINK_SPEED structure"]
ms.keywords: "*PNDIS_LINK_SPEED, NDIS_LINK_SPEED, NDIS_LINK_SPEED structure [Network Drivers Starting with Windows Vista], PNDIS_LINK_SPEED, PNDIS_LINK_SPEED structure pointer [Network Drivers Starting with Windows Vista], _NDIS_LINK_SPEED, netvista.ndis_link_speed, ntddndis/NDIS_LINK_SPEED, ntddndis/PNDIS_LINK_SPEED, oid_structures_ref_c610b58c-eead-4483-96ab-c3fd62c1e846.xml"
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: 
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
targetos: Windows
req.typenames: NDIS_LINK_SPEED, *PNDIS_LINK_SPEED
f1_keywords:
 - _NDIS_LINK_SPEED
 - ntddndis/_NDIS_LINK_SPEED
 - PNDIS_LINK_SPEED
 - ntddndis/PNDIS_LINK_SPEED
 - NDIS_LINK_SPEED
 - ntddndis/NDIS_LINK_SPEED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - NDIS_LINK_SPEED
---

# _NDIS_LINK_SPEED structure


## -description

The NDIS_LINK_SPEED structure specifies transmit and receive link speeds.

## -struct-fields

### -field XmitLinkSpeed

The transmit link speed in bits per second. A value of -1 in this member indicates that the
     transmit link speed is unknown.

### -field RcvLinkSpeed

The receive link speed in bits per second. A value of -1 in this member indicates that the receive
     link speed is unknown.

## -remarks

The NDIS_LINK_SPEED structure specifies link speeds in the 
    <a href="/windows-hardware/drivers/network/oid-gen-link-speed-ex">OID_GEN_LINK_SPEED_EX</a> and 
    <a href="/windows-hardware/drivers/network/oid-gen-max-link-speed">OID_GEN_MAX_LINK_SPEED</a> OIDs.

## -see-also

<a href="/windows-hardware/drivers/network/oid-gen-link-speed-ex">OID_GEN_LINK_SPEED_EX</a>



<a href="/windows-hardware/drivers/network/oid-gen-max-link-speed">OID_GEN_MAX_LINK_SPEED</a>