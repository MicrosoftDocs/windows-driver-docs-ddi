---
UID: NC:ndis.NDIS_SWITCH_GET_NET_BUFFER_LIST_SWITCH_CONTEXT
title: NDIS_SWITCH_GET_NET_BUFFER_LIST_SWITCH_CONTEXT (ndis.h)
description: The Hyper-V extensible switch extension calls the GetNetBufferListSwitchContext function to retrieve the switch context previously set on the NET_BUFFER_LIST.
old-location: netvista\getnetbufferlistswitchcontext.htm
tech.root: netvista
ms.assetid: 68270219-7003-489B-8362-8D6867D571FD
ms.date: 05/02/2018
keywords: ["NDIS_SWITCH_GET_NET_BUFFER_LIST_SWITCH_CONTEXT callback function"]
ms.keywords: GetNetBufferListSwitchContext, GetNetBufferListSwitchContext callback function [Network Drivers Starting with Windows Vista], NDIS_SWITCH_GET_NET_BUFFER_LIST_SWITCH_CONTEXT, NDIS_SWITCH_GET_NET_BUFFER_LIST_SWITCH_CONTEXT callback, ndis/GetNetBufferListSwitchContext, netvista.getnetbufferlistswitchcontext
f1_keywords:
 - "ndis/GetNetBufferListSwitchContext"
 - "GetNetBufferListSwitchContext"
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
- GetNetBufferListSwitchContext
targetos: Windows
req.typenames: 
---

# NDIS_SWITCH_GET_NET_BUFFER_LIST_SWITCH_CONTEXT callback function


## -description


The Hyper-V extensible switch extension calls the GetNetBufferListSwitchContext function to retrieve the switch context previously set on the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>. 


## -parameters




### -param NdisSwitchContext 
[in]
An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the Hyper-V extensible switch extension is attached. When the extension calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>, this handle is returned through the <i>NdisSwitchContext</i> parameter.


### -param NetBufferList 
[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure for a single packet that contains the context to be retrieved.

<div class="alert"><b>Note</b>  This structure must contain an extensible switch forwarding context. If the extension created or cloned the packet, it must have previously allocated this structure by calling the AllocateNetBufferListForwardingContext function.</div>
<div> </div>

### -param ContextType 
[in]
Context

Context type declared using the <i>NDIS_DECLARE_SWITCH_NET_BUFFER_LIST_CONTEXT_TYPE</i> that was used when setting the context. 


## -returns



NULL if no context was found in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> that matches the specified context type. Otherwise, a non-NULL pointer to the buffer is returned. 




## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_set_net_buffer_list_switch_context">SetNetBufferListSwitchContext</a> APIs allow extensions to attach context to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> on ingress and retrieve it on egress. Even so, extensions should be resilient to the ingress context not being present on egress. The switch context is not preserved when an NET_BUFFER_LIST is cloned, so in scenarios where the NET_BUFFER_LIST is cloned between ingress and egress, the NET_BUFFER_LIST will not have the original's switch context.

The extension must manage the lifetime of the context. One approach is to allocate NDIS NET_BUFFER_LIST context (using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistcontext">NdisAllocateNetBufferListContext</a>, or preconfigured if the extension owns the NET_BUFFER_LIST pool), and use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_set_net_buffer_list_switch_context">SetNetBufferListSwitchContext</a> to associate a context type identifier with the NDIS NET_BUFFER_LIST context. When the NBL is completed, the extension can free the NDIS NET_BUFFER_LIST context (using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbufferlistcontext">NdisFreeNetBufferListContext</a>, or freeing the NET_BUFFER_LIST itself if it was originated by the extension).

For more information about the extensible switch forwarding context, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/hyper-v-extensible-switch-forwarding-context">Hyper-V Extensible Switch Forwarding Context</a>.




## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_allocate_net_buffer_list_forwarding_context">AllocateNetBufferListForwardingContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_get_net_buffer_list_destinations">GetNetBufferListDestinations</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_switch_port_destination">NDIS_SWITCH_PORT_DESTINATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfoidrequest">NdisFOidRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_set_net_buffer_list_switch_context">SetNetBufferListSwitchContext</a>
 

 

