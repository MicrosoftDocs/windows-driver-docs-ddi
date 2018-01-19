---
UID: NS:fwpsk.FWPS_INCOMING_METADATA_VALUES0_
title: FWPS_INCOMING_METADATA_VALUES0_
author: windows-driver-content
description: The FWPS_INCOMING_METADATA_VALUES0 structure defines metadata values that the filter engine passes to a callout's classifyFn callout function.Note  FWPS_INCOMING_METADATA_VALUES0 is a specific version of FWPS_INCOMING_METADATA_VALUES.
old-location: netvista\fwps_incoming_metadata_values0.htm
old-project: netvista
ms.assetid: fba7eb60-0d19-4bfd-b484-2e615d3e9237
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: FWPS_INCOMING_METADATA_VALUES0_, FWPS_INCOMING_METADATA_VALUES0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with  Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FWPS_INCOMING_METADATA_VALUES0
req.alt-loc: fwpsk.h
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
req.typenames: FWPS_INCOMING_METADATA_VALUES0
---

# FWPS_INCOMING_METADATA_VALUES0_ structure



## -description
The <b>FWPS_INCOMING_METADATA_VALUES0</b> structure defines metadata values that the filter engine passes to
  a callout's 
  <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> callout function.



## -syntax

````
typedef struct FWPS_INCOMING_METADATA_VALUES0_ {
  UINT32                          currentMetadataValues;
  UINT32                          flags;
  UINT64                          reserved;
  FWPS_DISCARD_METADATA0          discardMetadata;
  UINT64                          flowHandle;
  UINT32                          ipHeaderSize;
  UINT32                          transportHeaderSize;
  FWP_BYTE_BLOB                   *processPath;
  UINT64                          token;
  UINT64                          processId;
  UINT32                          sourceInterfaceIndex;
  UINT32                          destinationInterfaceIndex;
  ULONG                           compartmentId;
  FWPS_INBOUND_FRAGMENT_METADATA0 fragmentMetadata;
  ULONG                           pathMtu;
  HANDLE                          completionHandle;
  UINT64                          transportEndpointHandle;
  SCOPE_ID                        remoteScopeId;
  WSACMSGHDR                      *controlData;
  ULONG                           controlDataLength;
  FWP_DIRECTION                   packetDirection;
#if (NTDDI_VERSION >= NTDDI_WIN6SP1)
  PVOID                           headerIncludeHeader;
  ULONG                           headerIncludeHeaderLength;
#if (NTDDI_VERSION >= NTDDI_WIN7)
  IP_ADDRESS_PREFIX               destinationPrefix;
  UINT16                          frameLength;
  UINT64                          parentEndpointHandle;
  UINT32                          icmpIdAndSequence;
  DWORD                           localRedirectTargetPID;
  SOCKADDR                        *originalDestination;
#if (NTDDI_VERSION >= NTDDI_WIN8)
  HANDLE                          redirectRecords;
  UINT32                          currentL2MetadataValues;
  UINT32                          l2Flags;
  UINT32                          ethernetMacHeaderSize;
  UINT32                          wiFiOperationMode;
#if (NDIS_SUPPORT_NDIS630)
  NDIS_SWITCH_PORT_ID             vSwitchSourcePortId;
  NDIS_SWITCH_NIC_INDEX           vSwitchSourceNicIndex;
  NDIS_SWITCH_PORT_ID             vSwitchDestinationPortId;
#else 
  UINT32                          padding0;
  USHORT                          padding1;
  UINT32                          padding2;
#endif 
  HANDLE                          vSwitchPacketContext;
  UINT32                          l2ConnectionProfileIndex;
#endif 
#endif 
#endif 
#if (NTDDI_VERSION >= NTDDI_WIN8)
  PVOID                           subProcessTag;
  UINT64                          Reserved1;
#endif 
} FWPS_INCOMING_METADATA_VALUES0;
````


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

<dl>
<dd>
FWPS_LAYER_INBOUND_ICMP_ERROR_V4

</dd>
<dd>
FWPS_LAYER_INBOUND_ICMP_ERROR_V6

</dd>
<dd>
FWPS_LAYER_INBOUND_ICMP_ERROR_V4_DISCARD

</dd>
<dd>
FWPS_LAYER_INBOUND_ICMP_ERROR_V6_DISCARD

</dd>
</dl>
On outbound paths, if 
     <b>ipHeaderSize</b> is greater than zero, it specifies the number of bytes to
     advance from the data offset location to the end of the IP header.

This member is not applicable to the outbound path at the following layers:

<dl>
<dd>
FWPS_LAYER_DATAGRAM_DATA_V4

</dd>
<dd>
FWPS_LAYER_DATAGRAM_DATA_V6

</dd>
<dd>
FWPS_LAYER_DATAGRAM_DATA_V4_DISCARD

</dd>
<dd>
FWPS_LAYER_DATAGRAM_DATA_V6_DISCARD

</dd>
</dl>
This member contains valid data only if the FWPS_METADATA_FIELD_IP_HEADER_SIZE flag is set in the 
     <b>currentMetadataValues</b> member.


### -field transportHeaderSize

The offset or size, in bytes, of the transport header.
     

On inbound paths, 
     <b>transportHeaderSize</b> specifies the number of bytes to retreat from the data
     offset location to the end of the transport header.

