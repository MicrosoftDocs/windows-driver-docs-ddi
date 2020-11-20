---
UID: NC:ndis.NDIS_SWITCH_SET_NET_BUFFER_LIST_SWITCH_CONTEXT
title: NDIS_SWITCH_SET_NET_BUFFER_LIST_SWITCH_CONTEXT (ndis.h)
description: The Hyper-V extensible switch extension calls the SetNetBufferListSwitchContext function to attach an extension-allocated context buffer to the NET_BUFFER_LIST.
old-location: netvista\setnetbufferlistswitchcontext.htm
tech.root: netvista
ms.assetid: BFA54990-E1BB-4E86-B806-F3021FB0075B
ms.date: 05/02/2018
keywords: ["NDIS_SWITCH_SET_NET_BUFFER_LIST_SWITCH_CONTEXT callback function"]
ms.keywords: NDIS_SWITCH_SET_NET_BUFFER_LIST_SWITCH_CONTEXT, NDIS_SWITCH_SET_NET_BUFFER_LIST_SWITCH_CONTEXT callback, SetNetBufferListSwitchContext, SetNetBufferListSwitchContext callback function [Network Drivers Starting with Windows Vista], ndis/SetNetBufferListSwitchContext, netvista.setnetbufferlistswitchcontext
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NDIS_SWITCH_SET_NET_BUFFER_LIST_SWITCH_CONTEXT
 - ndis/NDIS_SWITCH_SET_NET_BUFFER_LIST_SWITCH_CONTEXT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - SetNetBufferListSwitchContext
---

# NDIS_SWITCH_SET_NET_BUFFER_LIST_SWITCH_CONTEXT callback function


## -description

The Hyper-V extensible switch extension calls the <i>SetNetBufferListSwitchContext</i> function to attach an extension-allocated context buffer to the <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>. The context is then accessible for the lifetime of that NET_BUFFER_LIST, including if the context is set on ingress and the NBL is seen again on egress, regardless of whether other extensions set their own context. This type of access is not possible using the existing NDIS NET_BUFFER_LIST context APIs (<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistcontext">NdisAllocateNetBufferListContext</a>/ <a href="/windows-hardware/drivers/network/net-buffer-list-context-data-start">NET_BUFFER_LIST_CONTEXT_DATA_START</a>) because another extension can allocate NDIS context when it gets ownership of the NET_BUFFER_LIST, at which point the pointer to the original NDIS context is lost.

## -parameters

### -param NdisSwitchContext 

[in]
An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the Hyper-V extensible switch extension is attached. When the extension calls <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>, this handle is returned through the <i>NdisSwitchContext</i> parameter.

### -param NetBufferList 

[in, out]
A pointer to a <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure for a single packet that receives the context association.

<div class="alert"><b>Note</b>  This structure must contain an extensible switch forwarding context. If the extension created or cloned the packet, it must have previously allocated this structure by calling the <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_allocate_net_buffer_list_forwarding_context">AllocateNetBufferListForwardingContext</a> function.</div>
<div> </div>

### -param ContextType 

[in]
The context type declared using <i>NDIS_DECLARE_SWITCH_NET_BUFFER_LIST_CONTEXT_TYPE</i> that will be used as the key when retrieving the context.

### -param Context 

[in]
The pointer to the context that will be retrievable using the specified <i>ContextType</i>.

## -returns

If the call succeeds, the function returns NDIS_STATUS_SUCCESS. Otherwise, it returns an NDIS_STATUS_<i>Xxx</i> error code that is defined in Ndis.h.

## -remarks

The <i>SetNetBufferListSwitchContext</i> APIs allow extensions to attach context to a <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> on ingress and retrieve it on egress. Even so, extensions should be resilient to the ingress context not being present on egress. The switch context is not preserved when an NET_BUFFER_LIST is cloned, so in scenarios where the NET_BUFFER_LIST is cloned between ingress and egress, the NET_BUFFER_LIST will not have the original's switch context. 

The extension must manage the lifetime of the context. One approach is to allocate NDIS NET_BUFFER_LIST context (using <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistcontext">NdisAllocateNetBufferListContext</a>, or preconfigured if the extension owns the NET_BUFFER_LIST pool), and use the <i>SetNetBufferListSwitchContext</i> to associate a context type identifier with the NDIS NET_BUFFER_LIST context. When the NBL is completed, the extension can free the NDIS NET_BUFFER_LIST context (using <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbufferlistcontext">NdisFreeNetBufferListContext</a>, or freeing the NET_BUFFER_LIST itself if it was originated by the extension).

For more information about the extensible switch forwarding context, see <a href="/windows-hardware/drivers/network/hyper-v-extensible-switch-forwarding-context">Hyper-V Extensible Switch Forwarding Context</a>.

## -see-also

<b></b>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_allocate_net_buffer_list_forwarding_context">AllocateNetBufferListForwardingContext</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_get_net_buffer_list_destinations">GetNetBufferListDestinations</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_get_net_buffer_list_switch_context">GetNetBufferListSwitchContext</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_switch_port_destination">NDIS_SWITCH_PORT_DESTINATION</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfoidrequest">NdisFOidRequest</a>