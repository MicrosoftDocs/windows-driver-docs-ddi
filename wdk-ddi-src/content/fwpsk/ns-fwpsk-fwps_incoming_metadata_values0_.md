---
UID: NS:fwpsk.FWPS_INCOMING_METADATA_VALUES0_
title: FWPS_INCOMING_METADATA_VALUES0_ (fwpsk.h)
description: The FWPS_INCOMING_METADATA_VALUES0 structure defines metadata values that the filter engine passes to a callout's classifyFn callout function.Note  FWPS_INCOMING_METADATA_VALUES0 is a specific version of FWPS_INCOMING_METADATA_VALUES.
old-location: netvista\fwps_incoming_metadata_values0.htm
tech.root: netvista
ms.assetid: fba7eb60-0d19-4bfd-b484-2e615d3e9237
ms.date: 05/02/2018
ms.keywords: FWPS_INCOMING_METADATA_VALUES0, FWPS_INCOMING_METADATA_VALUES0 structure [Network Drivers Starting with Windows Vista], FWPS_INCOMING_METADATA_VALUES0_, FWPS_L2_INCOMING_FLAG_IS_RAW_IPV4_FRAMING, FWPS_L2_INCOMING_FLAG_IS_RAW_IPV6_FRAMING, FWPS_L2_INCOMING_FLAG_RECLASSIFY_MULTI_DESTINATION, FWPS_L2_METADATA_FIELD_ETHERNET_MAC_HEADER_SIZE, FWPS_L2_METADATA_FIELD_VSWITCH_DESTINATION_PORT_ID, FWPS_L2_METADATA_FIELD_VSWITCH_PACKET_CONTEXT, FWPS_L2_METADATA_FIELD_VSWITCH_SOURCE_NIC_INDEX, FWPS_L2_METADATA_FIELD_VSWITCH_SOURCE_PORT_ID, FWPS_L2_METADATA_FIELD_WIFI_OPERATION_MODE, fwpsk/FWPS_INCOMING_METADATA_VALUES0, netvista.fwps_incoming_metadata_values0, wfp_ref_3_struct_3_fwps_F-O_ee69ce82-24a0-4757-bba4-f1abb3f00c8e.xml
ms.topic: struct
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with  Windows Vista.
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
-	fwpsk.h
api_name:
-	FWPS_INCOMING_METADATA_VALUES0
product:
- Windows
targetos: Windows
req.typenames: FWPS_INCOMING_METADATA_VALUES0
---

# FWPS_INCOMING_METADATA_VALUES0_ structure


## -description


The <b>FWPS_INCOMING_METADATA_VALUES0</b> structure defines metadata values that the filter engine passes to
  a callout's 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> callout function.
<div class="alert"><b>Note</b>  <b>FWPS_INCOMING_METADATA_VALUES0</b> is a specific version of <b>FWPS_INCOMING_METADATA_VALUES</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -struct-fields




### -field currentMetadataValues

A UINT32 value that contains a bitwise OR of a combination of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff559186">Metadata Field Identifiers</a> that
     specify which metadata values are set in the structure.


### -field flags

Used internally by the filter engine. Callout drivers should ignore this member.


### -field reserved

Reserved for system use. Callout drivers should ignore this member.


### -field discardMetadata

An 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff551235">FWPS_DISCARD_METADATA0</a> structure
     that describes the reason why the data was discarded. This member contains valid data only if the
     FWPS_METADATA_FIELD_DISCARD_REASON flag is set in the 
     <b>currentMetadataValues</b> member.


### -field flowHandle

A handle for the data flow. This member contains valid data only if the
     FWPS_METADATA_FIELD_FLOW_HANDLE flag is set in the 
     <b>currentMetadataValues</b> member.


### -field ipHeaderSize

The offset, in bytes, of the IP header.
     

On inbound paths, 
     <b>ipHeaderSize</b>, when used in conjunction with the 
     <b>transportHeaderSize</b> member, specifies the number of bytes to retreat from
     the data offset location to the beginning of the IP header.

On the following inbound ICMP error layers, 
     <b>ipHeaderSize</b> alone specifies the total number of bytes to retreat from the
     data offset to the beginning of the IP header:

FWPS_LAYER_INBOUND_ICMP_ERROR_V4

FWPS_LAYER_INBOUND_ICMP_ERROR_V6

FWPS_LAYER_INBOUND_ICMP_ERROR_V4_DISCARD

FWPS_LAYER_INBOUND_ICMP_ERROR_V6_DISCARD

