---
UID: NS:ntddndis._NDIS_PM_CAPABILITIES
title: _NDIS_PM_CAPABILITIES (ntddndis.h)
description: The NDIS_PM_CAPABILITIES structure specifies power management capabilities of a network adapter.
old-location: netvista\ndis_pm_capabilities.htm
tech.root: netvista
ms.assetid: 713c8ecc-e0a5-480a-9c53-e331aeaeb38e
ms.date: 05/02/2018
ms.keywords: "*PNDIS_PM_CAPABILITIES, NDIS_PM_CAPABILITIES, NDIS_PM_CAPABILITIES structure [Network Drivers Starting with Windows Vista], PNDIS_PM_CAPABILITIES, PNDIS_PM_CAPABILITIES structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PM_CAPABILITIES, miniport_power_management_ref_e70356b9-5c5a-4b38-b413-553a772da8b6.xml, netvista.ndis_pm_capabilities, ntddndis/NDIS_PM_CAPABILITIES, ntddndis/PNDIS_PM_CAPABILITIES"
ms.topic: struct
f1_keywords:
 - "ntddndis/NDIS_PM_CAPABILITIES"
req.header: ntddndis.h
req.include-header: Ntddndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddndis.h
api_name:
- NDIS_PM_CAPABILITIES
product:
- Windows
targetos: Windows
req.typenames: NDIS_PM_CAPABILITIES, *PNDIS_PM_CAPABILITIES
---

# _NDIS_PM_CAPABILITIES structure


## -description


The <b>NDIS_PM_CAPABILITIES</b> structure specifies power management capabilities of a network adapter.


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_PM_CAPABILITIES</b> structure. This member is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_PM_CAPABILITIES</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_PM_CAPABILITIES_REVISION_2

Added various changes for NDIS 6.30.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_PM_CAPABILITIES_REVISION_2.



#### NDIS_PM_CAPABILITIES_REVISION_1

Original version for NDIS 6.20.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_PM_CAPABILITIES_REVISION_1.


### -field Flags

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags. For NDIS 6.20, this member is reserved for NDIS.

Starting with NDIS 6.30, the following flags are defined:





#### NDIS_PM_WAKE_PACKET_INDICATION_SUPPORTED

If this flag is set, the network adapter must be able to save the received packet that caused the adapter to generate a wake-up event.

If this flag is set, the miniport driver must be able to do the following with this packet after the network adapter transitions to a full-power state:

<ul>
<li>
The miniport driver must be able to indicate the packet by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismindicatereceivenetbufferlists">NdisMIndicateReceiveNetBufferLists</a>.



</li>
<li>
The miniport driver must be able to issue an <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-pm-wake-reason">NDIS_STATUS_PM_WAKE_REASON</a> status indication and must pass the packet with the indication.



</li>
</ul>
For more information about this power management capability, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-wake-reason-status-indications-ref">NDIS Wake Reason Status Indications</a>.



#### NDIS_PM_SELECTIVE_SUSPEND_SUPPORTED

If this flag is set, the miniport driver supports NDIS selective suspend for network adapters. 

For more information about this power management capability, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_netvista/">NDIS Selective Suspend</a>.


### -field SupportedWoLPacketPatterns

A ULONG value that contains a bitwise OR of flags that specify the wake-on-LAN (WOL) patterns that
     a network adapter supports. Miniport drivers use these flags to advertise packet based WOL patterns that a network adapter
     supports. 
     

For more information about this member, see the Remarks section. For more information about WOL
     patterns, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_pm_wol_pattern">NDIS_PM_WOL_PATTERN</a>.





#### NDIS_PM_WOL_BITMAP_PATTERN_SUPPORTED

The network adapter can generate a wake-up event when it receives a packet that matches a
       configured bitmap pattern.



#### NDIS_PM_WOL_MAGIC_PACKET_SUPPORTED

The network adapter can generate a wake-up event when it receives a WOL magic packet. A 
       <i>magic packet</i> contains within its payload a string of six bytes with a value of 0xFF, followed
       immediately by 16 contiguous copies of the receiving network adapter's Ethernet address.



#### NDIS_PM_WOL_IPV4_TCP_SYN_SUPPORTED

