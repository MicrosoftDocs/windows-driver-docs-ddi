---
UID: NS:ndis._NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY
title: "_NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY" (ndis.h)
description: The NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY structure specifies an array of Hyper-V extensible switch destination ports for a packet.
old-location: netvista\ndis_switch_forwarding_destination_array.htm
tech.root: netvista
ms.assetid: f48b3b5f-000e-4e57-87b7-52ce542773f7
ms.date: 05/02/2018
ms.keywords: "*PNDIS_SWITCH_FORWARDING_DESTINATION_ARRAY, NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY, NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY structure [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_FORWARDING_DESTINATION_ARRAY, PNDIS_SWITCH_FORWARDING_DESTINATION_ARRAY structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY, ndis/NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY, ndis/PNDIS_SWITCH_FORWARDING_DESTINATION_ARRAY, netvista.ndis_switch_forwarding_destination_array"
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ndis.h
api_name:
-	NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY
product:
- Windows
targetos: Windows
req.typenames: NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY, *PNDIS_SWITCH_FORWARDING_DESTINATION_ARRAY
---

# _NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY structure


## -description



The <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure specifies an array of Hyper-V extensible switch destination ports for a packet.  Each element in the array is formatted as an <a href="https://msdn.microsoft.com/library/windows/hardware/hh598224">NDIS_SWITCH_PORT_DESTINATION</a> structure. 

This information is contained in the out-of-band (OOB) data of the packet's  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure.




## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure. This member is formatted as an <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value: 





#### NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY_REVISION_1.


### -field ElementSize

A ULONG value that specifies the size, in bytes, of each <a href="https://msdn.microsoft.com/library/windows/hardware/hh598224">NDIS_SWITCH_PORT_DESTINATION</a> element that follows the <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure. 


### -field NumElements

A ULONG value that specifies the total number of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598224">NDIS_SWITCH_PORT_DESTINATION</a> elements in the <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure. 

The value of the <b>NumElements</b> member specifies the number of currently used <a href="https://msdn.microsoft.com/library/windows/hardware/hh598224">NDIS_SWITCH_PORT_DESTINATION</a> elements (as specified by the <b>NumDestinations</b> member) plus the number of elements that are available for new destination ports. The number of unused <b>NDIS_SWITCH_PORT_DESTINATION</b> elements in the <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure is calculated by (<b>NumElements</b> - <b>NumDestinations</b>).


### -field NumDestinations

A ULONG value that specifies the number of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598224">NDIS_SWITCH_PORT_DESTINATION</a> elements in the <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure that specify port destinations. 

<div class="alert"><b>Note</b>  If <b>NumElements</b> is set to zero, this member is ignored.  </div>
<div> </div>

### -field FirstElement

A pointer to the first <a href="https://msdn.microsoft.com/library/windows/hardware/hh598224">NDIS_SWITCH_PORT_DESTINATION</a> element in the buffer that contains the <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure and all its elements.


## -remarks



The extensible switch extension can do the following with the destination ports  in a packet's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure:

<ul>
<li>
Query the current destination ports on the extensible switch that the packet will be forwarded to. 

The extensible switch extension calls the <a href="https://msdn.microsoft.com/55B5C0B4-5359-410B-9110-79EDDBA3010C">GetNetBufferListDestinations</a> function to obtain the array of port destinations for a packet. <i>GetNetBufferListDestinations</i> returns a pointer to the <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure in the <i>Destinations</i> parameter.

For more information, see <a href="https://msdn.microsoft.com/57D82C5E-3758-492C-A1DA-B7BC3DBE2E7A">Querying a Packet's Extensible Switch Destination Port Data</a>.

</li>
<li>
Add or modify the destination ports for the packet. 

After it queries the current destination ports for the packet, the extensible switch extension can do the following:

<ul>
<li>
A forwarding extension can add new destination ports to the <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure.

</li>
<li>
A filtering or forwarding extension can modify the data within an <a href="https://msdn.microsoft.com/library/windows/hardware/hh598224">NDIS_SWITCH_PORT_DESTINATION</a> structure for a destination port.

<div class="alert"><b>Note</b>  A filtering extension can only change the <b>IsExcluded</b> member of this structure. A forwarding extension can also change the <b>PreserveVLAN</b> and <b>PreservePriority</b> members.</div>
<div> </div>
</li>
</ul>
If the extension adds or modifies port destinations, it must call <a href="https://msdn.microsoft.com/9A740524-0FC1-4585-8059-F678D4777F66">UpdateNetBufferListDestinations</a> to commit the changes to the destination ports to the packet's OOB data in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure.

For more information, see <a href="https://msdn.microsoft.com/2781E64A-61D6-49A9-AD9B-F6B348560E30">Managing Hyper-V Extensible Switch Destination Port Data</a>.

</li>
</ul>
Extensible switch extensions can use the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598225">NDIS_SWITCH_PORT_DESTINATION_AT_ARRAY_INDEX</a> macro to access <a href="https://msdn.microsoft.com/library/windows/hardware/hh598224">NDIS_SWITCH_PORT_DESTINATION</a> elements in an <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> array.




## -see-also




<b></b>



<a href="https://msdn.microsoft.com/C921D9F8-B6FB-4B53-8CC5-CC941720FF37">Adding Extensible Switch Destination Port Data to a Packet</a>



<a href="https://msdn.microsoft.com/04BF02A6-360F-482E-A86B-31232AFCB778">Excluding Packet Delivery to Extensible Switch Destination Ports</a>



<a href="https://msdn.microsoft.com/7ABBB3F3-66F5-4651-8A5A-94940F3FD82D">Forwarding Extensions</a>



<a href="https://msdn.microsoft.com/55B5C0B4-5359-410B-9110-79EDDBA3010C">GetNetBufferListDestinations</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/hybrid-forwarding">Hybrid Forwarding</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598224">NDIS_SWITCH_PORT_DESTINATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598225">NDIS_SWITCH_PORT_DESTINATION_AT_ARRAY_INDEX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/78181C72-FBFD-4860-A664-C297997D780F">Overview of the Hyper-V Extensible Switch</a>



<a href="https://msdn.microsoft.com/9A740524-0FC1-4585-8059-F678D4777F66">UpdateNetBufferListDestinations</a>
 

 

