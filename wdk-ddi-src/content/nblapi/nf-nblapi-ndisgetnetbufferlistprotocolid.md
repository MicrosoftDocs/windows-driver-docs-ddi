---
UID: NF:nblapi.NdisGetNetBufferListProtocolId
title: NdisGetNetBufferListProtocolId
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: The NdisGetNetBufferListProtocolId function retrieves the protocol identifier from the NetBufferListInfo member of a NET_BUFFER_LIST structure.
tech.root: netvista
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ndis/nblapi.h
req.idl: 
req.include-header: ndis.h
req.irql: Any level
req.kmdf-ver: 
req.lib: Ndis.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.target-type: Universal
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - nblapi.h
api_name:
 - NdisGetNetBufferListProtocolId
f1_keywords:
 - NdisGetNetBufferListProtocolId
 - nblapi/NdisGetNetBufferListProtocolId
dev_langs:
 - c++
---

# NdisGetNetBufferListProtocolId function


## -description

The 
  <b>NdisGetNetBufferListProtocolId</b> function retrieves the protocol identifier from the 
  <b>NetBufferListInfo</b> member of a 
  <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure.

## -parameters

### -param NetBufferList 

[in]
A pointer to a 
     <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure.

## -returns

<b>NdisGetNetBufferListProtocolId</b> returns a protocol identifier as one of the following
     values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_PROTOCOL_ID_DEFAULT</b></dt>
</dl>
</td>
<td width="60%">
A default protocol driver identifier.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_PROTOCOL_ID_TCP_IP</b></dt>
</dl>
</td>
<td width="60%">
The TCP/IP protocol identifier.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_PROTOCOL_ID_IPX</b></dt>
</dl>
</td>
<td width="60%">
The IPX protocol identifier.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_PROTOCOL_ID_NBF</b></dt>
</dl>
</td>
<td width="60%">
The NetBEUI protocol identifier.

</td>
</tr>
</table>

## -remarks

NDIS drivers can call the 
    <b>NdisGetNetBufferListProtocolId</b> function to determine the type of protocol driver that created a 
    <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure. For example,
    miniport drivers that support TCP chimney offload can verify that a NET_BUFFER_LIST structure comes from
    a TCP protocol.

Protocol drivers that create NET_BUFFER_LIST structures should set the protocol identifier by calling the [NdisSetNetBufferListProtocolId](nf-ndis-ndissetnetbufferlistprotocolid.md) macro or by associating an identifier with a NET_BUFFER_LIST pool.

## -see-also

<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>



[NdisSetNetBufferListProtocolId](nf-ndis-ndissetnetbufferlistprotocolid.md)