The network adapter can generate a wake-up event when it receives an IPv4 TCP SYN packet.
       Remote hosts send TCP SYN packets to initiate a TCP connection to the local computer.



#### NDIS_PM_WOL_IPV6_TCP_SYN_SUPPORTED

The network adapter can generate a wake-up event when it receives an IPv6 TCP SYN
       packet.



#### NDIS_PM_WOL_IPV4_DEST_ADDR_WILDCARD_SUPPORTED

If this flag is set, the network adapter supports as 
        <i>wildcard values</i> any zero-filled, or 
        <i>unspecified</i>, values for IPv4 addresses and TCP/UDP ports in a WOL pattern.
        In this way, the wildcard value matches any IPv4 address and any port value of the incoming packet in
        the location that is specified by the WOL pattern.

When a network adapter supports an IPv4 based wake on LAN packet pattern, such as an IPv4 TCP SYN
        pattern, it must support the generation of a wake-up event if the IPv4 addresses and port values of
        the incoming packet match the ones that are specified in the wake-up pattern.

However, if the NDIS_PM_WOL_IPV4_DEST_ADDR_WILDCARD_SUPPORTED flag is set, the network adapter
        can also generate a wake-up event if the following pattern matching conditions are true:

<ul>
<li>
Any value from the incoming packet in the location that is specified by the WOL pattern is a match, if
          the WOL pattern for that location contains a wildcard value.

</li>
<li>
A value from the incoming packet in the location that is specified by the WOL pattern is a match if the
          WOL pattern for that location contains a nonzero value that equals the packet's value.

</li>
</ul>
The miniport driver must restrict wake-up events to the specified IPv4 addresses and ports unless
        an overlying driver enables this capability.

<div class="alert"><b>Note</b>  Wildcard values that are enabled by this flag can include unspecified IPv4
        source and destination addresses, as well as unspecified source and destination ports.</div>
<div> </div>


#### NDIS_PM_WOL_IPV6_DEST_ADDR_WILDCARD_SUPPORTED

If this flag is set, the network adapter supports as 
        <i>wildcard values</i> any zero-filled, or 
        <i>unspecified</i>, values for IPv6 addresses and TCP/UDP ports in a WOL pattern.
        In this way, the wildcard value matches any IPv6 address and any port value of the incoming packet in
        the location that is specified by the WOL pattern.

When a network adapter supports an IPv6 based wake on LAN packet pattern, such as an IPv6 TCP SYN
        pattern, it must support the generation of a wake-up event if the IPv6 addresses and port values of
        the incoming packet match the ones that are specified in the wake-up pattern.

However, if the NDIS_PM_WOL_IPV6_DEST_ADDR_WILDCARD_SUPPORTED flag is set, the network adapter
        can also generate a wake-up event if the following pattern matching conditions are true:

<ul>
<li>
Any value from the incoming packet in the location that is specified by the WOL pattern is a match, if
          the WOL pattern for that location contains a wildcard value.

</li>
<li>
A value from the incoming packet in the location that is specified by the WOL pattern is a match if the
          WOL pattern for that location contains a nonzero value that equals the packet's value.

</li>
</ul>
The miniport driver must restrict wake-up events to the specified IPv6 addresses and ports unless
        an overlying driver enables this capability.

<div class="alert"><b>Note</b>  Wildcard values that are enabled by this flag can include unspecified IPv6
        source and destination addresses, as well as unspecified source and destination ports.</div>
<div> </div>


#### NDIS_PM_WOL_EAPOL_REQUEST_ID_MESSAGE_SUPPORTED

The network adapter can generate a wake-up event when it receives an EAPOL request identifier
       message.


### -field NumTotalWoLPatterns

A <b>ULONG</b> value that contains the total number of WOL patterns that a network adapter supports. This is the sum of "number of
      supported WOL protocol patterns" and "number of supported WOL bitmap patterns."

For example, if  your driver supports 8 flexible bitmap patterns, IPv4 TCP SYN (via preset filter), and magic packet, then you would report 9 in NumTotalWoLPatterns. (8 bitmaps + 1 IPv4 TCP SYN = 9)

