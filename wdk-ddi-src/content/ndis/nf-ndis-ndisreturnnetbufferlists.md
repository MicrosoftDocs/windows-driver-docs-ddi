---
UID: NF:ndis.NdisReturnNetBufferLists
title: NdisReturnNetBufferLists function (ndis.h)
description: NDIS drivers call the NdisReturnNetBufferLists function to release ownership of a list of NET_BUFFER_LIST structures, along with the associated NET_BUFFER structures and network data.
old-location: netvista\ndisreturnnetbufferlists.htm
tech.root: netvista
ms.assetid: 1a45bc5c-cdc1-46d2-905b-3d5eea3645c1
ms.date: 05/02/2018
ms.keywords: NdisReturnNetBufferLists, NdisReturnNetBufferLists function [Network Drivers Starting with Windows Vista], ndis/NdisReturnNetBufferLists, ndis_sendrcv_ref_9c5a4908-356f-4e7c-9351-4fec4358180d.xml, netvista.ndisreturnnetbufferlists
ms.topic: function
f1_keywords:
 - "ndis/NdisReturnNetBufferLists"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_SendRcv_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisReturnNetBufferLists
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisReturnNetBufferLists function


## -description


NDIS drivers call the 
  <b>NdisReturnNetBufferLists</b> function to release ownership of a list of 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures, along with the
  associated 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures and network data.


## -parameters




### -param NdisBindingHandle [in]

A handle that identifies the target adapter. This handle was returned by a previous call to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a> function. All of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures that are
     specified in this call must be from the binding that this handle identifies.


### -param NetBufferLists [in]

A pointer to a linked list of NET_BUFFER_LIST structures that are to be returned to the underlying
     driver. The linked list can contain NET_BUFFER_LIST structures from multiple previous calls to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_receive_net_buffer_lists">
     ProtocolReceiveNetBufferLists</a> function.


### -param ReturnFlags [in]

NDIS flags that can be combined with an OR operation. To clear all the flags, set this member to
     zero. This function supports the NDIS_RETURN_FLAGS_DISPATCH_LEVEL flag which; if set, indicates that the
     current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/dispatch-irql-tracking">Dispatch IRQL Tracking</a>.


## -remarks



If the NDIS_RECEIVE_FLAGS_RESOURCES flag in the 
    <i>ReceiveFlags</i> parameter that NDIS passed to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_receive_net_buffer_lists">
    ProtocolReceiveNetBufferLists</a> function was not set, the protocol driver must call 
    <b>NdisReturnNetBufferLists</b> to return the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures and associated
    data. After the protocol driver calls 
    <b>NdisReturnNetBufferLists</b>, NDIS calls the underlying miniport driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_return_net_buffer_lists">
    MiniportReturnNetBufferLists</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_return_net_buffer_lists">
   MiniportReturnNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_receive_net_buffer_lists">
   ProtocolReceiveNetBufferLists</a>
 

 

