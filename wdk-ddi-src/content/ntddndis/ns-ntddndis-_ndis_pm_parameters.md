---
UID: NS:ntddndis._NDIS_PM_PARAMETERS
title: _NDIS_PM_PARAMETERS (ntddndis.h)
description: The NDIS_PM_PARAMETERS structure specifies the current or new power management hardware capabilities that are enabled for a network adapter.
old-location: netvista\ndis_pm_parameters.htm
tech.root: netvista
ms.assetid: 7747645c-398f-434e-9f0c-21b6d3c7d963
ms.date: 05/02/2018
ms.keywords: "*PNDIS_PM_PARAMETERS, NDIS_PM_PARAMETERS, NDIS_PM_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_PM_PARAMETERS, PNDIS_PM_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PM_PARAMETERS, miniport_power_management_ref_dc82d32a-ee0e-4167-b322-f0b91ece8002.xml, netvista.ndis_pm_parameters, ntddndis/NDIS_PM_PARAMETERS, ntddndis/PNDIS_PM_PARAMETERS"
ms.topic: struct
f1_keywords:
 - "ntddndis/NDIS_PM_PARAMETERS"
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
- NDIS_PM_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_PM_PARAMETERS, *PNDIS_PM_PARAMETERS
---

# _NDIS_PM_PARAMETERS structure


## -description


The <b>NDIS_PM_PARAMETERS</b> structure specifies the current or new power management hardware capabilities
  that are enabled for a network adapter.


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_PM_PARAMETERS</b> structure. This member is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_PM_PARAMETERS</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 

#### NDIS_PM_PARAMETERS_REVISION_2

Added various changes for NDIS 6.30.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_PM_CAPABILITIES_REVISION_2.



#### NDIS_PM_PARAMETERS_REVISION_1

Original version for NDIS 6.20.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_PM_CAPABILITIES_REVISION_1.


### -field EnabledWoLPacketPatterns

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags that correspond to capabilities that the
     miniport driver reported in the 
     <b>SupportedWoLPacketPatterns</b> member of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_pm_capabilities">NDIS_PM_CAPABILITIES</a> structure. NDIS
     uses these flags to enable the wake-on-LAN (WOL) patterns that a network adapter uses to wake the local
     computer from a low power state. For more information about WOL patterns, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_pm_wol_pattern">NDIS_PM_WOL_PATTERN</a>.     

The following flags are used:


#### NDIS_PM_WOL_BITMAP_PATTERN_ENABLED

If this flag is set, the network adapter is enabled to generate a wake-up event when it receives a packet that matches a configured bitmap pattern.



#### NDIS_PM_WOL_MAGIC_PACKET_ENABLED

If this flag is set, the network adapter is enabled to generate a wake-up event when it receives a WOL magic packet. A 
       <i>magic packet</i> contains within its payload a string of six bytes with a value of 0xFF, followed
       immediately by 16 contiguous copies of the receiving network adapter's media access control (MAC) address.



#### NDIS_PM_WOL_EAPOL_REQUEST_ID_MESSAGE_ENABLED

If this flag is set, the network adapter is enabled to generate a wake-up event when it receives an EAPOL request identifier message.



#### NDIS_PM_WOL_IPV4_TCP_SYN_ENABLED

If this flag is set, the network adapter is enabled to generate a wake-up event when it receives an IPv4 TCP SYN packet. Remote hosts send TCP SYN packets to
       initiate a TCP connection to the local computer.



#### NDIS_PM_WOL_IPV6_TCP_SYN_ENABLED

If this flag is set, the network adapter is enabled to generate a wake-up event when it receives an IPv6 TCP SYN packet.



#### NDIS_PM_WOL_IPV4_DEST_ADDR_WILDCARD_ENABLED

If this flag is set, the network adapter must treat as 
        <i>wildcard</i> values any zero-filled, or 
        <i>unspecified</i>, values for IPv4 addresses and TCP/UDP ports in a WOL pattern.
        In this way, the wildcard value matches any IPv4 address and any port value of the incoming packet in
        the location specified by the WOL pattern.

If this flag is set, the network adapter is enabled to generate a wake-up event if the following pattern-matching
        conditions are true:

<ul>
<li>
Any value from the incoming packet in the location specified by the WOL pattern is a match, if
          the WOL pattern for that location contains a wildcard value.

</li>
<li>
A value from the incoming packet in the location specified by the WOL pattern is a match if the
          WOL pattern for that location contains a nonzero value that equals the packet's value.

</li>
</ul>

