---
UID: NC:ndis.NDIS_SWITCH_ADD_NET_BUFFER_LIST_DESTINATION
title: NDIS_SWITCH_ADD_NET_BUFFER_LIST_DESTINATION
author: windows-driver-content
description: The AddNetBufferListDestination function adds a single destination port for a packet that is specified by a NET_BUFFER_LIST structure.
old-location: netvista\AddNetBufferListDestination.htm
old-project: netvista
ms.assetid: 6B8CD868-D2F4-4892-BF6D-DFD7A3984320
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: AddNetBufferListDestination, AddNetBufferListDestination callback function [Network Drivers Starting with Windows Vista], NDIS_SWITCH_ADD_NET_BUFFER_LIST_DESTINATION, NDIS_SWITCH_ADD_NET_BUFFER_LIST_DESTINATION callback, ndis/AddNetBufferListDestination, netvista.AddNetBufferListDestination
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
-	AddNetBufferListDestination
product: Windows
targetos: Windows
req.typenames: 
---

# NDIS_SWITCH_ADD_NET_BUFFER_LIST_DESTINATION callback function


## -description


The <i>AddNetBufferListDestination</i> function adds a single destination port for a packet that is specified by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure.


## -parameters




### -param NdisSwitchContext [in]

An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the Hyper-V extensible switch extension is attached. When the extension calls <a href="https://msdn.microsoft.com/library/windows/hardware/hh598204">NdisFGetOptionalSwitchHandlers</a>,  this handle is returned through the <i>NdisSwitchContext</i> parameter.


### -param NetBufferList [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure for a packet. 

<div class="alert"><b>Note</b>  This structure must contain  an extensible switch forwarding context. If the extension created or cloned the  packet, it must have previously allocated this structure by calling the <a href="https://msdn.microsoft.com/C8A80DB2-4273-4FBA-82D4-4E8146812B16">AllocateNetBufferListForwardingContext</a> function.</div>
<div> </div>

### -param Destination [in]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh598224">NDIS_SWITCH_PORT_DESTINATION</a> structure. This structure specifies the destination extensible switch port that the packet will be forwarded to.


## -returns



If the call succeeds, the function returns NDIS_STATUS_SUCCESS. Otherwise, it returns an NDIS_STATUS_<i>Xxx</i> error code that is defined in Ndis.h.






## -remarks



The forwarding extensible switch extension calls <i>AddNetBufferListDestination</i> to define a single extensible switch destination port for a packet. The extension specifies this port by initializing an   <a href="https://msdn.microsoft.com/library/windows/hardware/hh598224">NDIS_SWITCH_PORT_DESTINATION</a> structure. The extension sets the <i>Destination</i> parameter to a pointer to this structure. For more information on how to specify an extensible switch destination port, see <a href="https://msdn.microsoft.com/2781E64A-61D6-49A9-AD9B-F6B348560E30">Managing Hyper-V Extensible Switch Destination Port Data</a>.

<div class="alert"><b>Note</b>  For performance reasons, the extension should not call <i>AddNetBufferListDestination</i> packets with multiple destination ports.</div>
<div> </div>
The extension must follow these guidelines before it calls <i>AddNetBufferListDestination</i>:

<ul>
<li>
Only forwarding extensions can call <i>AddNetBufferListDestination</i> to add a destination port for a packet. For more information on this type of extension, see <a href="https://msdn.microsoft.com/7ABBB3F3-66F5-4651-8A5A-94940F3FD82D">Forwarding Extensions</a>.

</li>
<li>
If the forwarding extension is originating a packet with one destination port, the extension must first call the <a href="https://msdn.microsoft.com/C8A80DB2-4273-4FBA-82D4-4E8146812B16">AllocateNetBufferListForwardingContext</a> function. This function allocates the extensible switch forwarding context for the packet. This data contains the extensible switch source and destination ports within the out-of-band (OOB) information for the packet.

For more information about this context, see <a href="https://msdn.microsoft.com/B2BF07B5-FA44-4994-9605-EFF4A0B9179F">Hyper-V Extensible Switch Forwarding Context</a>.

</li>
<li>
After the extension modifies the destination port information in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598224">NDIS_SWITCH_PORT_DESTINATION</a> structure, it calls <i>AddNetBufferListDestination</i> to commit the changes to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure for the packet.

<div class="alert"><b>Note</b>  For performance reasons, the extension should not call the <a href="https://msdn.microsoft.com/9A740524-0FC1-4585-8059-F678D4777F66">UpdateNetBufferListDestinations</a> function to commit the changes for the packet.
</div>
<div> </div>
</li>
</ul>
<div class="alert"><b>Note</b>  After the forwarding extension commits the changes for destination ports to the forwarding context, destination ports cannot be removed and only the <b>IsExcluded</b>  member of a destination port's <a href="https://msdn.microsoft.com/library/windows/hardware/hh598224">NDIS_SWITCH_PORT_DESTINATION</a> structure can be changed. For more information, see <a href="https://msdn.microsoft.com/04BF02A6-360F-482E-A86B-31232AFCB778">Excluding Packet Delivery to Extensible Switch Destination Ports</a>.</div>
<div> </div>



## -see-also




<b></b>



<a href="https://msdn.microsoft.com/55B5C0B4-5359-410B-9110-79EDDBA3010C">GetNetBufferListDestinations</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598224">NDIS_SWITCH_PORT_DESTINATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598204">NdisFGetOptionalSwitchHandlers</a>



<a href="https://msdn.microsoft.com/9A740524-0FC1-4585-8059-F678D4777F66">UpdateNetBufferListDestinations</a>
 

 