<div class="alert"><b>Note</b>  The total number of WOL patterns does not include the magic packet wake-up
      pattern.</div>
<div> </div>
For more information about WOL
     protocol patterns, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_pm_wol_pattern">NDIS_PM_WOL_PATTERN</a>.


### -field MaxWoLPatternSize

A ULONG value that contains the maximum number of bytes that can be compared with a
     pattern.


### -field MaxWoLPatternOffset

A ULONG value that contains the number of bytes in a packet that can be examined, starting at
     the beginning of the MAC header.


### -field MaxWoLPacketSaveBuffer

A ULONG value that contains the number of bytes of a WOL packet that a miniport driver can save to
     a buffer and indicate up the driver stack. This value must be less than or equal to the size, in bytes, of the maximum transmission unit (MTU)  for the network media. The driver reports the MTU size through OID query requests of <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-maximum-frame-size">OID_GEN_MAXIMUM_FRAME_SIZE</a>.

<div class="alert"><b>Note</b>  This member is ignored in NDIS 6.20 and earlier versions of NDIS. Starting with NDIS 6.30, this member must contain a nonzero value if the NDIS_PM_WAKE_PACKET_INDICATION_SUPPORTED flag is set in the <b>Flags</b> member.</div>
<div> </div>

### -field SupportedProtocolOffloads

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags that specify the protocol offload features that
     a network adapter supports. Miniport drivers use these flags to report the low power protocol offload capabilities
     of a network adapter. 
     





#### NDIS_PM_PROTOCOL_OFFLOAD_ARP_SUPPORTED

If this bit is set, the network adapter can respond to IPv4 ARP packets while it is in a low
       power state
       

For more information about the ARP protocol, see RFC 826.



#### NDIS_PM_PROTOCOL_OFFLOAD_NS_SUPPORTED

If this bit is set, the network adapter can respond to IPv6 Neighbor Solicitation (NS) packets
       while it is in a low power state. 
       

For more information about IPv6 NS messages, see <a href="https://go.microsoft.com/fwlink/p/?linkid=268370">RFC 4861</a>.



#### NDIS_PM_PROTOCOL_OFFLOAD_80211_RSN_REKEY_SUPPORTED

The network adapter can respond to IEEE 802.11i Robust Security Network (RSN) re-key requests
       while it is in a low power state.


### -field NumArpOffloadIPv4Addresses

A <b>ULONG</b> value that contains the number of IPv4 addresses that the adapter supports for ARP
     offload.


### -field NumNSOffloadIPv6Addresses

A <b>ULONG</b> value that contains the number of IPv6 NS offload requests that the adapter supports. This should be at least 2.

<div class="alert"><b>Note</b>  Despite its name, the <b>NumNSOffloadIPv6Addresses</b> contains the number of supported requests, not addresses.</div>
<div> </div>

### -field MinMagicPacketWakeUp

Specifies the lowest device power state from which a network adapter can signal a wake-up event on receipt of
     a magic packet. A 
     <i>magic packet</i> contains within its payload a string of six bytes with a value of 0xFF, followed
     immediately by 16 contiguous copies of the receiving network adapter's MAC address.
     

<div class="alert"><b>Note</b>  Device power states are specified by a value of D<i>x</i>, where D0 is the highest device power state and D3 is the lowest device power state.</div>
<div> </div>
The device power state is specified as one of the following <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ne-ntddndis-_ndis_device_power_state">NDIS_DEVICE_POWER_STATE</a> values:





#### NdisDeviceStateUnspecified

The network adapter does not support magic packet wake-ups.

<div class="alert"><b>Note</b>  If the <b>MinMagicPacketWakeUp</b> member is set to this value, the NDIS_PM_WOL_MAGIC_PACKET_SUPPORTED flag must not be set in the <b>SupportedWoLPacketPatterns</b> member.</div>
<div> </div>


#### NdisDeviceStateD0

The network adapter can signal a magic packet wake-up from device power state D0. Because D0 is the fully
       powered state, this does not cause a wake-up, but can be used as a run-time event.

<div class="alert"><b>Note</b>  Starting with NDIS 6.20, signaling a magic packet wake-up from NdisDeviceStateD0 is no longer supported.</div>
<div> </div>


