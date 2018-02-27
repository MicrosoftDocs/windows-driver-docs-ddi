---
UID: NC:ndis.NDIS_SWITCH_ALLOCATE_NET_BUFFER_LIST_FORWARDING_CONTEXT
title: NDIS_SWITCH_ALLOCATE_NET_BUFFER_LIST_FORWARDING_CONTEXT
author: windows-driver-content
description: The AllocateNetBufferListForwardingContext function prepares a NET_BUFFER_LIST structure for send or receive operations within the extensible switch.
old-location: netvista\AllocateNetBufferListForwardingContext.htm
old-project: netvista
ms.assetid: C8A80DB2-4273-4FBA-82D4-4E8146812B16
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: AllocateNetBufferListForwardingContext, AllocateNetBufferListForwardingContext callback function [Network Drivers Starting with Windows Vista], NDIS_SWITCH_ALLOCATE_NET_BUFFER_LIST_FORWARDING_CONTEXT, ndis/AllocateNetBufferListForwardingContext, netvista.AllocateNetBufferListForwardingContext
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
-	AllocateNetBufferListForwardingContext
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# NDIS_SWITCH_ALLOCATE_NET_BUFFER_LIST_FORWARDING_CONTEXT callback


## -description



The <i>AllocateNetBufferListForwardingContext</i> function prepares a <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure for send or receive operations within the extensible switch.




## -prototype


````
NDIS_SWITCH_ALLOCATE_NET_BUFFER_LIST_FORWARDING_CONTEXT AllocateNetBufferListForwardingContext;

NDIS_STATUS AllocateNetBufferListForwardingContext(
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


## -returns



If the call succeeds, the function returns NDIS_STATUS_SUCCESS. Otherwise, it returns an NDIS_STATUS_<i>Xxx</i> error code that is defined in Ndis.h.






## -remarks



The extensible switch extension can originate packet send operations within the extensible switch data path. For example, the extension can send packets to any port on the extensible switch. For more information about this data path, see <a href="https://msdn.microsoft.com/5E7F135B-3086-415F-8D39-98CDBED8EBB4">Hyper-V Extensible Switch Data Path</a>.

After the extension calls <a href="..\ndis\nf-ndis-ndisallocatenetbufferlist.md">NdisAllocateNetBufferList</a> or <a href="..\ndis\nf-ndis-ndisallocateclonenetbufferlist.md">NdisAllocateCloneNetBufferList</a> to create or clone a packet from its <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> pool, the extension must  call the <i>AllocateNetBufferListForwardingContext</i> function. This function allocates and initializes the out-of-band (OOB) extensible switch forwarding context for the specified  <b>NET_BUFFER_LIST</b> structure. For more information about this context, see <a href="https://msdn.microsoft.com/B2BF07B5-FA44-4994-9605-EFF4A0B9179F">Hyper-V Extensible Switch Forwarding Context</a>.

The extension must follow these guidelines for allocating the forwarding context through the <i>AllocateNetBufferListForwardingContext</i> function:

<ul>
<li>
The extension calls <a href="..\ndis\nf-ndis-ndisallocatenetbufferlist.md">NdisAllocateNetBufferList</a> to allocate a packet from the extension's <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> pool for a send or receive operation over the extensible switch. Before the extension initializes source and destination ports for the packet, it must call <i>AllocateNetBufferListForwardingContext</i>. 

For more information on how to specify source and destination extensible switch ports, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/managing-hyper-v-extensible-switch-source-and-destination-port-data">Managing Hyper-V Extensible Switch Source and Destination Port Data</a>.

</li>
<li>
Before the extension calls <i>AllocateNetBufferListForwardingContext</i>, it must set the <b>SourceHandle</b> member of each allocated <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure to the handle value that identifies the extension. The extension receives this handle through the <i>NdisFilterHandle</i> parameter when NDIS calls the extension's <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.

</li>
<li>
When the send operation is complete, the extension must call the <a href="https://msdn.microsoft.com/08AE3160-276F-4D1F-9D02-AD5AF38CDED2">FreeNetBufferListForwardingContext</a> function to deallocate the resources for the forwarding context. The extension must call this function before it calls <a href="..\ndis\nf-ndis-ndisfreenetbufferlist.md">NdisFreeNetBufferList</a> to return the packet to its <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> pool.

</li>
<li>
If the extension is cloning a packet, it must call <a href="https://msdn.microsoft.com/5CC345FA-C3EF-4122-8E9C-6EA27B20DD5A">CopyNetBufferListInfo</a> to copy the forwarding context from the original packet to the cloned packet. The extension must do this after it calls <i>AllocateNetBufferListForwardingContext</i>.

</li>
</ul>
 For more information on how to originate send operations, see <a href="https://msdn.microsoft.com/208f9af6-cde4-4801-9355-daa6633d7d0b">Filter Module Send and Receive Operations</a>.

<div class="alert"><b>Note</b>  If the <i>NetBufferList</i> parameter contains a pointer to a linked-list of multiple <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures, only the first  <b>NET_BUFFER_LIST</b> structure in the list has a forwarding context allocated for it.</div>
<div> </div>



## -see-also

<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/08AE3160-276F-4D1F-9D02-AD5AF38CDED2">FreeNetBufferListForwardingContext</a>



<a href="..\ndis\nf-ndis-ndisallocatenetbufferlist.md">NdisAllocateNetBufferList</a>



<a href="..\ndis\nf-ndis-ndisfreenetbufferlist.md">NdisFreeNetBufferList</a>



<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/5CC345FA-C3EF-4122-8E9C-6EA27B20DD5A">CopyNetBufferListInfo</a>



<a href="..\ndis\nf-ndis-ndisfgetoptionalswitchhandlers.md">NdisFGetOptionalSwitchHandlers</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_ALLOCATE_NET_BUFFER_LIST_FORWARDING_CONTEXT callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

