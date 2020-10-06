---
UID: NS:ndis._NET_BUFFER_LIST_HEADER
title: _NET_BUFFER_LIST_HEADER (ndis.h)
description: The NET_BUFFER_LIST_HEADER defines header information for the NET_BUFFER_LIST structure.
old-location: netvista\net_buffer_list_header.htm
tech.root: netvista
ms.assetid: 49169618-c42d-4bae-b1df-1426059d60d7
ms.date: 05/02/2018
keywords: ["NET_BUFFER_LIST_HEADER structure"]
ms.keywords: "*PNET_BUFFER_LIST_HEADER, NET_BUFFER_LIST_HEADER, NET_BUFFER_LIST_HEADER union [Network Drivers Starting with Windows Vista], PNET_BUFFER_LIST_HEADER, PNET_BUFFER_LIST_HEADER union pointer [Network Drivers Starting with Windows Vista], _NET_BUFFER_LIST_HEADER, ndis/NET_BUFFER_LIST_HEADER, ndis/PNET_BUFFER_LIST_HEADER, ndis_netbuf_structures_ref_d7b08d29-e8af-4a7d-84bc-03c1885ee7e9.xml, netvista.net_buffer_list_header"
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
req.typenames: NET_BUFFER_LIST_HEADER, *PNET_BUFFER_LIST_HEADER
f1_keywords:
 - _NET_BUFFER_LIST_HEADER
 - ndis/_NET_BUFFER_LIST_HEADER
 - PNET_BUFFER_LIST_HEADER
 - ndis/PNET_BUFFER_LIST_HEADER
 - NET_BUFFER_LIST_HEADER
 - ndis/NET_BUFFER_LIST_HEADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NET_BUFFER_LIST_HEADER
---

# _NET_BUFFER_LIST_HEADER structure


## -description

The NET_BUFFER_LIST_HEADER defines header information for the 
  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure.

## -struct-fields

### -field NetBufferListData

A 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_data">NET_BUFFER_LIST_DATA</a> structure.

### -field Link

Reserved for NDIS.

## -remarks

NDIS maintains the information in the NET_BUFFER_LIST_HEADER union.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_data">NET_BUFFER_LIST_DATA</a>