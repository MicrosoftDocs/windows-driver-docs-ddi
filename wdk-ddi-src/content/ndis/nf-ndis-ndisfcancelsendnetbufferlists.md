---
UID: NF:ndis.NdisFCancelSendNetBufferLists
title: NdisFCancelSendNetBufferLists function (ndis.h)
description: Filter drivers call the NdisFCancelSendNetBufferLists function to cancel the transmission of network data.
old-location: netvista\ndisfcancelsendnetbufferlists.htm
tech.root: netvista
ms.assetid: 358b1aa9-4bfd-4bed-94f7-1b021c732a02
ms.date: 05/02/2018
keywords: ["NdisFCancelSendNetBufferLists function"]
ms.keywords: NdisFCancelSendNetBufferLists, NdisFCancelSendNetBufferLists function [Network Drivers Starting with Windows Vista], filter_ndis_functions_ref_272bc8c3-bf88-42d8-b415-429100169d47.xml, ndis/NdisFCancelSendNetBufferLists, netvista.ndisfcancelsendnetbufferlists
f1_keywords:
 - "ndis/NdisFCancelSendNetBufferLists"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Filter_Driver_Function
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
- NdisFCancelSendNetBufferLists
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFCancelSendNetBufferLists function


## -description


Filter drivers call the 
  <b>NdisFCancelSendNetBufferLists</b> function to cancel the transmission of network data.


## -parameters




### -param NdisFilterHandle [in]

The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a> function.


### -param CancelId [in]

The cancellation identifier. This identifier specifies the network data for the transmission that
     is being canceled.


## -remarks



A filter driver can cancel the send requests that it originates or pass on the cancellation requests
    from overlying drivers. To cancel a send request from an overlying driver, NDIS calls the filter drivers 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_cancel_send_net_buffer_lists">
    FilterCancelSendNetBufferLists</a> function.

A filter driver can call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-set-net-buffer-list-cancel-id">
    NDIS_SET_NET_BUFFER_LIST_CANCEL_ID</a> macro to mark NET_BUFFER_LIST structures that it originates and
    passes down to lower-level drivers for transmission. The NDIS_SET_NET_BUFFER_LIST_CANCEL_ID macro marks
    the specified packet with a cancellation identifier.

<b>NdisFCancelSendNetBufferLists</b> cancels the transmission of all data that is marked with the
    specified cancellation identifier.

NDIS returns canceled send data that the filter driver originated to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_send_net_buffer_lists_complete">
    FilterSendNetBufferListsComplete</a> function. The completion status of canceled requests is
    NDIS_STATUS_SEND_ABORTED.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_cancel_send_net_buffer_lists">
   FilterCancelSendNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_send_net_buffer_lists_complete">
   FilterSendNetBufferListsComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-set-net-buffer-list-cancel-id">
   NDIS_SET_NET_BUFFER_LIST_CANCEL_ID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>
 

 

