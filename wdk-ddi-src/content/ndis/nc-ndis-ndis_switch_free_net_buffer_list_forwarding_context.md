---
UID: NC:ndis.NDIS_SWITCH_FREE_NET_BUFFER_LIST_FORWARDING_CONTEXT
title: NDIS_SWITCH_FREE_NET_BUFFER_LIST_FORWARDING_CONTEXT (ndis.h)
description: The FreeNetBufferListForwardingContext function releases resources in the out-of-band (OOB) extensible switch forwarding context of a NET_BUFFER_LIST structure.
old-location: netvista\FreeNetBufferListForwardingContext.htm
tech.root: netvista
ms.assetid: 08AE3160-276F-4D1F-9D02-AD5AF38CDED2
ms.date: 05/02/2018
ms.keywords: FreeNetBufferListForwardingContext, FreeNetBufferListForwardingContext callback function [Network Drivers Starting with Windows Vista], NDIS_SWITCH_FREE_NET_BUFFER_LIST_FORWARDING_CONTEXT, NDIS_SWITCH_FREE_NET_BUFFER_LIST_FORWARDING_CONTEXT callback, ndis/FreeNetBufferListForwardingContext, netvista.FreeNetBufferListForwardingContext
ms.topic: callback
f1_keywords:
 - "ndis/FreeNetBufferListForwardingContext"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndis.h
api_name:
- FreeNetBufferListForwardingContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDIS_SWITCH_FREE_NET_BUFFER_LIST_FORWARDING_CONTEXT callback function


## -description



The <i>FreeNetBufferListForwardingContext</i> function releases resources in the out-of-band (OOB) extensible switch forwarding context of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure. This data was used for send or receive operations in a Hyper-V extensible switch, and was previously allocated  by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_allocate_net_buffer_list_forwarding_context">AllocateNetBufferListForwardingContext</a> function.




## -parameters




### -param NdisSwitchContext [in]

An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the Hyper-V extensible switch extension is attached. When the extension calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>,  this handle is returned through the <i>NdisSwitchContext</i> parameter.


### -param NetBufferList [in, out]

A pointer to a linked list of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures.

<div class="alert"><b>Note</b>  This structure must contain an extensible switch forwarding context that was previously allocated by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_allocate_net_buffer_list_forwarding_context">AllocateNetBufferListForwardingContext</a> function.</div>
<div> </div>

## -returns



If the call succeeds, the function returns NDIS_STATUS_SUCCESS. Otherwise, it returns an NDIS_STATUS_<i>Xxx</i> error code that is defined in Ndis.h.






## -remarks



The extensible switch extension can originate packet send operations within the extensible switch data path. For example, the extension can send packets to any port on the extensible switch. For more information about this data path, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/hyper-v-extensible-switch-data-path">Hyper-V Extensible Switch Data Path</a>.

If the extensible switch extension originates a packet send  operation, the extension must  call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_allocate_net_buffer_list_forwarding_context">AllocateNetBufferListForwardingContext</a> function. This function allocates and initializes the forwarding context  for the specified  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure. For more information about this context, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/hyper-v-extensible-switch-forwarding-context">Hyper-V Extensible Switch Forwarding Context</a>.

When the send operation is complete, the extension must call the <i>FreeNetBufferListForwardingContext</i> function to deallocate the forwarding context.

<div class="alert"><b>Note</b>  The extension must call the <i>FreeNetBufferListForwardingContext</i> function when the send operation is completed. The extension must do this regardless of whether it adds the packet's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure to a lookaside list or calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbufferlist">NdisFreeNetBufferList</a> to return the structure to a pool. </div>
<div> </div>
 For more information on how to originate send operations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/filter-module-send-and-receive-operations">Filter Module Send and Receive Operations</a>.

<div class="alert"><b>Note</b>  If the <i>NetBufferList</i> parameter contains a pointer to a linked-list of multiple <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures, only the first  <b>NET_BUFFER_LIST</b> structure in the list has its forwarding context deallocated.</div>
<div> </div>



## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_allocate_net_buffer_list_forwarding_context">AllocateNetBufferListForwardingContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbufferlist">NdisFreeNetBufferList</a>
 

 

