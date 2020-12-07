---
UID: NS:ndis._NET_BUFFER_LIST_DATA
title: _NET_BUFFER_LIST_DATA (ndis.h)
description: The NET_BUFFER_LIST_DATA structure contains management data for the NET_BUFFER structures that are linked to a NET_BUFFER_LIST structure.
old-location: netvista\net_buffer_list_data.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NET_BUFFER_LIST_DATA structure"]
ms.keywords: "*PNET_BUFFER_LIST_DATA, NET_BUFFER_LIST_DATA, NET_BUFFER_LIST_DATA structure [Network Drivers Starting with Windows Vista], PNET_BUFFER_LIST_DATA, PNET_BUFFER_LIST_DATA structure pointer [Network Drivers Starting with Windows Vista], _NET_BUFFER_LIST_DATA, ndis/NET_BUFFER_LIST_DATA, ndis/PNET_BUFFER_LIST_DATA, ndis_netbuf_structures_ref_1ce577dd-1eec-4ba6-94cb-3e37c205630d.xml, netvista.net_buffer_list_data"
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
req.typenames: NET_BUFFER_LIST_DATA, *PNET_BUFFER_LIST_DATA
f1_keywords:
 - _NET_BUFFER_LIST_DATA
 - ndis/_NET_BUFFER_LIST_DATA
 - PNET_BUFFER_LIST_DATA
 - ndis/PNET_BUFFER_LIST_DATA
 - NET_BUFFER_LIST_DATA
 - ndis/NET_BUFFER_LIST_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NET_BUFFER_LIST_DATA
---

# _NET_BUFFER_LIST_DATA structure


## -description

The NET_BUFFER_LIST_DATA structure contains management data for the 
  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures that are linked to a 
  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure.

## -struct-fields

### -field Next

A pointer to the next NET_BUFFER_LIST structure in a linked list of NET_BUFFER_LIST structures. If
     this structure is the last NET_BUFFER_LIST structure in the list, this member is <b>NULL</b>.

### -field FirstNetBuffer

A pointer to the first 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure in the linked list of
     NET_BUFFER structures.

## -remarks

The 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_header">NET_BUFFER_LIST_HEADER</a> structure
    contains a NET_BUFFER_LIST_DATA structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_header">NET_BUFFER_LIST_HEADER</a>