On outbound paths, if 
     <b>ipHeaderSize</b> is greater than zero, it specifies the number of bytes to
     advance from the data offset location to the end of the IP header.

This member is not applicable to the outbound path at the following layers:

FWPS_LAYER_DATAGRAM_DATA_V4

FWPS_LAYER_DATAGRAM_DATA_V6

FWPS_LAYER_DATAGRAM_DATA_V4_DISCARD

FWPS_LAYER_DATAGRAM_DATA_V6_DISCARD

This member contains valid data only if the FWPS_METADATA_FIELD_IP_HEADER_SIZE flag is set in the 
     <b>currentMetadataValues</b> member.


### -field transportHeaderSize

The offset or size, in bytes, of the transport header.
     

On inbound paths, 
     <b>transportHeaderSize</b> specifies the number of bytes to retreat from the data
     offset location to the end of the transport header.

On the following inbound ICMP error layers, 
     <b>transportHeaderSize</b> specifies the size of the ICMP header:

FWPS_LAYER_INBOUND_ICMP_ERROR_V4

FWPS_LAYER_INBOUND_ICMP_ERROR_V6

FWPS_LAYER_INBOUND_ICMP_ERROR_V4_DISCARD

FWPS_LAYER_INBOUND_ICMP_ERROR_V6_DISCARD

On outbound paths, 
     <b>transportHeaderSize</b> specifies the number of bytes to advance from the data
     offset location to the end of the transport header.

This member contains valid data only if the FWPS_METADATA_FIELD_TRANSPORT_HEADER_SIZE flag is set in
     the 
     <b>currentMetadataValues</b> member.


### -field processPath

A pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff552427">FWP_BYTE_BLOB</a> structure that contains the
     full path to the process that owns the endpoint. This member contains valid data only if the
     FWPS_METADATA_FIELD_PROCESS_PATH flag is set in the 
     <b>currentMetadataValues</b> member.


### -field token

A handle for the token used to validate the permissions for the user. This member contains valid
     data only if the FWPS_METADATA_FIELD_TOKEN flag is set in the 
     <b>currentMetadataValues</b> member.


### -field processId

The process ID for the process that owns the endpoint. This member contains valid data only if the
     FWPS_METADATA_FIELD_PROCESS_ID flag is set in the 
     <b>currentMetadataValues</b> member.


### -field sourceInterfaceIndex

The index of the network interface where an incoming packet was received. This member contains
     valid data only if the FWPS_METADATA_FIELD_SOURCE_INTERFACE_INDEX flag is set in the 
     <b>currentMetadataValues</b> member.


### -field destinationInterfaceIndex

The index of the network interface where an outgoing packet is to be sent. This member contains
     valid data only if the FWPS_METADATA_FIELD_DESTINATION_INTERFACE_INDEX flag is set in the 
     <b>currentMetadataValues</b> member.


### -field compartmentId

The identifier of the routing compartment in which the packet either was received or is being
     sent. Any modified packets should be injected back into the same routing compartment that is indicated
     for the original packet. This member contains valid data only if the FWPS_METADATA_FIELD_COMPARTMENT_ID
     flag is set in the 
     <b>currentMetadataValues</b> member.


### -field fragmentMetadata

An 
     <a href="https://msdn.microsoft.com/9bead001-7ea7-4a51-8a7c-82fe01017dd7">
     FWPS_INBOUND_FRAGMENT_METADATA0</a> structure that describes the fragment data for a received packet
     fragment. This member contains valid data only if the FWPS_METADATA_FIELD_FRAGMENT_DATA flag is set in
     the 
     <b>currentMetadataValues</b> member.


### -field pathMtu

The path maximum transmission unit (path MTU) for an outbound packet. This value indicates the
     largest physical packet size, in bytes, that a network can transmit without fragmentation, This member
     contains valid data only if the FWPS_METADATA_FIELD_PATH_MTU flag is set in the 
     <b>currentMetadataValues</b> member.


### -field completionHandle

A completion handle that is required to pend the current filtering operation. This member contains
     valid data only if the FWPS_METADATA_FIELD_COMPLETION_HANDLE flag is set in the 
     <b>currentMetadataValues</b> member.


### -field transportEndpointHandle

An endpoint handle that indicates the end of the packet to be injected into the outbound transport
     layer. This member contains valid data only if the FWPS_METADATA_FIELD_TRANSPORT_ENDPOINT_HANDLE flag is
     set in the 
     <b>currentMetadataValues</b> member.


### -field remoteScopeId

The remote scope identifier to be used in outbound transport layer injection. This member contains
     valid data only if the FWPS_METADATA_FIELD_REMOTE_SCOPE_ID flag is set in the 
     <b>currentMetadataValues</b> member.


