---
UID: NS:ndis._NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY
title: _NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY
author: windows-driver-content
description: The NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY structure specifies an array of Hyper-V extensible switch destination ports for a packet.
old-location: netvista\ndis_switch_forwarding_destination_array.htm
old-project: netvista
ms.assetid: f48b3b5f-000e-4e57-87b7-52ce542773f7
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY, NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY, *PNDIS_SWITCH_FORWARDING_DESTINATION_ARRAY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY
req.alt-loc: Ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section
req.typenames: NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY, *PNDIS_SWITCH_FORWARDING_DESTINATION_ARRAY
---

# _NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY structure



## -description

The <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure specifies an array of Hyper-V extensible switch destination ports for a packet.  Each element in the array is formatted as an <a href="..\ndis\ns-ndis-_ndis_switch_port_destination.md">NDIS_SWITCH_PORT_DESTINATION</a> structure. 

This information is contained in the out-of-band (OOB) data of the packet's  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.



The <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure specifies an array of Hyper-V extensible switch destination ports for a packet.  Each element in the array is formatted as an <a href="..\ndis\ns-ndis-_ndis_switch_port_destination.md">NDIS_SWITCH_PORT_DESTINATION</a> structure. 

This information is contained in the out-of-band (OOB) data of the packet's  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.



## -syntax

````
typedef struct _NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY {
  NDIS_OBJECT_HEADER Header;
  ULONG              ElementSize;
  ULONG              NumElements;
  USHORT             NumDestinations;
  PVOID              FirstElement;
} NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY, *PNDIS_SWITCH_FORWARDING_DESTINATION_ARRAY;
````


## -struct-fields

### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value: 




### -field NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY_REVISION_1.

</dd>
</dl>

### -field ElementSize

A ULONG value that specifies the size, in bytes, of each <a href="..\ndis\ns-ndis-_ndis_switch_port_destination.md">NDIS_SWITCH_PORT_DESTINATION</a> element that follows the <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure. 


### -field NumElements

A ULONG value that specifies the total number of <a href="..\ndis\ns-ndis-_ndis_switch_port_destination.md">NDIS_SWITCH_PORT_DESTINATION</a> elements in the <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure. 

The value of the <b>NumElements</b> member specifies the number of currently used <a href="..\ndis\ns-ndis-_ndis_switch_port_destination.md">NDIS_SWITCH_PORT_DESTINATION</a> elements (as specified by the <b>NumDestinations</b> member) plus the number of elements that are available for new destination ports. The number of unused <b>NDIS_SWITCH_PORT_DESTINATION</b> elements in the <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure is calculated by (<b>NumElements</b> - <b>NumDestinations</b>).


### -field NumDestinations

A ULONG value that specifies the number of <a href="..\ndis\ns-ndis-_ndis_switch_port_destination.md">NDIS_SWITCH_PORT_DESTINATION</a> elements in the <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure that specify port destinations. 

<div class="alert"><b>Note</b>  If <b>NumElements</b> is set to zero, this member is ignored.  </div>
<div> </div>

### -field FirstElement

A pointer to the first <a href="..\ndis\ns-ndis-_ndis_switch_port_destination.md">NDIS_SWITCH_PORT_DESTINATION</a> element in the buffer that contains the <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure and all its elements.


## -remarks
The extensible switch extension can do the following with the destination ports  in a packet's <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure:

Query the current destination ports on the extensible switch that the packet will be forwarded to. 

The extensible switch extension calls the <a href="https://msdn.microsoft.com/55B5C0B4-5359-410B-9110-79EDDBA3010C">GetNetBufferListDestinations</a> function to obtain the array of port destinations for a packet. <i>GetNetBufferListDestinations</i> returns a pointer to the <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure in the <i>Destinations</i> parameter.

For more information, see <a href="https://msdn.microsoft.com/57D82C5E-3758-492C-A1DA-B7BC3DBE2E7A">Querying a Packet's Extensible Switch Destination Port Data</a>.

Add or modify the destination ports for the packet. 

After it queries the current destination ports for the packet, the extensible switch extension can do the following:

A forwarding extension can add new destination ports to the <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure.

A filtering or forwarding extension can modify the data within an <a href="..\ndis\ns-ndis-_ndis_switch_port_destination.md">NDIS_SWITCH_PORT_DESTINATION</a> structure for a destination port.

If the extension adds or modifies port destinations, it must call <a href="https://msdn.microsoft.com/9A740524-0FC1-4585-8059-F678D4777F66">UpdateNetBufferListDestinations</a> to commit the changes to the destination ports to the packet's OOB data in the <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.

For more information, see <a href="https://msdn.microsoft.com/2781E64A-61D6-49A9-AD9B-F6B348560E30">Managing Hyper-V Extensible Switch Destination Port Data</a>.

Extensible switch extensions can use the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598225">NDIS_SWITCH_PORT_DESTINATION_AT_ARRAY_INDEX</a> macro to access <a href="..\ndis\ns-ndis-_ndis_switch_port_destination.md">NDIS_SWITCH_PORT_DESTINATION</a> elements in an <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> array.


## -see-also
<dl>
<dt><b></b></dt>
<dt>
<a href="https://msdn.microsoft.com/C921D9F8-B6FB-4B53-8CC5-CC941720FF37">Adding Extensible Switch Destination Port Data to a Packet</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/04BF02A6-360F-482E-A86B-31232AFCB778">Excluding Packet Delivery to Extensible Switch Destination Ports</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/7ABBB3F3-66F5-4651-8A5A-94940F3FD82D">Forwarding Extensions</a>
</dt>
<dt>
<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/hybrid-forwarding">Hybrid Forwarding</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/78181C72-FBFD-4860-A664-C297997D780F">Overview of the Hyper-V Extensible Switch</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/55B5C0B4-5359-410B-9110-79EDDBA3010C">GetNetBufferListDestinations</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_switch_port_destination.md">NDIS_SWITCH_PORT_DESTINATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598225">NDIS_SWITCH_PORT_DESTINATION_AT_ARRAY_INDEX</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/9A740524-0FC1-4585-8059-F678D4777F66">UpdateNetBufferListDestinations</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

