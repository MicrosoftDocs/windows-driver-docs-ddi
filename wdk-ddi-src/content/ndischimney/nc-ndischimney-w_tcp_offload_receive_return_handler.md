---
UID: NC:ndischimney.W_TCP_OFFLOAD_RECEIVE_RETURN_HANDLER
title: W_TCP_OFFLOAD_RECEIVE_RETURN_HANDLER (ndischimney.h)
description: NDIS calls the MiniportTcpOffloadReceiveReturn function to return ownership of NET_BUFFER_LIST and associated structures to an offload target.
old-location: netvista\miniporttcpoffloadreceivereturn.htm
tech.root: netvista
ms.assetid: b746f58d-d029-4fcd-a59d-baba037fc38e
ms.date: 05/02/2018
keywords: ["W_TCP_OFFLOAD_RECEIVE_RETURN_HANDLER callback function"]
ms.keywords: MiniportTcpOffloadReceiveReturn, MiniportTcpOffloadReceiveReturn callback function [Network Drivers Starting with Windows Vista], W_TCP_OFFLOAD_RECEIVE_RETURN_HANDLER, W_TCP_OFFLOAD_RECEIVE_RETURN_HANDLER callback, ndischimney/MiniportTcpOffloadReceiveReturn, netvista.miniporttcpoffloadreceivereturn, tcp_chim_miniport_func_c6477511-6f31-4a37-9b28-d157e1fa09af.xml
req.header: ndischimney.h
req.include-header: Ndischimney.h
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
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - W_TCP_OFFLOAD_RECEIVE_RETURN_HANDLER
 - ndischimney/W_TCP_OFFLOAD_RECEIVE_RETURN_HANDLER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndischimney.h
api_name:
 - MiniportTcpOffloadReceiveReturn
---

# W_TCP_OFFLOAD_RECEIVE_RETURN_HANDLER callback function


## -description

<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

NDIS calls the 
  <i>MiniportTcpOffloadReceiveReturn</i> function to return ownership of 
  <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> and associated structures to
  an offload target.

## -parameters

### -param MiniportAdapterContext 

[in]
The handle to an offload-target allocated context area in which the offload target maintains state
     information about this instance of the adapter. The miniport driver provided this handle to NDIS when it
     called 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">
     NdisMSetMiniportAttributes</a> from its 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">
     MiniportInitializeEx</a> function.

### -param NetBufferList 

[in]
A pointer to a 
     <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure. This structure
     can be a stand-alone structure or the first structure in a linked list of NET_BUFFER_LIST structures.
     The linked list can contain NET_BUFFER_LIST structures from one or more calls to the 
     <a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_receive_indicate">
     NdisTcpOffloadReceiveHandler</a> function.

## -returns

The 
     <i>MiniportTcpOffloadReceiveReturn</i> function should always succeed. Therefore, the 
     <i>MiniportTcpOffloadReceiveReturn</i> function should always return NDIS_STATUS_SUCCESS.

## -remarks

NDIS calls the 
    <i>MiniportTcpOffloadReceiveReturn</i> function to return ownership of NET_BUFFER_LIST structures and
    associated structures that the offload target passed in one or more previous calls to the 
    <a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_receive_indicate">
    NdisTcpOffloadReceiveHandler</a> function.

The 
    <i>MiniportTcpOffloadReceiveReturn</i> function can prepare a returned NET_BUFFER_LIST structure for use
    in a subsequent receive indication. Although the 
    <i>MiniportTcpOffloadReceiveReturn</i> function can return the NET_BUFFER_LIST structures to a pool (for
    example, it could call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbufferlist">NdisFreeNetBufferList</a> function), it
    can be more efficient to reuse the structures without returning them to the pool.

Note that the offload target driver should not unload and the offload target adapter must not be
    closed until all indicated receive buffers have been returned.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbufferlist">NdisFreeNetBufferList</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a>



<a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_receive_indicate">NdisTcpOffloadReceiveHandler</a>