### -field controlData

An optional socket control data object. This member contains valid data only if the
     FWPS_METADATA_FIELD_TRANSPORT_CONTROL_DATA flag is set in the 
     <b>currentMetadataValues</b> member. For information about the WSACMSGHDR type,
     see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff544964">CMSGHDR</a>.


### -field controlDataLength

The length, in bytes, of the 
     <b>controlData</b> member.


### -field packetDirection

The direction of network traffic (inbound or outbound) as specified by one of the constant values of      
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff552433">FWP_DIRECTION</a>. This member is set at the
      application layer enforcement (ALE) connect or receive/accept layers during a reauthorization classify
      operation. For more information, see the Remarks section.

<div class="alert"><b>Note</b>  This member contains valid data only if the FWPS_METADATA_FIELD_PACKET_DIRECTION
      flag is set in the 
      <b>currentMetadataValues</b> member.</div>
<div> </div>

### -field headerIncludeHeader

A pointer to the IP header if the packet is sent from a raw socket.
     

<div class="alert"><b>Note</b>  Available only in Windows Server 2008, Windows Vista SP1, and later versions of
     Windows.</div>
<div> </div>

### -field headerIncludeHeaderLength

The length, in bytes, of the IP header that is pointed to by 
     <b>headerIncludeHeader</b>.
     

<div class="alert"><b>Note</b>  Available only in Windows Server 2008, Windows Vista SP1, and later versions of
     Windows.</div>
<div> </div>

### -field destinationPrefix

The destination prefix.
     

<div class="alert"><b>Note</b>  Available only in Windows 7 and later versions of Windows.</div>
<div> </div>

### -field frameLength

The frame length.
     

<div class="alert"><b>Note</b>  Available only in Windows 7 and later versions of Windows.</div>
<div> </div>

### -field parentEndpointHandle

The handle of the endpoint's parent.
     

<div class="alert"><b>Note</b>  Available only in Windows 7 and later versions of Windows.</div>
<div> </div>

### -field icmpIdAndSequence

The ICMP identifier and sequence.
     

<div class="alert"><b>Note</b>  Available only in Windows 7 and later versions of Windows.</div>
<div> </div>

### -field localRedirectTargetPID

The PID of the process that is responsible for a redirected connection.
     

<div class="alert"><b>Note</b>  Available only in Windows 7 and later versions of Windows.</div>
<div> </div>

### -field originalDestination

The original destination of a redirected connection.
     

<div class="alert"><b>Note</b>  Available only in Windows 7 and later versions of Windows.</div>
<div> </div>

### -field redirectRecords

A redirect records handle that can be passed to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439677">FwpsQueryConnectionRedirectState0</a> function to get the redirect state. 

<div class="alert"><b>Note</b>  Available only in <i>Windows 8</i> and later versions of Windows.</div>
<div> </div>

### -field currentL2MetadataValues

A bitmask that contains flags  that specify which layer 2 values are set. One or more values can be combined with a bitwise OR.

<div class="alert"><b>Note</b>  Available only in <i>Windows 8</i> and later versions of Windows.</div>
<div> </div>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="FWPS_L2_METADATA_FIELD_ETHERNET_MAC_HEADER_SIZE"></a><a id="fwps_l2_metadata_field_ethernet_mac_header_size"></a><dl>
<dt><b>FWPS_L2_METADATA_FIELD_ETHERNET_MAC_HEADER_SIZE</b></dt>
</dl>
</td>
<td width="60%">
The value of the  <b>ethernetMacHeaderSize</b> member indicates the size of the MAC header.

</td>
</tr>
<tr>
<td width="40%"><a id="FWPS_L2_METADATA_FIELD_WIFI_OPERATION_MODE"></a><a id="fwps_l2_metadata_field_wifi_operation_mode"></a><dl>
<dt><b>FWPS_L2_METADATA_FIELD_WIFI_OPERATION_MODE</b></dt>
</dl>
</td>
<td width="60%">
The value of the  <b>wiFiOperationMode</b> member indicates current Native 802.11  operation mode.

</td>
</tr>
<tr>
<td width="40%"><a id="FWPS_L2_METADATA_FIELD_VSWITCH_SOURCE_PORT_ID"></a><a id="fwps_l2_metadata_field_vswitch_source_port_id"></a><dl>
<dt><b>FWPS_L2_METADATA_FIELD_VSWITCH_SOURCE_PORT_ID</b></dt>
</dl>
</td>
<td width="60%">
The value of the  <b>vSwitchSourcePortId</b> member indicates  the identifier for the source port on the   virtual switch.