On the following inbound ICMP error layers, 
     <b>transportHeaderSize</b> specifies the size of the ICMP header:

<dl>
<dd>
FWPS_LAYER_INBOUND_ICMP_ERROR_V4

</dd>
<dd>
FWPS_LAYER_INBOUND_ICMP_ERROR_V6

</dd>
<dd>
FWPS_LAYER_INBOUND_ICMP_ERROR_V4_DISCARD

</dd>
<dd>
FWPS_LAYER_INBOUND_ICMP_ERROR_V6_DISCARD

</dd>
</dl>
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

A redirect records handle that can be passed to the <a href="..\fwpsk\nf-fwpsk-fwpsqueryconnectionredirectstate0.md">FwpsQueryConnectionRedirectState0</a> function to get the redirect state. 

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

### -field FWPS_L2_METADATA_FIELD_ETHERNET_MAC_HEADER_SIZE

</td>
<td width="60%">
The value of the  <b>ethernetMacHeaderSize</b> member indicates the size of the MAC header.

</td>
</tr>
<tr>

### -field FWPS_L2_METADATA_FIELD_WIFI_OPERATION_MODE

</td>
<td width="60%">
The value of the  <b>wiFiOperationMode</b> member indicates current Native 802.11  operation mode.

</td>
</tr>
<tr>

### -field FWPS_L2_METADATA_FIELD_VSWITCH_SOURCE_PORT_ID

</td>
<td width="60%">
The value of the  <b>vSwitchSourcePortId</b> member indicates  the identifier for the source port on the   virtual switch.

</td>
</tr>
<tr>

### -field FWPS_L2_METADATA_FIELD_VSWITCH_SOURCE_NIC_INDEX

</td>
<td width="60%">
The value of the  <b>vSwitchSourceNicIndex</b> member indicates the index for the source NIC on the   virtual switch.

</td>
</tr>
<tr>

### -field FWPS_L2_METADATA_FIELD_VSWITCH_PACKET_CONTEXT

</td>
<td width="60%">
The value of the  <b>vSwitchPacketContext</b> member indicates a  HANDLE to the virtual switch packet context

</td>
</tr>
<tr>

### -field FWPS_L2_METADATA_FIELD_VSWITCH_DESTINATION_PORT_ID

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

### -field FWPS_L2_INCOMING_FLAG_IS_RAW_IPV4_FRAMING

</td>
<td width="60%">
Indicates raw IP4 framing.

</td>
</tr>
<tr>

### -field FWPS_L2_INCOMING_FLAG_IS_RAW_IPV6_FRAMING

</td>
<td width="60%">
Indicates raw IP6 framing.

</td>
</tr>
<tr>

### -field FWPS_L2_INCOMING_FLAG_RECLASSIFY_MULTI_DESTINATION

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

The  current Native 802.11  operation mode  if the FWPS_L2_METADATA_FIELD_802_11_OPERATION_MODE flag is set. For more information, see <a href="..\windot11\ns-windot11-_dot11_current_operation_mode.md">DOT11_CURRENT_OPERATION_MODE</a>.
     

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

### -field l2ConnectionProfileIndex

A the layer 2 connection profile index. 

<div class="alert"><b>Note</b>  Available only in <i>Windows 8</i> and later versions of Windows.</div>
<div> </div>

### -field subProcessTag

Reserved. 

<div class="alert"><b>Note</b>  Available only in <i>Windows 8</i> and later versions of Windows.</div>
<div> </div>

### -field Reserved1

Reserved. 

<div class="alert"><b>Note</b>  Available only in <i>Windows 8</i> and later versions of Windows.</div>
<div> </div>

## -remarks
The filter engine passes a pointer to an FWPS_INCOMING_METADATA_VALUES0 structure to a callout's 
    <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> callout function. The metadata
    values contained in the structure are not processed by the filter engine but are supplied to a callout's 
    <i>classifyFn</i> callout function to provide
    additional information.

A callout driver can use the following macro to test if a specific metadata value is present in an
    FWPS_INCOMING_METADATA_VALUES0 structure:



A pointer to an FWPS_INCOMING_METADATA_VALUES0 structure.

The metadata field identifier for the metadata value being tested. See 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff559186">Metadata Field Identifiers</a> for a
      list of the metadata field identifiers.

If the FWPS_METADATA_FIELD_PACKET_DIRECTION metadata value is present in an
    FWPS_INCOMING_METADATA_VALUES0 structure, the 
    <b>packetDirection</b> member specifies whether the packet was inbound or outbound
    during a reauthorization classify operation. Otherwise, the FWPS_METADATA_FIELD_PACKET_DIRECTION metadata
    value is not present.

The callout driver must follow these guidelines when it inspects the packet:


## -see-also
<dl>
<dt>
<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544964">CMSGHDR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552427">FWP_BYTE_BLOB</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552433">FWP_DIRECTION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551235">FWPS_DISCARD_METADATA0</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/9bead001-7ea7-4a51-8a7c-82fe01017dd7">
   FWPS_INBOUND_FRAGMENT_METADATA0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsqueryconnectionredirectstate0.md">FwpsQueryConnectionRedirectState0</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_INCOMING_METADATA_VALUES0 structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

