---
UID: NC:ndis.NDIS_SWITCH_SET_NET_BUFFER_LIST_SOURCE
title: NDIS_SWITCH_SET_NET_BUFFER_LIST_SOURCE
author: windows-driver-content
description: The SetNetBufferListSource function sets the Hyper-V extensible switch source port identifier and network adapter index for a packet that is specified by a NET_BUFFER_LIST structure.
old-location: netvista\setnetbufferlistsource.htm
old-project: netvista
ms.assetid: 6537824A-F521-4916-AAC8-7C0E6E5F7331
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NDIS_SWITCH_SET_NET_BUFFER_LIST_SOURCE, SetNetBufferListSource, SetNetBufferListSource callback function [Network Drivers Starting with Windows Vista], ndis/SetNetBufferListSource, netvista.setnetbufferlistsource
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	SetNetBufferListSource
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# NDIS_SWITCH_SET_NET_BUFFER_LIST_SOURCE callback


## -description



The <i>SetNetBufferListSource</i> function sets the Hyper-V extensible switch source port identifier and network adapter index for a packet that is specified by a <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.




## -prototype


````
NDIS_SWITCH_SET_NET_BUFFER_LIST_SOURCE SetNetBufferListSource;

NDIS_STATUS SetNetBufferListSource(
  _In_    NDIS_SWITCH_CONTEXT   NdisSwitchContext,
  _Inout_ PNET_BUFFER_LIST      NetBufferLists,
  _In_    NDIS_SWITCH_PORT_ID   PortId,
  _In_    NDIS_SWITCH_NIC_INDEX NicIndex
)
{ ... }
````


## -parameters




### -param NdisSwitchContext [in]

An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the Hyper-V extensible switch extension is attached. When the extension calls <a href="..\ndis\nf-ndis-ndisfgetoptionalswitchhandlers.md">NdisFGetOptionalSwitchHandlers</a>,  this handle is returned through the <i>NdisSwitchContext</i> parameter.


### -param NetBufferList


### -param PortId [in]

An NDIS_SWITCH_PORT_ID value that specifies the unique identifier of the source port on the extensible switch.


### -param NicIndex [in]

An NDIS_SWITCH_NIC_INDEX value that specifies the index of the network adapter that is connected to the extensible switch port specified by the <i>PortId</i> parameter.

For more information on NDIS_SWITCH_NIC_INDEX values, see <a href="https://msdn.microsoft.com/969333DA-0282-474B-8D56-72CD623C5329">Network Adapter Index Values</a>.



<div class="alert"><b>Note</b>  This parameter must specify the index value of a network adapter that is in a connected state. Index values for network adapters that are in a created or disconnected state cannot be specified. For more information about network connection states, see <a href="https://msdn.microsoft.com/1E2075E3-D7CC-4364-ABB2-D5969DB361B5">Hyper-V Extensible Switch Port and Network Adapter States</a>.</div>
<div> </div>

#### - NetBufferLists [in, out]

A pointer to a <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure for a single packet.  

<div class="alert"><b>Note</b>  This structure must contain  an extensible switch forwarding context that was previously allocated by calling the <a href="https://msdn.microsoft.com/C8A80DB2-4273-4FBA-82D4-4E8146812B16">AllocateNetBufferListForwardingContext</a> function. For more information about the extensible switch forwarding context, see <a href="https://msdn.microsoft.com/B2BF07B5-FA44-4994-9605-EFF4A0B9179F">Hyper-V Extensible Switch Forwarding Context</a>.</div>
<div> </div>

## -returns



If the call succeeds, the function returns NDIS_STATUS_SUCCESS. Otherwise, it returns an NDIS_STATUS_<i>Xxx</i> error code that is defined in Ndis.h.






## -remarks



The extensible switch extension calls the <i>SetNetBufferListSource</i> function to set the source port identifier and network adapter index in a packet's <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure. The extension does this for the following types of packets:

<ul>
<li>
A new packet that the extension has allocated for send or receive operations.

<div class="alert"><b>Note</b>  Before the extension calls <i>SetNetBufferListSource</i> for an allocated packet, it must call <a href="https://msdn.microsoft.com/C8A80DB2-4273-4FBA-82D4-4E8146812B16">AllocateNetBufferListForwardingContext</a>. </div>
<div> </div>
</li>
<li>
A duplicated packet that the extension had cloned from an original packet that it was filtering. The extension duplicates a packet by calling <a href="..\ndis\nf-ndis-ndisallocateclonenetbufferlist.md">NdisAllocateCloneNetBufferList</a>.

</li>
</ul>
In both cases, a new or duplicated packet will have its source port identifier set to <b>NDIS_SWITCH_DEFAULT_PORT_ID</b> and its source network adapter index set to <b>NDIS_SWITCH_DEFAULT_NIC_INDEX</b>. The extension  calls the <i>SetNetBufferListSource</i> function to change the source port identifier and network adapter index in a packet's <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.

For example, a packet that has a source port identifier of <b>NDIS_SWITCH_DEFAULT_PORT_ID</b> is trusted and bypasses many extensible switch port policies. These policies include access control lists (ACLs) and quality of service (QoS). If the extension specifies a non-default source port for the packet, this allows the policies for that port to be applied to the packet.

<div class="alert"><b>Note</b>  Because packets with a source port identifier of <b>NDIS_SWITCH_DEFAULT_PORT_ID</b> are trusted, the extension must use this source port identifier very carefully when it originates packet traffic. For more information on the recommended use of the <b>NDIS_SWITCH_DEFAULT_PORT_ID</b> for source ports, see <a href="https://msdn.microsoft.com/885A2D15-BEFC-4FB0-AFE4-B472448E0FEA">Managing Hyper-V Extensible Switch Source Port Data</a>.</div>
<div> </div>
For more information on packet send and receive operations, see <a href="https://msdn.microsoft.com/208f9af6-cde4-4801-9355-daa6633d7d0b">Filter Module Send and Receive Operations</a>.




## -see-also

<a href="https://msdn.microsoft.com/C8A80DB2-4273-4FBA-82D4-4E8146812B16">AllocateNetBufferListForwardingContext</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\ndis\nf-ndis-ndisfgetoptionalswitchhandlers.md">NdisFGetOptionalSwitchHandlers</a>



<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>



<a href="..\ndis\nf-ndis-ndisallocateclonenetbufferlist.md">NdisAllocateCloneNetBufferList</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_SET_NET_BUFFER_LIST_SOURCE callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