#### NdisDeviceStateD1

The network adapter can signal a magic packet wake-up from a device power state of D1.



#### NdisDeviceStateD2

The network adapter can signal a magic packet wake-up from a device state of D2.



#### NdisDeviceStateD3

The network adapter can signal a magic packet wake-up from a device power state  of D3.


### -field MinPatternWakeUp

Specifies the lowest device power state from which a network adapter can signal a wake-up event on receipt of
     a network frame that contains a pattern that is specified by the protocol driver. The power state is
     specified as one of the following <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ne-ntddndis-_ndis_device_power_state">NDIS_DEVICE_POWER_STATE</a> values:
     





#### NdisDeviceStateUnspecified

The network adapter does not support pattern-match wake-ups.

<div class="alert"><b>Note</b>  If the <b>MinPatternWakeUp</b> member is set to this value, only the NDIS_PM_WOL_MAGIC_PACKET_SUPPORTED flag can be set in the <b>SupportedWoLPacketPatterns </b> member.</div>
<div> </div>


#### NdisDeviceStateD0

The network adapter can signal a pattern-match wake-up from device power state D0. Because D0 is the fully
       powered state, this does not cause a wake-up but can be used as a run-time event.

<div class="alert"><b>Note</b>  Starting with NDIS 6.20, signaling a pattern-match wake-up from NdisDeviceStateD0 is no longer supported.</div>
<div> </div>


#### NdisDeviceStateD1

The network adapter can signal a pattern-match wake-up from a device power state of D1.



#### NdisDeviceStateD2

The network adapter can signal a pattern-match wake-up from a device power state of D2.



#### NdisDeviceStateD3

The network adapter can signal a pattern-match wake-up from a device power state of D3.


### -field MinLinkChangeWakeUp

Starting with NDIS 6.20, this member specifies the lowest device power state from which a network adapter can signal a wake-up event when the link
     state changes from media disconnected to media connected. 

Starting with NDIS 6.30, this member specifies the lowest device power state from which a network adapter can signal    wake-up events. These events are specified in the  <b>SupportedWakeUpEvents</b> member.

The power state is specified as one of the
     following <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ne-ntddndis-_ndis_device_power_state">NDIS_DEVICE_POWER_STATE</a> values:
     





#### NdisDeviceStateUnspecified

The network adapter does not support link change wake-ups.

<div class="alert"><b>Note</b>  If the <b>MinLinkChangeWakeUp</b> member is set to this value, the<b>SupportedWakeUpEvents</b> member must be set to zero.</div>
<div> </div>


#### NdisDeviceStateD0

The network adapter can signal a link change wake-up from device power state D0. Because D0 is the fully
       powered state, this does not cause a wake-up but can be used as a run-time event.

<div class="alert"><b>Note</b>  Starting with NDIS 6.20, signaling a link change wake-up from NdisDeviceStateD0 is no longer supported.</div>
<div> </div>


#### NdisDeviceStateD1

The network adapter can signal a link change wake-up from a device power state of D1.



#### NdisDeviceStateD2

The network adapter can signal a link change wake-up from a device power state of D2.



#### NdisDeviceStateD3

The network adapter can signal a link change wake-up from a device power state of D3.


### -field SupportedWakeUpEvents

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags. These flags specify the   media-independent wake-up events that a network adapter supports. 
     These events are not specific to media type.

Starting with NDIS 6.30, the following flags are defined:





#### NDIS_PM_WAKE_ON_MEDIA_CONNECT_SUPPORTED

If this flag is set, the network adapter can generate a wake-up event when it becomes connected to the networking interface.



#### NDIS_PM_WAKE_ON_MEDIA_DISCONNECT_SUPPORTED

If this flag is set, the network adapter can generate a wake-up event when it becomes disconnected to the networking interface.


### -field MediaSpecificWakeUpEvents

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags. These flags specify the media-specific wake-up events that a network adapter supports. 
     

Starting with NDIS 6.30, the following flags are defined:





#### NDIS_WLAN_WAKE_ON_NLO_DISCOVERY_SUPPORTED

