---
UID: NF:ndis.NdisGeneratePartialCancelId
title: NdisGeneratePartialCancelId function (ndis.h)
description: The NdisGeneratePartialCancelId function returns a value that the calling driver must use as the high-order byte of a cancellation ID.
old-location: netvista\ndisgeneratepartialcancelid.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisGeneratePartialCancelId function"]
ms.keywords: NdisGeneratePartialCancelId, NdisGeneratePartialCancelId function [Network Drivers Starting with Windows Vista], ndis/NdisGeneratePartialCancelId, netvista.ndisgeneratepartialcancelid, protocol_ndis_functions_ref_0d6b9e5a-d346-46a0-8f1c-d6677df53f1c.xml
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisGeneratePartialCancelId   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisGeneratePartialCancelId   (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisGeneratePartialCancelId
 - ndis/NdisGeneratePartialCancelId
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisGeneratePartialCancelId
---

# NdisGeneratePartialCancelId function


## -description

The
  <b>NdisGeneratePartialCancelId</b> function returns a value that the calling driver must use as the
  high-order byte of a cancellation ID.

## -returns

<b>NdisGeneratePartialCancelId</b> returns a value that the calling driver uses as the high-order byte of
     a cancellation ID.

## -remarks

Before marking send 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures with cancellation
    IDs by calling the 
    <a href="/windows-hardware/drivers/network/ndis-set-net-buffer-list-cancel-id">
    NDIS_SET_NET_BUFFER_LIST_CANCEL_ID</a> macro, a driver should call 
    <b>NdisGeneratePartialCancelId</b> one or more times. 
    <b>NdisGeneratePartialCancelId</b> returns a value that the calling driver can use as the high-order byte
    of a cancellation ID. Prefixing a cancellation ID with the value returned by 
    <b>NdisGeneratePartialCancelId</b> ensures that the cancellation ID will not be a duplicate of a
    cancellation ID assigned by another driver in the local computer.

Typically, an overlying driver calls 
    <b>NdisGeneratePartialCancelId</b> one or more times during its initialization sequence and stores the
    returned value or values for later use. A protocol driver, for example, could call 
    <b>NdisGeneratePartialCancelId</b> once for each client (such as DHCP or ARC) that it supports. The
    protocol driver can call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscancelsendnetbufferlists">
    NdisCancelSendNetBufferLists</a> function later to cancel a send request. In this case, NDIS calls the
    cancel send function (for example, 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_cancel_send">MiniportCancelSend</a>) of the
    underlying drivers.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_cancel_send">MiniportCancelSend</a>



<a href="/windows-hardware/drivers/network/ndis-set-net-buffer-list-cancel-id">
   NDIS_SET_NET_BUFFER_LIST_CANCEL_ID</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscancelsendnetbufferlists">NdisCancelSendNetBufferLists</a>
