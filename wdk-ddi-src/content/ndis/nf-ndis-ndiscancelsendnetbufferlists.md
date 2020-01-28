---
UID: NF:ndis.NdisCancelSendNetBufferLists
title: NdisCancelSendNetBufferLists function (ndis.h)
description: Protocol drivers call the NdisCancelSendNetBufferLists function to cancel the transmission of network data.
old-location: netvista\ndiscancelsendnetbufferlists.htm
tech.root: netvista
ms.assetid: 7b61db73-ddd4-4d46-b378-9a82fdf041ea
ms.date: 05/02/2018
ms.keywords: NdisCancelSendNetBufferLists, NdisCancelSendNetBufferLists function [Network Drivers Starting with Windows Vista], ndis/NdisCancelSendNetBufferLists, ndis_sendrcv_ref_f4aca438-863f-44fa-9503-8ac339010360.xml, netvista.ndiscancelsendnetbufferlists
f1_keywords:
 - "ndis/NdisCancelSendNetBufferLists"
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
- NdisCancelSendNetBufferLists
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisCancelSendNetBufferLists function


## -description


Protocol drivers call the 
  <b>NdisCancelSendNetBufferLists</b> function to cancel the transmission of network data.


## -parameters




### -param NdisBindingHandle [in]

The handle returned by the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a> function that
     identifies the miniport driver or virtual miniport to which the cancellation applies.


### -param CancelId [in]

The cancellation identifier. This identifier specifies the network data for which transmission is
     being canceled.


## -remarks



A protocol driver maps IRPs that it receives from higher-level software to NDIS network data. A list
    of 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures describes the
    network data that the protocol driver sends to lower-level drivers for transmission. If an IRP is
    canceled, a protocol driver can call the 
    <b>NdisCancelSendNetBufferLists</b> function to cancel the pending transmission of the corresponding NDIS
    network data.

Call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-set-net-buffer-list-cancel-id">
    NDIS_SET_NET_BUFFER_LIST_CANCEL_ID</a> macro for each NET_BUFFER_LIST structure that is passed to
    lower-level drivers for transmission. The NDIS_SET_NET_BUFFER_LIST_CANCEL_ID macro marks the specified
    packet with a cancellation identifier.

<b>NdisCancelSendNetBufferLists</b> cancels the transmission of all data that is marked with the specified
    cancellation identifier and is associated with the specified miniport driver. The binding handle that is
    specified in the 
    <i>NdisBindingHandle</i> parameter identifies the miniport driver.

The 
    <b>NdisCancelSendNetBufferLists</b> function cancels network data transmissions on a single binding. To
    cancel network data transmissions on more than one binding, a protocol driver must call the 
    <b>NdisCancelSendNetBufferLists</b> function once for each binding.

The protocol driver must ensure that the handle that the 
    <i>NdisBindingHandle</i> parameter specifies remains valid for the duration of the call to 
    <b>NdisCancelSendNetBufferLists</b>. That is, the protocol driver must not call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscloseadapterex">NdisCloseAdapterEx</a> function to close
    the binding before 
    <b>NdisCancelSendNetBufferLists</b> returns.

There is no guarantee that calling 
    <b>NdisCancelSendNetBufferLists</b> will cancel the pending transmission of all network data with the
    specified cancellation identifier. For example, if the next-lower driver to which the protocol driver is
    bound does not provide a 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_cancel_send">MiniportCancelSend</a> function, a call
    to 
    <b>NdisCancelSendNetBufferLists</b> does nothing.

In all cases, NDIS returns network data that was submitted for transmission to the originating
    protocol driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_send_net_buffer_lists_complete">
    ProtocolSendNetBufferListsComplete</a> function. NDIS returns canceled send data with a completion
    status of NDIS_STATUS_SEND_ABORTED. The delay between calling 
    <b>NdisCancelSendNetBufferLists</b> and the return of the canceled NET_BUFFER_LIST structures can vary and
    therefore cannot be exactly specified.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_cancel_send">MiniportCancelSend</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-set-net-buffer-list-cancel-id">
   NDIS_SET_NET_BUFFER_LIST_CANCEL_ID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscloseadapterex">NdisCloseAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_send_net_buffer_lists_complete">
   ProtocolSendNetBufferListsComplete</a>
 

 

