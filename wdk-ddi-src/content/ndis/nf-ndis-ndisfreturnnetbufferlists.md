---
UID: NF:ndis.NdisFReturnNetBufferLists
title: NdisFReturnNetBufferLists function (ndis.h)
description: Filter drivers call NdisFReturnNetBufferLists to release the ownership of one or more NET_BUFFER_LIST structures and their associated NET_BUFFER structures.
old-location: netvista\ndisfreturnnetbufferlists.htm
tech.root: netvista
ms.assetid: 083cf25d-7436-4c4e-b29a-c9a2702b136d
ms.date: 05/02/2018
keywords: ["NdisFReturnNetBufferLists function"]
ms.keywords: NdisFReturnNetBufferLists, NdisFReturnNetBufferLists function [Network Drivers Starting with Windows Vista], filter_ndis_functions_ref_3473c0c3-077c-4df7-b9d4-8392cf1ed918.xml, ndis/NdisFReturnNetBufferLists, netvista.ndisfreturnnetbufferlists
f1_keywords:
 - "ndis/NdisFReturnNetBufferLists"
 - "NdisFReturnNetBufferLists"
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
- NdisFReturnNetBufferLists
targetos: Windows
req.typenames: 
---

# NdisFReturnNetBufferLists function


## -description


Filter drivers call
  <b>NdisFReturnNetBufferLists</b> to release the ownership of one or more 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures and their
  associated 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures.


## -parameters




### -param NdisFilterHandle 
[in]
The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a> function.


### -param NetBufferLists 
[in]
A pointer to a linked list of NET_BUFFER_LIST structures that are to be returned to the underlying
     driver. The linked list can contain NET_BUFFER_LIST structures from multiple previous calls to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_receive_net_buffer_lists">
     FilterReceiveNetBufferLists</a> function.


### -param ReturnFlags 
[in]
NDIS flags that can be combined with an OR operation. To clear all the flags, set this member to
     zero.This function supports the following flags: 





#### NDIS_RETURN_FLAGS_DISPATCH_LEVEL

Specifies that the current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/network/dispatch-irql-tracking">Dispatch IRQL Tracking</a>.



#### NDIS_RETURN_FLAGS_SWITCH_SINGLE_SOURCE

If this flag is set, all packets in a linked list of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures originated from the same Hyper-V extensible switch source port.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/hyper-v-extensible-switch-send-and-receive-flags">Hyper-V Extensible Switch Send and Receive Flags</a>.

<div class="alert"><b>Note</b>  If each packet in the linked list of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures uses the same source port, the extension should set the <b>NDIS_RECEIVE_FLAGS_SWITCH_SINGLE_SOURCE</b> flag in the <i>ReceiveFlags</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfindicatereceivenetbufferlists">NdisFIndicateReceiveNetBufferLists</a>  when it sends the request.</div>
<div> </div>

## -remarks



If the NDIS_RECEIVE_FLAGS_RESOURCES flag in the 
    <i>ReceiveFlags</i> parameter that NDIS passed to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_receive_net_buffer_lists">
    FilterReceiveNetBufferLists</a> function was not set, the filter driver must call the 
    <b>NdisFReturnNetBufferLists</b> function to return the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures and associated
    data. After the filter driver calls 
    <b>NdisFReturnNetBufferLists</b>, NDIS returns the data to the underlying driver.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_receive_net_buffer_lists">FilterReceiveNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>
 

 

