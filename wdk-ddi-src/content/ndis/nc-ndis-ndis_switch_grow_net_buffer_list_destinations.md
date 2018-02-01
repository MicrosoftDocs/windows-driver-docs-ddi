---
UID: NC:ndis.NDIS_SWITCH_GROW_NET_BUFFER_LIST_DESTINATIONS
title: NDIS_SWITCH_GROW_NET_BUFFER_LIST_DESTINATIONS
author: windows-driver-content
description: The GrowNetBufferListDestinations function adds space for additional Hyper-V extensible switch destination ports to a packet that is specified by a NET_BUFFER_LIST structure.
old-location: netvista\grownetbufferlistdestinations.htm
old-project: netvista
ms.assetid: 9A79F41F-566F-4844-BF1A-E8889E6FDCE8
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.grownetbufferlistdestinations, GrowNetBufferListDestinations callback function [Network Drivers Starting with Windows Vista], GrowNetBufferListDestinations, NDIS_SWITCH_GROW_NET_BUFFER_LIST_DESTINATIONS, NDIS_SWITCH_GROW_NET_BUFFER_LIST_DESTINATIONS, ndis/GrowNetBufferListDestinations
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
-	GrowNetBufferListDestinations
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# NDIS_SWITCH_GROW_NET_BUFFER_LIST_DESTINATIONS callback


## -description



The <i>GrowNetBufferListDestinations</i> function adds space for additional Hyper-V extensible switch destination ports to a packet that is specified by a <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.




## -prototype


````
NDIS_SWITCH_GROW_NET_BUFFER_LIST_DESTINATIONS GrowNetBufferListDestinations;

NDIS_STATUS GrowNetBufferListDestinations(
  _In_    NDIS_SWITCH_CONTEXT                       NdisSwitchContext,
  _Inout_ PNET_BUFFER_LIST                          NetBufferLists,
  _In_    UINT32                                    NumberOfNewDestinations,
  _Out_   PNDIS_SWITCH_FORWARDING_DESTINATION_ARRAY *Destinations
)
{ ... }
````


## -parameters




### -param NdisSwitchContext [in]

An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the Hyper-V extensible switch extension is attached. When the extension calls <a href="..\ndis\nf-ndis-ndisfgetoptionalswitchhandlers.md">NdisFGetOptionalSwitchHandlers</a>,  this handle is returned through the <i>NdisSwitchContext</i> parameter.


### -param NetBufferList



### -param NumberOfNewDestinations [in]

A UINT32 value that specifies the number of new destination ports to be  added for the packet.


### -param Destinations [out]

A pointer to an <a href="..\ndis\ns-ndis-_ndis_switch_forwarding_destination_array.md">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a> structure. This structure specifies the extensible switch destination ports of the packet.


#### - NetBufferLists [in, out]

A pointer to a linked list of <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures.  
<div class="alert"><b>Note</b>  This structure must contain  an extensible switch forwarding context. If the extension created or cloned the  packet, it must have previously allocated this structure by calling the <a href="https://msdn.microsoft.com/C8A80DB2-4273-4FBA-82D4-4E8146812B16">AllocateNetBufferListForwardingContext</a> function. For more information about the extensible switch forwarding context, see <a href="https://msdn.microsoft.com/B2BF07B5-FA44-4994-9605-EFF4A0B9179F">Hyper-V Extensible Switch Forwarding Context</a>.</div><div> </div>

## -returns


If the call succeeds, the function returns NDIS_STATUS_SUCCESS. Otherwise, it returns an NDIS_STATUS_<i>Xxx</i> error code that is defined in Ndis.h.





## -remarks


The extensible switch extension calls the <i>GrowNetBufferListDestinations</i> function to add space for destination ports for a packet. Port destinations are specified through an <a href="..\ndis\ns-ndis-_ndis_switch_forwarding_destination_array.md">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a> structure.

For more information on how to add destination ports to a packet, see <a href="https://msdn.microsoft.com/C921D9F8-B6FB-4B53-8CC5-CC941720FF37">Adding Extensible Switch Destination Port Data to a Packet</a>.
<div class="alert"><b>Note</b>  If the <i>NetBufferList</i> parameter contains a pointer to a linked-list of multiple <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures, space for additional destination ports is only added to the first  <b>NET_BUFFER_LIST</b> structure in the list.</div><div> </div>


## -see-also

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

<a href="..\ndis\ns-ndis-_ndis_switch_forwarding_destination_array.md">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a>

<a href="https://msdn.microsoft.com/C8A80DB2-4273-4FBA-82D4-4E8146812B16">AllocateNetBufferListForwardingContext</a>

<a href="https://msdn.microsoft.com/9A740524-0FC1-4585-8059-F678D4777F66">UpdateNetBufferListDestinations</a>

<a href="..\ndis\nf-ndis-ndisfgetoptionalswitchhandlers.md">NdisFGetOptionalSwitchHandlers</a>

<a href="..\ndis\ns-ndis-_ndis_switch_port_destination.md">NDIS_SWITCH_PORT_DESTINATION</a>

<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>

<b></b>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_GROW_NET_BUFFER_LIST_DESTINATIONS callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