> [!NOTE]
> Wildcard values that are enabled by this flag can include unspecified IPv4 source and destination addresses, as well as unspecified source and destination ports.

#### NDIS_PM_WOL_IPV6_DEST_ADDR_WILDCARD_ENABLED

If this flag is set, the network adapter must treat as 
        <i>wildcard</i> values any zero-filled, or 
        <i>unspecified</i>, values for IPv6 addresses and TCP/UDP ports in a WOL pattern.
        In this way, the wildcard value matches any IPv6 address and any port value of the incoming packet in
        the location specified by the WOL pattern.

If this flag is set, the network adapter is enabled to generate a wake-up event if the following pattern-matching
        conditions are true:

<ul>
<li>
Any value from the incoming packet in the location specified by the WOL pattern is a match, if
          the WOL pattern for that location contains a wildcard value.

</li>
<li>
A value from the incoming packet in the location specified by the WOL pattern is a match if the
          WOL pattern for that location contains a nonzero value that equals the packet's value.

</li>
</ul>

> [!NOTE]
> Wildcard values that are enabled by this flag can include unspecified IPv6 source and destination addresses, as well as unspecified source and destination ports.



### -field EnabledProtocolOffloads

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags that correspond to capabilities that the
     miniport driver reported in the 
     <b>SupportedProtocolOffloads</b> member of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_pm_capabilities">NDIS_PM_CAPABILITIES</a> structure. NDIS
     uses these flags to enable the low power protocol offload capabilities on a network adapter. The
     following flags are used:
     





#### NDIS_PM_PROTOCOL_OFFLOAD_ARP_ENABLED

If this bit is set, the overlying driver will request the network adapter to enable the ARP
       protocol offload capability. As soon as this protocol offload has been configured by a set request of 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-pm-add-protocol-offload">OID_PM_ADD_PROTOCOL_OFFLOAD</a>,
       the driver should enable the network adapter to respond to IPv4 ARP packets while it is in a low-power
       state.



#### NDIS_PM_PROTOCOL_OFFLOAD_NS_ENABLED

If this bit is set, the overlying driver will request the network adapter to enable the IPv6
       Neighbor Solicitation (NS) protocol offload capability. As soon as this protocol offload has been
       configured by a set request of 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-pm-add-protocol-offload">OID_PM_ADD_PROTOCOL_OFFLOAD</a>,
       the driver should enable the network adapter to respond to NS packets while it is in a low-power state.



#### NDIS_PM_PROTOCOL_OFFLOAD_80211_RSN_REKEY_ENABLED

If this bit is set, the overlying driver will request the network adapter to enable the IEEE
       802.11i Robust Security Network (RSN) protocol offload capability. As soon as this protocol offload
       has been configured by a set request of 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-pm-add-protocol-offload">OID_PM_ADD_PROTOCOL_OFFLOAD</a>,
       the driver should enable the network adapter to respond to RSN re-key requests packets while it is in a low power
       state.


### -field WakeUpFlags

A ULONG value that contains a bitwise OR of NDIS_PM_WAKE_ON_
     <i>Xxx</i> flags. NDIS uses these flags to enable wake-up capabilities on
     a network adapter. This member uses the following flags:
     





#### NDIS_PM_WAKE_ON_LINK_CHANGE_ENABLED

If this flag is set, the network adapter is enabled to generate a wake-up event when the link state changes from
       media disconnected to media connected. 
       

For more information about this WOL capability, see 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/network/low-power-on-media-disconnect">Low Power on Media
       Disconnect</a>.



#### NDIS_PM_WAKE_ON_MEDIA_DISCONNECT_ENABLED

If this flag is set, the network adapter is enabled to generate a wake-up event when the link state changes from
       media connected to media disconnected.



#### NDIS_PM_SELECTIVE_SUSPEND_ENABLED

If this flag is set, the  network adapter is enabled to generate a wake-up event whenever  one of the following events occurs:

<ul>
<li>
The network adapter receives a packet that matches a receive packet filter. The adapter is configured with these filters through OID set requests of <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-current-packet-filter">OID_GEN_CURRENT_PACKET_FILTER</a>.

</li>
<li>
The network adapter detects other external events that require processing by the networking driver stack, such as when the  link state changes to either media disconnect or media connected.

</li>
</ul>

> [!NOTE]
> The <b>NDIS_PM_SELECTIVE_SUSPEND_ENABLED</b>  flag is available in NDIS 6.30 and later.
>
> If this flag is set, no other power management flags can be set in the <b>WakeUpFlags</b> member and the <b>EnabledWoLPacketPatterns</b> member must be set to zero.

