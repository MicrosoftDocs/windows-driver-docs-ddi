---
UID: NC:ndis.NDIS_SWITCH_FREE_NET_BUFFER_LIST_FORWARDING_CONTEXT
title: NDIS_SWITCH_FREE_NET_BUFFER_LIST_FORWARDING_CONTEXT
author: windows-driver-content
description: The FreeNetBufferListForwardingContext function releases resources in the out-of-band (OOB) extensible switch forwarding context of a NET_BUFFER_LIST structure.
old-location: netvista\FreeNetBufferListForwardingContext.htm
old-project: netvista
ms.assetid: 08AE3160-276F-4D1F-9D02-AD5AF38CDED2
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.FreeNetBufferListForwardingContext, FreeNetBufferListForwardingContext callback function [Network Drivers Starting with Windows Vista], FreeNetBufferListForwardingContext, NDIS_SWITCH_FREE_NET_BUFFER_LIST_FORWARDING_CONTEXT, NDIS_SWITCH_FREE_NET_BUFFER_LIST_FORWARDING_CONTEXT, ndis/FreeNetBufferListForwardingContext
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
req.irql: <= DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	Ndis.h
apiname: 
-	FreeNetBufferListForwardingContext
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# NDIS_SWITCH_FREE_NET_BUFFER_LIST_FORWARDING_CONTEXT callback


## -description



The <i>FreeNetBufferListForwardingContext</i> function releases resources in the out-of-band (OOB) extensible switch forwarding context of a <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure. This data was used for send or receive operations in a Hyper-V extensible switch, and was previously allocated  by calling the <a href="https://msdn.microsoft.com/C8A80DB2-4273-4FBA-82D4-4E8146812B16">AllocateNetBufferListForwardingContext</a> function.




## -prototype


````
NDIS_SWITCH_FREE_NET_BUFFER_LIST_FORWARDING_CONTEXT FreeNetBufferListForwardingContext;

NDIS_STATUS FreeNetBufferListForwardingContext(
  _In_    NDIS_SWITCH_CONTEXT NdisSwitchContext,
  _Inout_ PNET_BUFFER_LIST    NetBufferList
)
{ ... }
````


## -parameters




### -param NdisSwitchContext [in]

An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the Hyper-V extensible switch extension is attached. When the extension calls <a href="..\ndis\nf-ndis-ndisfgetoptionalswitchhandlers.md">NdisFGetOptionalSwitchHandlers</a>,  this handle is returned through the <i>NdisSwitchContext</i> parameter.


### -param NetBufferList [in, out]

A pointer to a linked list of <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures.
<div class="alert"><b>Note</b>  This structure must contain an extensible switch forwarding context that was previously allocated by calling the <a href="https://msdn.microsoft.com/C8A80DB2-4273-4FBA-82D4-4E8146812B16">AllocateNetBufferListForwardingContext</a> function.</div><div> </div>

## -returns


If the call succeeds, the function returns NDIS_STATUS_SUCCESS. Otherwise, it returns an NDIS_STATUS_<i>Xxx</i> error code that is defined in Ndis.h.





## -remarks


The extensible switch extension can originate packet send operations within the extensible switch data path. For example, the extension can send packets to any port on the extensible switch. For more information about this data path, see <a href="https://msdn.microsoft.com/5E7F135B-3086-415F-8D39-98CDBED8EBB4">Hyper-V Extensible Switch Data Path</a>.

If the extensible switch extension originates a packet send  operation, the extension must  call the <a href="https://msdn.microsoft.com/C8A80DB2-4273-4FBA-82D4-4E8146812B16">AllocateNetBufferListForwardingContext</a> function. This function allocates and initializes the forwarding context  for the specified  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure. For more information about this context, see <a href="https://msdn.microsoft.com/B2BF07B5-FA44-4994-9605-EFF4A0B9179F">Hyper-V Extensible Switch Forwarding Context</a>.

When the send operation is complete, the extension must call the <i>FreeNetBufferListForwardingContext</i> function to deallocate the forwarding context.
<div class="alert"><b>Note</b>  The extension must call the <i>FreeNetBufferListForwardingContext</i> function when the send operation is completed. The extension must do this regardless of whether it adds the packet's <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure to a lookaside list or calls <a href="..\ndis\nf-ndis-ndisfreenetbufferlist.md">NdisFreeNetBufferList</a> to return the structure to a pool. </div><div> </div> For more information on how to originate send operations, see <a href="https://msdn.microsoft.com/208f9af6-cde4-4801-9355-daa6633d7d0b">Filter Module Send and Receive Operations</a>.
<div class="alert"><b>Note</b>  If the <i>NetBufferList</i> parameter contains a pointer to a linked-list of multiple <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures, only the first  <b>NET_BUFFER_LIST</b> structure in the list has its forwarding context deallocated.</div><div> </div>


## -see-also

<a href="https://msdn.microsoft.com/C8A80DB2-4273-4FBA-82D4-4E8146812B16">AllocateNetBufferListForwardingContext</a>

<a href="..\ndis\nf-ndis-ndisfreenetbufferlist.md">NdisFreeNetBufferList</a>

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

<a href="..\ndis\nf-ndis-ndisfgetoptionalswitchhandlers.md">NdisFGetOptionalSwitchHandlers</a>

<b></b>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_FREE_NET_BUFFER_LIST_FORWARDING_CONTEXT callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

