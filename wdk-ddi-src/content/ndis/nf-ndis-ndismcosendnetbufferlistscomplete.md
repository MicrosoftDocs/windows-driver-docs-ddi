---
UID: NF:ndis.NdisMCoSendNetBufferListsComplete
title: NdisMCoSendNetBufferListsComplete function (ndis.h)
description: The NdisMCoSendNetBufferListsComplete function returns a linked list of NET_BUFFER_LIST structures to an overlying driver and returns the final status of a CoNDIS send request.
old-location: netvista\ndismcosendnetbufferlistscomplete.htm
tech.root: netvista
ms.assetid: c4978122-6d13-4e9b-8eb7-d06cd7372268
ms.date: 05/02/2018
ms.keywords: NdisMCoSendNetBufferListsComplete, NdisMCoSendNetBufferListsComplete function [Network Drivers Starting with Windows Vista], condis_sendrcv_ref_49470611-47cb-4778-8723-4acc2ebbfb81.xml, ndis/NdisMCoSendNetBufferListsComplete, netvista.ndismcosendnetbufferlistscomplete
ms.topic: function
f1_keywords:
 - "ndis/NdisMCoSendNetBufferListsComplete"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_MCO_Function
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
- NdisMCoSendNetBufferListsComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMCoSendNetBufferListsComplete function


## -description


The 
  <b>NdisMCoSendNetBufferListsComplete</b> function returns a linked list of 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures to an overlying
  driver and returns the final status of a CoNDIS send request.


## -parameters




### -param NdisVcHandle [in]

A handle that identifies a virtual connection (VC). The miniport driver obtained this handle as an
     input parameter to its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_co_create_vc">MiniportCoCreateVc</a> function, either
     when a client set up an outgoing call or when the call manager created a VC for a client-registered
     service access point (SAP) to indicate an incoming-call notification on.


### -param NetBufferLists [in]

A pointer to a linked list of 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures. The miniport
     driver received the NET_BUFFER_LIST structures in previous calls to its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_co_send_net_buffer_lists">
     MiniportCoSendNetBufferLists</a> function.


### -param SendCompleteFlags [in]

NDIS flags that can be combined with a bitwise OR operation. To clear all of the flags, set this
     parameter to zero. 
     <b>NdisMCoSendNetBufferListsComplete</b> supports the NDIS_SEND_COMPLETE_FLAGS_DISPATCH_LEVEL flag,
     which; if set, indicates that the current IRQL is DISPATCH_LEVEL. For more information about this flag,
     see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/dispatch-irql-tracking">Dispatch IRQL Tracking</a>.


## -returns



None




## -remarks



A miniport driver calls 
    <b>NdisMCoSendNetBufferListsComplete</b> to complete send requests that NDIS made to the driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_co_send_net_buffer_lists">
    MiniportCoSendNetBufferLists</a> function. The miniport driver specifies a linked list of 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures that are
    associated with the completed send requests.

While the status of the send requests is pending, the miniport driver retains ownership of the
    NET_BUFFER_LIST structures and all of the resources that are associated with the NET_BUFFER_LIST
    structures.

After a miniport driver calls 
    <b>NdisMCoSendNetBufferListsComplete</b>, NDIS returns the NET_BUFFER_LIST structures and associated data
    to the overlying driver that originated the send request.

The miniport driver can complete send requests in any order. For example, the miniport driver could
    concatenate the NET_BUFFER_LIST structure lists from multiple 
    <i>MiniportCoSendNetBufferLists</i> calls or split up a list from a 
    <i>MiniportCoSendNetBufferLists</i> call. However, the miniport driver must not modify the list of
    NET_BUFFER structures that are associated with a NET_BUFFER_LIST structure.

The miniport driver must set one of the following status codes in the 
    <b>Status</b> member of each NET_BUFFER_LIST structure that the 
    <i>NetBufferLists</i> parameter specifies:



A miniport driver's call to 
    <b>NdisMCoSendNetBufferListsComplete</b> does not necessarily indicate that the data for a send request
    has been transmitted over the network. For example, the data might be queued in the NIC hardware.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_cancel_send">MiniportCancelSend</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_co_create_vc">MiniportCoCreateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_co_send_net_buffer_lists">
   MiniportCoSendNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>
 

 

