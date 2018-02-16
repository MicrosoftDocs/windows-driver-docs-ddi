---
UID: NC:ndis.NDIS_SWITCH_GET_NET_BUFFER_LIST_SWITCH_CONTEXT
title: NDIS_SWITCH_GET_NET_BUFFER_LIST_SWITCH_CONTEXT
author: windows-driver-content
description: The Hyper-V extensible switch extension calls the GetNetBufferListSwitchContext function to retrieve the switch context previously set on the NET_BUFFER_LIST.
old-location: netvista\getnetbufferlistswitchcontext.htm
old-project: netvista
ms.assetid: 68270219-7003-489B-8362-8D6867D571FD
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.getnetbufferlistswitchcontext, GetNetBufferListSwitchContext callback function [Network Drivers Starting with Windows Vista], GetNetBufferListSwitchContext, NDIS_SWITCH_GET_NET_BUFFER_LIST_SWITCH_CONTEXT, NDIS_SWITCH_GET_NET_BUFFER_LIST_SWITCH_CONTEXT, ndis/GetNetBufferListSwitchContext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ndis.h
apiname:
-	GetNetBufferListSwitchContext
product: Windows
targetos: Windows
req.typenames: "*LPVIDEO_STREAM_INIT_PARMS, VIDEO_STREAM_INIT_PARMS"
---

# NDIS_SWITCH_GET_NET_BUFFER_LIST_SWITCH_CONTEXT callback


## -description


The Hyper-V extensible switch extension calls the GetNetBufferListSwitchContext function to retrieve the switch context previously set on the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>. 


## -prototype


````
NDIS_SWITCH_GET_NET_BUFFER_LIST_SWITCH_CONTEXT GetNetBufferListSwitchContext;

PVOID GetNetBufferListSwitchContext(
  _In_ NDIS_SWITCH_CONTEXT                       NdisSwitchContext,
  _In_ PNET_BUFFER_LIST                          NetBufferList,
  _In_ PNDIS_SWITCH_NET_BUFFER_LIST_CONTEXT_TYPE ContextType
)
{ ... }
````


## -parameters




### -param NdisSwitchContext [in]

An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the Hyper-V extensible switch extension is attached. When the extension calls <a href="..\ndis\nf-ndis-ndisfgetoptionalswitchhandlers.md">NdisFGetOptionalSwitchHandlers</a>, this handle is returned through the <i>NdisSwitchContext</i> parameter.


### -param NetBufferList [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure for a single packet that contains the context to be retrieved.

<div class="alert"><b>Note</b>  This structure must contain an extensible switch forwarding context. If the extension created or cloned the packet, it must have previously allocated this structure by calling the AllocateNetBufferListForwardingContext function.</div>
<div> </div>

### -param ContextType [in]

Context

Context type declared using the <i>NDIS_DECLARE_SWITCH_NET_BUFFER_LIST_CONTEXT_TYPE</i> that was used when setting the context. 


## -returns



NULL if no context was found in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> that matches the specified context type. Otherwise, a non-NULL pointer to the buffer is returned. 




## -remarks



The <a href="..\ndis\nc-ndis-ndis_switch_set_net_buffer_list_switch_context.md">SetNetBufferListSwitchContext</a> APIs allow extensions to attach context to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> on ingress and retrieve it on egress. Even so, extensions should be resilient to the ingress context not being present on egress. The switch context is not preserved when an NET_BUFFER_LIST is cloned, so in scenarios where the NET_BUFFER_LIST is cloned between ingress and egress, the NET_BUFFER_LIST will not have the original's switch context.

The extension must manage the lifetime of the context. One approach is to allocate NDIS NET_BUFFER_LIST context (using <a href="..\ndis\nf-ndis-ndisallocatenetbufferlistcontext.md">NdisAllocateNetBufferListContext</a>, or preconfigured if the extension owns the NET_BUFFER_LIST pool), and use the <a href="..\ndis\nc-ndis-ndis_switch_set_net_buffer_list_switch_context.md">SetNetBufferListSwitchContext</a> to associate a context type identifier with the NDIS NET_BUFFER_LIST context. When the NBL is completed, the extension can free the NDIS NET_BUFFER_LIST context (using <a href="..\ndis\nf-ndis-ndisfreenetbufferlistcontext.md">NdisFreeNetBufferListContext</a>, or freeing the NET_BUFFER_LIST itself if it was originated by the extension).

For more information about the extensible switch forwarding context, see <a href="https://msdn.microsoft.com/B2BF07B5-FA44-4994-9605-EFF4A0B9179F">Hyper-V Extensible Switch Forwarding Context</a>.




## -see-also

<a href="..\ndis\nf-ndis-ndisfoidrequest.md">NdisFOidRequest</a>



<a href="https://msdn.microsoft.com/55B5C0B4-5359-410B-9110-79EDDBA3010C">GetNetBufferListDestinations</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="..\ndis\ns-ndis-_ndis_switch_port_destination.md">NDIS_SWITCH_PORT_DESTINATION</a>



<a href="..\ndis\nc-ndis-ndis_switch_set_net_buffer_list_switch_context.md">SetNetBufferListSwitchContext</a>



<a href="..\ndis\nf-ndis-ndisfgetoptionalswitchhandlers.md">NdisFGetOptionalSwitchHandlers</a>



<a href="https://msdn.microsoft.com/C8A80DB2-4273-4FBA-82D4-4E8146812B16">AllocateNetBufferListForwardingContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_GET_NET_BUFFER_LIST_SWITCH_CONTEXT callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

