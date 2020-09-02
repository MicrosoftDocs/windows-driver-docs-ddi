---
UID: NF:ndis.NdisGetNetBufferListProtocolId
title: NdisGetNetBufferListProtocolId function (ndis.h)
description: The NdisGetNetBufferListProtocolId function retrieves the protocol identifier from the NetBufferListInfo member of a NET_BUFFER_LIST structure.
old-location: netvista\ndisgetnetbufferlistprotocolid.htm
tech.root: netvista
ms.assetid: a90b1318-ce21-4483-b253-767674fe0a2f
ms.date: 05/02/2018
keywords: ["NdisGetNetBufferListProtocolId function"]
ms.keywords: NdisGetNetBufferListProtocolId, NdisGetNetBufferListProtocolId function [Network Drivers Starting with Windows Vista], ndis/NdisGetNetBufferListProtocolId, ndis_netbuf_functions_ref_7ce217e7-6d68-4e22-af32-bc984c1b7677.xml, netvista.ndisgetnetbufferlistprotocolid
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
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
req.lib: Ndis.lib
req.dll: 
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisGetNetBufferListProtocolId
 - ndis/NdisGetNetBufferListProtocolId
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisGetNetBufferListProtocolId
---

# NdisGetNetBufferListProtocolId function


## -description

The 
  <b>NdisGetNetBufferListProtocolId</b> function retrieves the protocol identifier from the 
  <b>NetBufferListInfo</b> member of a 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure.

## -parameters

### -param NetBufferList 

[in]
A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure.

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
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure. For example,
    miniport drivers that support TCP chimney offload can verify that a NET_BUFFER_LIST structure comes from
    a TCP protocol.

Protocol drivers that create NET_BUFFER_LIST structures should set the protocol identifier by calling the [NdisSetNetBufferListProtocolId](nf-ndis-ndissetnetbufferlistprotocolid.md) macro or by associating an identifier with a NET_BUFFER_LIST pool.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



[NdisSetNetBufferListProtocolId](nf-ndis-ndissetnetbufferlistprotocolid.md)

