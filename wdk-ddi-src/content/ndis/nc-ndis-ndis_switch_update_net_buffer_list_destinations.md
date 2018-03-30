---
UID: NC:ndis.NDIS_SWITCH_UPDATE_NET_BUFFER_LIST_DESTINATIONS
title: NDIS_SWITCH_UPDATE_NET_BUFFER_LIST_DESTINATIONS
author: windows-driver-content
description: The Hyper-V extensible switch extension calls the UpdateNetBufferListDestinations function to commit modifications that the extension made to a packet that contains multiple extensible switch destination ports.
old-location: netvista\UpdateNetBufferListDestinations.htm
old-project: netvista
ms.assetid: 9A740524-0FC1-4585-8059-F678D4777F66
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NDIS_SWITCH_UPDATE_NET_BUFFER_LIST_DESTINATIONS, UpdateNetBufferListDestinations, UpdateNetBufferListDestinations callback function [Network Drivers Starting with Windows Vista], ndis/UpdateNetBufferListDestinations, netvista.UpdateNetBufferListDestinations
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
-	UpdateNetBufferListDestinations
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# NDIS_SWITCH_UPDATE_NET_BUFFER_LIST_DESTINATIONS callback


## -description



The Hyper-V extensible switch extension calls the <i>UpdateNetBufferListDestinations</i> function to commit modifications that the extension made to a packet that contains multiple extensible switch destination ports. The function saves these modifications to the out-of-band (OOB) extensible switch forwarding context of the packet's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure. 




## -parameters




### -param NdisSwitchContext [in]

An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the Hyper-V extensible switch extension is attached. When the extension calls <a href="https://msdn.microsoft.com/library/windows/hardware/hh598204">NdisFGetOptionalSwitchHandlers</a>,  this handle is returned through the <i>NdisSwitchContext</i> parameter.


### -param NetBufferList [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure for a single packet.

<div class="alert"><b>Note</b>  This structure must contain  an extensible switch forwarding context. If the extension created or cloned the  packet, it must have previously allocated this structure by calling the <a href="https://msdn.microsoft.com/C8A80DB2-4273-4FBA-82D4-4E8146812B16">AllocateNetBufferListForwardingContext</a> function.</div>
<div> </div>

### -param NumberOfNewDestinations [in]

A UINT32 value that specifies the number of new destination ports that were added to the packet.


### -param Destinations [in]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh598210">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a> structure. This structure specifies the extensible switch destination ports of the packet.

<div class="alert"><b>Note</b>  The extension received this structure through a previous call to the <a href="https://msdn.microsoft.com/55B5C0B4-5359-410B-9110-79EDDBA3010C">GetNetBufferListDestinations</a> function.</div>
<div> </div>

## -returns



If the call succeeds, the function returns NDIS_STATUS_SUCCESS. Otherwise, it returns an NDIS_STATUS_<i>Xxx</i> error code that is defined in Ndis.h.






## -remarks



The extensible switch extension calls the <a href="https://msdn.microsoft.com/55B5C0B4-5359-410B-9110-79EDDBA3010C">GetNetBufferListDestinations</a> function to obtain an array of the extensible switch destination ports for a packet. If the function returns successfully, the array is obtained through the <i>Destinations</i> parameter, which contains a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh598210">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a> structure. Each element in this array is formatted as an <a href="https://msdn.microsoft.com/library/windows/hardware/hh598224">NDIS_SWITCH_PORT_DESTINATION</a> structure that specifies a destination port for the packet.

After the extension obtains the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598210">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a> structure, the extension can do the following:

<ul>
<li>
Add additional <a href="https://msdn.microsoft.com/library/windows/hardware/hh598224">NDIS_SWITCH_PORT_DESTINATION</a> elements in the array.

For more information, see <a href="https://msdn.microsoft.com/C921D9F8-B6FB-4B53-8CC5-CC941720FF37">Adding Extensible Switch Destination Port Data to a Packet</a>.

</li>
<li>
Modify existing <a href="https://msdn.microsoft.com/library/windows/hardware/hh598224">NDIS_SWITCH_PORT_DESTINATION</a> elements of the array to exclude a packet from being forwarded to a specified port.

For more information, see <a href="https://msdn.microsoft.com/04BF02A6-360F-482E-A86B-31232AFCB778">Excluding Packet Delivery to Extensible Switch Destination Ports</a>.

</li>
</ul>
If the extension adds or modifies destination ports in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598210">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a> structure, the extension must call the <i>UpdateNetBufferListDestinations</i> function to commit those changes to the packet's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure.

<div class="alert"><b>Note</b>  Only forwarding extensions can call <i>UpdateNetBufferListDestinations</i> to commit destination ports that were added or changed for packets with multiple destination ports. For more information on this type of extension, see <a href="https://msdn.microsoft.com/7ABBB3F3-66F5-4651-8A5A-94940F3FD82D">Forwarding Extensions</a>.</div>
<div> </div>
If the call to <i>UpdateNetBufferListDestinations</i> returns NDIS_STATUS_SUCCESS, the extensible switch interface guarantees that the extensible switch port and network adapter connection that are referenced in the destination ports will not be deleted until the packet's send or receive operation is completed. 

Also, after the changes for destination ports have been committed, destination ports cannot be removed, and only the <b>IsExcluded</b>  member of a destination port's <a href="https://msdn.microsoft.com/library/windows/hardware/hh598224">NDIS_SWITCH_PORT_DESTINATION</a> structure can be changed. For more information, see <a href="https://msdn.microsoft.com/04BF02A6-360F-482E-A86B-31232AFCB778">Excluding Packet Delivery to Extensible Switch Destination Ports</a>.

<div class="alert"><b>Note</b>  For performance reasons, the extension should not call the <i>UpdateNetBufferListDestinations</i> function to commit the changes to a packet with only one destination port.
Instead, the extension calls <a href="https://msdn.microsoft.com/6B8CD868-D2F4-4892-BF6D-DFD7A3984320">AddNetBufferListDestination</a> to commit the changes to the packet's destination port.</div>
<div> </div>
For more information about the extensible switch forwarding context, see <a href="https://msdn.microsoft.com/B2BF07B5-FA44-4994-9605-EFF4A0B9179F">Hyper-V Extensible Switch Forwarding Context</a>.




## -see-also




<b></b>



<a href="https://msdn.microsoft.com/C8A80DB2-4273-4FBA-82D4-4E8146812B16">AllocateNetBufferListForwardingContext</a>



<a href="https://msdn.microsoft.com/55B5C0B4-5359-410B-9110-79EDDBA3010C">GetNetBufferListDestinations</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598224">NDIS_SWITCH_PORT_DESTINATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598204">NdisFGetOptionalSwitchHandlers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561830">NdisFOidRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598264">OID_SWITCH_NIC_DELETE</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_UPDATE_NET_BUFFER_LIST_DESTINATIONS callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
