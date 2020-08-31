---
UID: NS:ndis._NET_BUFFER_HEADER
title: _NET_BUFFER_HEADER (ndis.h)
description: The NET_BUFFER_HEADER structure specifies header information for the NET_BUFFER structure.
old-location: netvista\net_buffer_header.htm
tech.root: netvista
ms.assetid: db7277d0-9671-4680-84d4-d3415ce3922f
ms.date: 05/02/2018
keywords: ["NET_BUFFER_HEADER structure"]
ms.keywords: "*PNET_BUFFER_HEADER, NET_BUFFER_HEADER, NET_BUFFER_HEADER union [Network Drivers Starting with Windows Vista], PNET_BUFFER_HEADER, PNET_BUFFER_HEADER union pointer [Network Drivers Starting with Windows Vista], _NET_BUFFER_HEADER, ndis/NET_BUFFER_HEADER, ndis/PNET_BUFFER_HEADER, ndis_netbuf_structures_ref_a19368c6-0bef-4fe6-be52-d76e0c6ea99d.xml, netvista.net_buffer_header"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.typenames: NET_BUFFER_HEADER, *PNET_BUFFER_HEADER
f1_keywords:
 - _NET_BUFFER_HEADER
 - ndis/_NET_BUFFER_HEADER
 - PNET_BUFFER_HEADER
 - ndis/PNET_BUFFER_HEADER
 - NET_BUFFER_HEADER
 - ndis/NET_BUFFER_HEADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NET_BUFFER_HEADER
---

# _NET_BUFFER_HEADER structure


## -description

The NET_BUFFER_HEADER structure specifies header information for the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure.

## -struct-fields

### -field NetBufferData

A 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_data">NET_BUFFER_DATA</a> structure.

### -field Link

Reserved for NDIS.

## -remarks

NDIS maintains the information in the NET_BUFFER_HEADER union.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_data">NET_BUFFER_DATA</a>