</td>
</tr>
<tr>
<td width="40%"><a id="FWPS_L2_METADATA_FIELD_VSWITCH_SOURCE_NIC_INDEX"></a><a id="fwps_l2_metadata_field_vswitch_source_nic_index"></a><dl>
<dt><b>FWPS_L2_METADATA_FIELD_VSWITCH_SOURCE_NIC_INDEX</b></dt>
</dl>
</td>
<td width="60%">
The value of the  <b>vSwitchSourceNicIndex</b> member indicates the index for the source NIC on the   virtual switch.

</td>
</tr>
<tr>
<td width="40%"><a id="FWPS_L2_METADATA_FIELD_VSWITCH_PACKET_CONTEXT"></a><a id="fwps_l2_metadata_field_vswitch_packet_context"></a><dl>
<dt><b>FWPS_L2_METADATA_FIELD_VSWITCH_PACKET_CONTEXT</b></dt>
</dl>
</td>
<td width="60%">
The value of the  <b>vSwitchPacketContext</b> member indicates a  HANDLE to the virtual switch packet context

</td>
</tr>
<tr>
<td width="40%"><a id="FWPS_L2_METADATA_FIELD_VSWITCH_DESTINATION_PORT_ID"></a><a id="fwps_l2_metadata_field_vswitch_destination_port_id"></a><dl>
<dt><b>FWPS_L2_METADATA_FIELD_VSWITCH_DESTINATION_PORT_ID</b></dt>
</dl>
</td>
<td width="60%">
The value of the  <b>vSwitchDestinationPortId</b> member indicates the identifier for the destination port on the   virtual switch.

</td>
</tr>
</table>
 


### -field l2Flags

A bitmask containing layer 2 flags that can be combined with a bitwise OR.
     

<div class="alert"><b>Note</b>  Available only in <i>Windows 8</i> and later versions of Windows.</div>
<div> </div>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="FWPS_L2_INCOMING_FLAG_IS_RAW_IPV4_FRAMING"></a><a id="fwps_l2_incoming_flag_is_raw_ipv4_framing"></a><dl>
<dt><b>FWPS_L2_INCOMING_FLAG_IS_RAW_IPV4_FRAMING</b></dt>
</dl>
</td>
<td width="60%">
Indicates raw IP4 framing.

</td>
</tr>
<tr>
<td width="40%"><a id="FWPS_L2_INCOMING_FLAG_IS_RAW_IPV6_FRAMING"></a><a id="fwps_l2_incoming_flag_is_raw_ipv6_framing"></a><dl>
<dt><b>FWPS_L2_INCOMING_FLAG_IS_RAW_IPV6_FRAMING</b></dt>
</dl>
</td>
<td width="60%">
Indicates raw IP6 framing.

</td>
</tr>
<tr>
<td width="40%"><a id="FWPS_L2_INCOMING_FLAG_RECLASSIFY_MULTI_DESTINATION"></a><a id="fwps_l2_incoming_flag_reclassify_multi_destination"></a><dl>
<dt><b>FWPS_L2_INCOMING_FLAG_RECLASSIFY_MULTI_DESTINATION</b></dt>
</dl>
</td>
<td width="60%">
This flag indicates that an NBL that was seen once at ingress has been distributed into multiple NBLs, each of which is destined to a different VM, and the first NBL of this distribution has already been indicated to your callout driver.

The first NBL of the distributed group will not have this flag set. All subsequent NBLs for the group will have this flag set.

For the purpose of injecting, your callout driver should clone the NBL, block and absorb the original packet, and clear the FWPS_RIGHT_ACTION_WRITE flag for the first indication. Then modify the clone and inject it into the ingress path.

For all subsequent indications, you should block and absorb the original packet and clear the FWPS_RIGHT_ACTION_WRITE flag for the clone. When the injected clone comes out of ingress, it will then be redistributed again, and all indications will have an injection state of FWPS_PACKET_INJECTED_BY_SELF or FWPS_PACKET_PREVIOUSLY_INJECTED_BY_SELF.

<div class="alert"><b>Note</b>  Available only in <i>Windows 8</i> and later versions of Windows.</div>
<div> </div>
</td>
</tr>
</table>
 


### -field ethernetMacHeaderSize

The size, in bytes,  of the MAC header if the FWPS_L2_METADATA_FIELD_802_3_MAC_HEADER_SIZE flag is set. This flag is set for the inbound 802.3 layer only.
     

