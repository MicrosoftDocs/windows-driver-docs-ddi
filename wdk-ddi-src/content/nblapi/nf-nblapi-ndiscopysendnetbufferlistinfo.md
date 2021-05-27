---
UID: NF:nblapi.NdisCopySendNetBufferListInfo
title: NdisCopySendNetBufferListInfo
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: Intermediate drivers call the NdisCopySendNetBufferListInfo function to copy the NET_BUFFER_LIST information in a transmit NET_BUFFER_LIST structure.
tech.root: netvista
req.assembly: 
req.construct-type: function
req.ddi-compliance: Irql_NetBuffer_Function
req.dll: 
req.header: ndis/nblapi.h
req.idl: 
req.include-header: ndis.h
req.irql: <= DISPATCH_LEVEL
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
 - NdisCopySendNetBufferListInfo
f1_keywords:
 - NdisCopySendNetBufferListInfo
 - nblapi/NdisCopySendNetBufferListInfo
dev_langs:
 - c++
---


# NdisCopySendNetBufferListInfo function


## -description

Intermediate drivers call the 
  <b>NdisCopySendNetBufferListInfo</b> function to copy the 
  <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> information in a transmit
  <b>NET_BUFFER_LIST</b> structure.

## -parameters

### -param DestNetBufferList 

[in]
A pointer to the destination <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure.

### -param SrcNetBufferList 

[in]
A pointer to the source <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure.

## -remarks

When an intermediate driver or filter driver receives a transmit request from an overlying driver, it
    can, for example, clone the 
    <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure or allocate a new
    structure to propagate the request to underlying drivers. The driver should use 
    <b>NdisCopySendNetBufferListInfo</b> to copy the <b>NET_BUFFER_LIST</b> information, including private NDIS
    information, to the new structure.

To copy the <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> information on the receive path, use the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscopyreceivenetbufferlistinfo">
    NdisCopyReceiveNetBufferListInfo</a> function.

The following <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> items are copied in a call to <b>NdisCopySendNetBufferListInfo</b>:

<table>
<tr>
<th>Copied Item </th>
<th>Starting Windows Version</th>
</tr>
<tr>
<td>TcpIpChecksumNetBufferListInfo</td>
<td>Windows Vista</td>
</tr>
<tr>
<td>IPsecOffloadV1NetBufferListInfo</td>
<td>Windows Vista</td>
</tr>
<tr>
<td>TcpLargeSendNetBufferListInfo</td>
<td>Windows Vista</td>
</tr>
<tr>
<td>Ieee8021QNetBufferListInfo</td>
<td>Windows Vista</td>
</tr>
<tr>
<td>MediaSpecificInformation</td>
<td>Windows Vista</td>
</tr>
<tr>
<td>NetBufferListCancelId</td>
<td>Windows Vista</td>
</tr>
<tr>
<td>NetBufferListProtocolId</td>
<td>Windows Vista</td>
</tr>
<tr>
<td>IPsecOffloadV2TunnelNetBufferListInfo</td>
<td>Windows Vista with Service Pack 1 (SP1)</td>
</tr>
<tr>
<td>IPsecOffloadV2HeaderNetBufferListInfo</td>
<td>Windows Vista with SP1</td>
</tr>
<tr>
<td>VirtualSubnetInfo</td>
<td>Windows 8 (AMD64 only)</td>
</tr>
<tr>
<td>NetBufferListFilteringInfo</td>
<td>Windows 8</td>
</tr>
</table>

## -see-also

<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/network/net-buffer-list-structure">NET_BUFFER_LIST Structure</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscopyreceivenetbufferlistinfo">
   NdisCopyReceiveNetBufferListInfo</a>