If NDIS sets the <b>NDIS_PM_SELECTIVE_SUSPEND_ENABLED</b> flag, it issues the OID set request of <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-pm-parameters">OID_PM_PARAMETERS</a> directly to the miniport driver. This allows NDIS to bypass the processing by filter drivers in the networking driver stack.

For more information about the selective suspend power management capability, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_netvista/">NDIS Selective Suspend</a>.

### -field MediaSpecificWakeUpEvents

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags. These flags specify the media-specific wake-up events that a network adapter supports. 
     

Starting with NDIS 6.30, the following flags are defined:

#### NDIS_WLAN_WAKE_ON_NLO_DISCOVERY_ENABLED

If this flag is set, the 802.11 network adapter is enabled to generate a wake-up event when it detects a service set identifier (SSID) that was specified through a network offload (NLO). 

For more information about NLO, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wi-fi-network-list-offload">Wi-Fi Network List Offload</a>.



#### NDIS_WLAN_WAKE_ON_AP_ASSOCIATION_LOST_ENABLED

If this flag is set, the 802.11 network adapter is enabled to generate a wake-up event when it disassociates with the access point (AP).



#### NDIS_WLAN_WAKE_ON_GTK_HANDSHAKE_ERROR_ENABLED

If this flag is set, the 802.11 network adapter is enabled to generate a wake-up event when it encounters an error during the IEEE 802.11i RSN group transient key (GTK) handshake with the AP.



#### NDIS_WLAN_WAKE_ON_4WAY_HANDSHAKE_REQUEST_ENABLED

If this flag is set, the 802.11 network adapter is enabled to generate a wake-up event when it receives the first frame of the IEEE 802.11i RSN 4-way handshake with the AP. This handshake is performed when the adapter authenticates with the AP.



#### NDIS_WWAN_WAKE_ON_REGISTER_STATE_ENABLED

If this flag is set, the mobile broadband (MB) network adapter is enabled to generate a wake-up event when its registration state to the MB Service has changed.



#### NDIS_WWAN_WAKE_ON_SMS_RECEIVE_ENABLED

If this flag is set, the MB network adapter is enabled to generate a wake-up event when the MB Service has to be notified about the receipt of a Short Message Service (SMS) message. The adapter generates this wake-up event either after the completion of a previously issued <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-sms-read">OID_WWAN_SMS_READ</a> query request, or the arrival of a new class-0 (flash/alert) message from the network provider as an event notification.



#### NDIS_WWAN_WAKE_ON_USSD_RECEIVE_ENABLED

If this flag is set, the MB network adapter is enabled to generate a wake-up event when it receives an Unstructured Supplementary Service Data (USSD) message.



#### NDIS_WWAN_WAKE_ON_PACKET_STATE_ENABLED

If this flag is set, the MB network adapter is enabled to generate a wake-up event when the availability of cellular packet data changes. This flag is new in Windows 10.



#### NDIS_WWAN_WAKE_ON_UICC_CHANGE_ENABLED

If this flag is set, the MB network adapter is enabled to generate a wake-up event when the UICC (SIM) card is inserted, removed, or enters an error state. This flag is new in Windows 10.


## -remarks



The <b>NDIS_PM_PARAMETERS</b> structure specifies the enabled power management hardware capabilities for the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-pm-parameters">OID_PM_PARAMETERS</a> OID. When the
    OID_PM_PARAMETERS OID is queried, this structure provides the current power management configuration.
    When the OID_PM_PARAMETERS OID is set, this structure specifies a new power management configuration that
    the network adapter should use.

An overlying driver should not try to enable capabilities that a network adapter does not support. To
    enable an overlying driver to determine what capabilities a network adapter provides, NDIS provides the
    capabilities in the 
    <b>PowerManagementCapabilitiesEx</b> member of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_bind_parameters">NDIS_BIND_PARAMETERS</a> structure.


> [!NOTE]
> NDIS 6.20 and later drivers must use the **PowerManagementCapabilitiesEx** member of the [NDIS_BIND_PARAMETERS](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_bind_parameters) structure instead of the **PowerManagementCapabilities** member.

## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_bind_parameters">NDIS_BIND_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_pm_capabilities">NDIS_PM_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_pm_wol_pattern">NDIS_PM_WOL_PATTERN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-current-packet-filter">OID_GEN_CURRENT_PACKET_FILTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-pm-parameters">OID_PM_PARAMETERS</a>
 

 