<div class="alert"><b>Note</b>  Available only in <i>Windows 8</i> and later versions of Windows.</div>
<div> </div>

### -field wiFiOperationMode

The  current Native 802.11  operation mode  if the FWPS_L2_METADATA_FIELD_802_11_OPERATION_MODE flag is set. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547678">DOT11_CURRENT_OPERATION_MODE</a>.
     

<div class="alert"><b>Note</b>  Available only in <i>Windows 8</i> and later versions of Windows.</div>
<div> </div>

### -field vSwitchSourcePortId

A unique identifier for the source port on the   virtual switch. 

<div class="alert"><b>Note</b>  Available only in <i>Windows 8</i> and later versions of Windows.</div>
<div> </div>

### -field vSwitchSourceNicIndex

A index for the source NIC on the   virtual switch. 

<div class="alert"><b>Note</b>  Available only in <i>Windows 8</i> and later versions of Windows.</div>
<div> </div>

### -field vSwitchDestinationPortId

A unique identifier for the destination port on the   virtual switch. 

<div class="alert"><b>Note</b>  Available only in <i>Windows 8</i> and later versions of Windows.</div>
<div> </div>

### -field padding0

Reserved. 

<div class="alert"><b>Note</b>  Available only in <i>Windows 8</i> and later versions of Windows.</div>
<div> </div>

### -field padding1

Reserved. 

<div class="alert"><b>Note</b>  Available only in <i>Windows 8</i> and later versions of Windows.</div>
<div> </div>

### -field padding2

Reserved. 

<div class="alert"><b>Note</b>  Available only in <i>Windows 8</i> and later versions of Windows.</div>
<div> </div>

### -field vSwitchPacketContext

A handle to the virtual switch packet context. 

<div class="alert"><b>Note</b>  Available only in <i>Windows 8</i> and later versions of Windows.</div>
<div> </div>

### -field subProcessTag

Reserved. 

<div class="alert"><b>Note</b>  Available only in <i>Windows 8</i> and later versions of Windows.</div>
<div> </div>

### -field reserved1

 




#### - Reserved1

Reserved. 

<div class="alert"><b>Note</b>  Available only in <i>Windows 8</i> and later versions of Windows.</div>
<div> </div>

#### - l2ConnectionProfileIndex

A the layer 2 connection profile index. 

<div class="alert"><b>Note</b>  Available only in <i>Windows 8</i> and later versions of Windows.</div>
<div> </div>

## -remarks



The filter engine passes a pointer to an FWPS_INCOMING_METADATA_VALUES0 structure to a callout's 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> callout function. The metadata
    values contained in the structure are not processed by the filter engine but are supplied to a callout's 
    <i>classifyFn</i> callout function to provide
    additional information.

A callout driver can use the following macro to test if a specific metadata value is present in an
    FWPS_INCOMING_METADATA_VALUES0 structure:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>FWPS_IS_METADATA_FIELD_PRESENT(metadataValues, metadataField)</pre>
</td>
</tr>
</table></span></div>


If the FWPS_METADATA_FIELD_PACKET_DIRECTION metadata value is present in an
    FWPS_INCOMING_METADATA_VALUES0 structure, the 
    <b>packetDirection</b> member specifies whether the packet was inbound or outbound
    during a reauthorization classify operation. Otherwise, the FWPS_METADATA_FIELD_PACKET_DIRECTION metadata
    value is not present.

The callout driver must follow these guidelines when it inspects the packet:

<ul>
<li>At the ALE connect or receive/accept layers, the callout driver should not assume that the packet
     contains a valid IP header if 
     <b>packetDirection</b> is set to <b>FWP_DIRECTION_OUTBOUND</b> and the
     FWPS_METADATA_FIELD_PACKET_DIRECTION metadata value is present.</li>
<li>At the ALE connect layer, if the FWPS_METADATA_FIELD_PACKET_DIRECTION metadata value is not
     present, the callout driver should assume a packet direction of FWP_DIRECTION_OUTBOUND.</li>
<li>At the ALE receive/accept layer, if the FWPS_METADATA_FIELD_PACKET_DIRECTION metadata value is not
     present, the callout driver should assume a packet direction of FWP_DIRECTION_INBOUND.</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544964">CMSGHDR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551235">FWPS_DISCARD_METADATA0</a>



<a href="https://msdn.microsoft.com/9bead001-7ea7-4a51-8a7c-82fe01017dd7">
   FWPS_INBOUND_FRAGMENT_METADATA0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552427">FWP_BYTE_BLOB</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552433">FWP_DIRECTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439677">FwpsQueryConnectionRedirectState0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a>
 

 