If this flag is set, the 802.11 network adapter can generate a wake-up event if it detects a service set identifier (SSID) that was specified through a network list offload (NLO). 

For more information about NLO, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wi-fi-network-list-offload">Wi-Fi Network List Offload</a>.



#### NDIS_WLAN_WAKE_ON_AP_ASSOCIATION_LOST_SUPPORTED

If this flag is set, the 802.11 network adapter can generate a wake-up event if it disassociates with the access point (AP).



#### NDIS_WLAN_WAKE_ON_GTK_HANDSHAKE_ERROR_SUPPORTED

If this flag is set, the 802.11 network adapter can generate a wake-up event if it encounters an error during the IEEE 802.11i RSN group transient key (GTK) handshake with the AP.



#### NDIS_WLAN_WAKE_ON_4WAY_HANDSHAKE_REQUEST_SUPPORTED

If this flag is set, the 802.11 network adapter can generate a wake-up event if it receives the first frame of the IEEE 802.11i RSN 4-way handshake with the AP. This handshake is performed when the adapter authenticates with the AP.



#### NDIS_WWAN_WAKE_ON_REGISTER_STATE_SUPPORTED

If this flag is set, the mobile broadband (MB) network adapter can generate a wake-up event if its registration state to the MB Service has changed.



#### NDIS_WWAN_WAKE_ON_SMS_RECEIVE_SUPPORTED

If this flag is set, the MB network adapter can generate a wake-up event if the MB Service has to be notified about the receipt of a Short Message Service (SMS) message. The adapter generates this wake-up event either after the completion of a previously issued <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-sms-read">OID_WWAN_SMS_READ</a> query request, or the arrival of a new class-0 (flash/alert) message from the network provider as an event notification.



#### NDIS_WWAN_WAKE_ON_USSD_RECEIVE_SUPPORTED

If this flag is set, the MB network adapter can generate a wake-up event if it receives an Unstructured Supplementary Service Data (USSD) message.


## -remarks



The <b>NDIS_PM_CAPABILITIES</b> structure is used in the 
    <b>PowerManagementCapabilitiesEx</b> member of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_adapter_general_attributes">
    NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</a> and 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_bind_parameters">NDIS_BIND_PARAMETERS</a> structures and in
    the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-pm-capabilities-change">
    NDIS_STATUS_PM_CAPABILITIES_CHANGE</a> status indication.

During miniport initialization, the miniport driver initializes an <b>NDIS_PM_CAPABILITIES</b> structure with
    the power management capabilities of the network adapter hardware. The miniport driver then sets the 
    <b>PowerManagementCapabilitiesEx</b> member of the NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES structure to
    point to the initialized <b>NDIS_PM_CAPABILITIES</b> structure.

An overlying driver should not try to enable capabilities that a network adapter does not support. To
    allow an overlying driver to determine what capabilities a network adapter provides, NDIS provides the
    capabilities in the 
    <b>PowerManagementCapabilitiesEx</b> member of the NDIS_BIND_PARAMETERS structure.

<div class="alert"><b>Note</b>  NDIS 6.20 drivers must use the 
    <b>PowerManagementCapabilitiesEx</b> member instead of the 
    <b>PowerManagementCapabilities</b> member.</div>
<div> </div>
The 
    <b>SupportedProtocolOffloads</b> member contains flags that specify the protocol offload features that a
    network adapter supports. The network adapter handles these protocols in a low power state. For example, if the network adapter hardware can
    handle IPv4 ARP packets for the driver stack while it is in a low power state, the miniport driver sets
    the NDIS_PM_PROTOCOL_OFFLOAD_ARP_SUPPORTED bit in 
    <b>SupportedProtocolOffloads</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_bind_parameters">NDIS_BIND_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_adapter_general_attributes">
   NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_pm_wol_pattern">NDIS_PM_WOL_PATTERN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-pm-capabilities-change">
   NDIS_STATUS_PM_CAPABILITIES_CHANGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-pm-wake-reason">NDIS_STATUS_PM_WAKE_REASON</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismindicatereceivenetbufferlists">NdisMIndicateReceiveNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismindicatestatusex">NdisMIndicateStatusEx</a>
 

 

