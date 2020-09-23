---
UID: NS:ndis._NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES
title: _NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES (ndis.h)
description: An NDIS miniport driver sets up an NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES structure to define the general miniport driver attributes that are associated with a miniport adapter.
old-location: netvista\ndis_miniport_adapter_general_attributes.htm
tech.root: netvista
ms.assetid: 5423d073-02a5-468b-b91e-713ac67a5253
ms.date: 05/02/2018
keywords: ["NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES structure"]
ms.keywords: "*PNDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES, NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES, NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES, PNDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES, miniport_structures_ref_42ce6caf-9d6f-47ee-ad20-749b0058c71e.xml, ndis/NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES, ndis/PNDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES, netvista.ndis_miniport_adapter_general_attributes"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
targetos: Windows
req.typenames: NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES, *PNDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES
f1_keywords:
 - _NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES
 - ndis/_NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES
 - PNDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES
 - ndis/PNDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES
 - NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES
 - ndis/NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES
---

# _NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES structure


## -description

An NDIS miniport driver sets up an <b>NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</b> structure to define the
  general miniport driver attributes that are associated with a miniport adapter.

## -struct-fields

### -field Header

The 
     <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</b> structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to <b>NDIS_OBJECT_TYPE_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</b>.
     

To indicate the version of the <b>NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</b> structure, set the 
     <b>Revision</b> member to one of the following values:





#### NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES_REVISION_2

Added the 
        <b>PowerManagementCapabilitiesEx</b> member for NDIS 6.2.

Set the <b>Size</b> member to <b>NDIS_SIZEOF_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES_REVISION_2</b>.



#### NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES_REVISION_1

Original version for NDIS 6.0 and NDIS 6,1.

Set the 
        <b>Size</b> member to
        <b>NDIS_SIZEOF_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES_REVISION_1</b>.

### -field Flags

Reserved for NDIS.

### -field MediaType

The 
     <b>NdisMedium<i>Xxx</i></b> type that the miniport adapter supports. For more information, see 
     <a href="/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_medium">NDIS_MEDIUM</a>.

### -field PhysicalMediumType

The physical medium type for the miniport adapter. For more information, see 
     <a href="/windows-hardware/drivers/network/oid-gen-physical-medium">OID_GEN_PHYSICAL_MEDIUM</a>

### -field MtuSize

The maximum transfer unit (MTU) size. For more information, see 
     <a href="/windows-hardware/drivers/network/oid-gen-maximum-frame-size">OID_GEN_MAXIMUM_FRAME_SIZE</a>.

### -field MaxXmitLinkSpeed

The maximum transmit link speed of the adapter in bits per second. For more information, see 
     <a href="/windows-hardware/drivers/network/oid-gen-max-link-speed">OID_GEN_MAX_LINK_SPEED</a>.

### -field XmitLinkSpeed

The current transmit link speed of the adapter in bits per second. For more information, see 
     <a href="/windows-hardware/drivers/network/oid-gen-link-speed-ex">OID_GEN_LINK_SPEED_EX</a>.

### -field MaxRcvLinkSpeed

The maximum receive link speed of the adapter in bits per second. For more information, see 
     <a href="/windows-hardware/drivers/network/oid-gen-max-link-speed">OID_GEN_MAX_LINK_SPEED</a>.

### -field RcvLinkSpeed

The current receive link speed of the adapter in bits per second. For more information, see 
     <a href="/windows-hardware/drivers/network/oid-gen-link-speed-ex">OID_GEN_LINK_SPEED_EX</a>.

### -field MediaConnectState

The media connect state for the miniport adapter. For more information, see 
     <a href="/windows-hardware/drivers/network/oid-gen-media-connect-status-ex">
     OID_GEN_MEDIA_CONNECT_STATUS_EX</a>.

### -field MediaDuplexState

The media duplex state for the miniport adapter. For more information, see 
     <a href="/windows-hardware/drivers/network/oid-gen-media-duplex-state">OID_GEN_MEDIA_DUPLEX_STATE</a>.

### -field LookaheadSize

The lookahead size for the miniport adapter. For more information, see 
     <a href="/windows-hardware/drivers/network/oid-gen-current-lookahead">OID_GEN_CURRENT_LOOKAHEAD</a>.

### -field PowerManagementCapabilities

The Plug and Play (PnP) capabilities of the miniport adapter. For more information about PnP
     capabilities, see 
     <a href="/windows-hardware/drivers/network/oid-pnp-capabilities">OID_PNP_CAPABILITIES</a>. If the miniport
     adapter is not power management-aware, the miniport driver should set 
     <b>PowerManagementCapabilities</b> to <b>NULL</b>. NDIS 6.20 and later drivers must use the 
     <b>PowerManagementCapabilitiesEx</b> member instead.

### -field MacOptions

The MAC options for the miniport adapter. For more information, see 
     <a href="/windows-hardware/drivers/network/oid-gen-mac-options">OID_GEN_MAC_OPTIONS</a>.

### -field SupportedPacketFilters

The packet filter flags for the miniport adapter. For more information, see 
     <a href="/windows-hardware/drivers/network/oid-gen-supported-packet-filters">
     OID_GEN_SUPPORTED_PACKET_FILTERS</a>.

### -field MaxMulticastListSize

The multicast address list size for the miniport adapter. For more information, see 
     <a href="/windows-hardware/drivers/network/oid-802-3-maximum-list-size">
     OID_802_3_MAXIMUM_LIST_SIZE</a>.

### -field MacAddressLength

The MAC address length, in bytes. The MAC address length is specific to the type of media.

### -field PermanentMacAddress

The permanent MAC address. For example, the 
     <a href="/windows-hardware/drivers/network/oid-802-3-permanent-address">OID_802_3_PERMANENT_ADDRESS</a> OID
     specifies the permanent MAC address for IEEE 802.3 drivers.

### -field CurrentMacAddress

The current MAC address. For example, the 
     <a href="/windows-hardware/drivers/network/oid-802-3-current-address">OID_802_3_CURRENT_ADDRESS</a> OID
     specifies the current MAC address for IEEE 802.3 drivers.

### -field RecvScaleCapabilities

The receive side scaling (RSS) capabilities of the NIC. If the miniport adapter does not support
     the RSS feature, set 
     <b>RecvScaleCapabilities</b> to <b>NULL</b>. For more information about RSS, see 
     <a href="/windows-hardware/drivers/network/oid-gen-receive-scale-capabilities">
     OID_GEN_RECEIVE_SCALE_CAPABILITIES</a>.

### -field AccessType

A 
     <a href="/windows/win32/api/ifdef/ne-ifdef-net_if_access_type">NET_IF_ACCESS_TYPE</a> NDIS network interface
     access type.

### -field DirectionType

A 
     <a href="/windows/win32/api/ifdef/ne-ifdef-net_if_direction_type">NET_IF_DIRECTION_TYPE</a> NDIS network
     interface direction type.

### -field ConnectionType

A 
     <a href="/windows/win32/api/ifdef/ne-ifdef-net_if_connection_type">NET_IF_CONNECTION_TYPE</a> NDIS network
     interface connection type.

### -field IfType

The Internet Assigned Numbers Authority (IANA) interface type. For example,
     IF_TYPE_ETHERNET_CSMACD (6) is the value for 
     <b>IfType</b> that is assigned to any Ethernet-like interface. For a list if interface types, see 
     <a href="/windows-hardware/drivers/network/ndis-interface-types">NDIS Interface Types</a>.

### -field IfConnectorPresent

A Boolean value that indicates if a connector is present. Set this value to <b>TRUE</b> if there is a
     physical adapter.

### -field SupportedStatistics

The supported statistics.
     

<div class="alert"><b>Note</b>  NDIS 6.0 drivers must support all statistics and must report them when the drivers
     are queried for 
     <a href="/windows-hardware/drivers/network/oid-gen-statistics">OID_GEN_STATISTICS</a>.</div>
<div> </div>
The value is the bitwise OR of the following flags:





#### NDIS_STATISTICS_DIRECTED_FRAMES_RCV_SUPPORTED

The data in the 
       <b>ifHCInUcastPkts</b> member is valid.



#### NDIS_STATISTICS_MULTICAST_FRAMES_RCV_SUPPORTED

The data in the 
       <b>ifHCInMulticastPkts</b> member of 
       NDIS_STATISTICS_INFO is valid.



#### NDIS_STATISTICS_BROADCAST_FRAMES_RCV_SUPPORTED

The data in the 
       <b>ifHCInBroadcastPkts</b> member of NDIS_STATISTICS_INFO is valid.



#### NDIS_STATISTICS_BYTES_RCV_SUPPORTED

The data in the 
       <b>ifHCInOctets</b> member of NDIS_STATISTICS_INFO is valid.



#### NDIS_STATISTICS_RCV_DISCARDS_SUPPORTED

The data in the 
       <b>ifInDiscards</b> member of NDIS_STATISTICS_INFO is valid.



#### NDIS_STATISTICS_RCV_ERROR_SUPPORTED

The data in the 
       <b>ifInErrors</b> member of NDIS_STATISTICS_INFO is valid.



#### NDIS_STATISTICS_DIRECTED_FRAMES_XMIT_SUPPORTED

The data in the 
       <b>ifHCOutUcastPkts</b> member of NDIS_STATISTICS_INFO is valid.



#### NDIS_STATISTICS_MULTICAST_FRAMES_XMIT_SUPPORTED

The data in the 
       <b>ifHCOutMulticastPkts</b> member of NDIS_STATISTICS_INFO is valid.



#### NDIS_STATISTICS_BROADCAST_FRAMES_XMIT_SUPPORTED

The data in the 
       <b>ifHCOutBroadcastPkts</b> member of NDIS_STATISTICS_INFO is valid.



#### NDIS_STATISTICS_BYTES_XMIT_SUPPORTED

The data in the 
       <b>ifHCOutOctets</b> member of NDIS_STATISTICS_INFO is valid.



#### NDIS_STATISTICS_XMIT_ERROR_SUPPORTED

The data in the 
       <b>ifOutErrors</b> member of NDIS_STATISTICS_INFO is valid.



#### NDIS_STATISTICS_XMIT_DISCARDS_SUPPORTED

The data in the 
       <b>ifOutDiscards</b> member of NDIS_STATISTICS_INFO is valid.



#### NDIS_STATISTICS_DIRECTED_BYTES_RCV_SUPPORTED

The data in the 
       <b>ifHCInUcastOctets</b> member of NDIS_STATISTICS_INFO is valid.



#### NDIS_STATISTICS_MULTICAST_BYTES_RCV_SUPPORTED

The data in the 
       <b>ifHCInMulticastOctets</b> member of NDIS_STATISTICS_INFO is valid.



#### NDIS_STATISTICS_BROADCAST_BYTES_RCV_SUPPORTED

The data in the 
       <b>ifHCInBroadcastOctets</b> member of NDIS_STATISTICS_INFO is valid.



#### NDIS_STATISTICS_DIRECTED_BYTES_XMIT_SUPPORTED

The data in the 
       <b>ifHCOutUcastOctets</b> member of NDIS_STATISTICS_INFO is valid.



#### NDIS_STATISTICS_MULTICAST_BYTES_XMIT_SUPPORTED

The data in the 
       <b>ifHCOutMulticastOctets</b> member of NDIS_STATISTICS_INFO is valid.



#### NDIS_STATISTICS_BROADCAST_BYTES_XMIT_SUPPORTED

The data in the 
       <b>ifHCOutBroadcastOctets</b> member of NDIS_STATISTICS_INFO is valid.

### -field SupportedPauseFunctions

Support for the IEEE 802.3 pause frames as one of the following pause functions:
     





#### NdisPauseFunctionsUnsupported

Indicates that the adapter or link partner does not support pause frames.



#### NdisPauseFunctionsSendOnly

Indicates that the adapter and link partner only support sending pause frames from the adapter
       to the link partner.



#### NdisPauseFunctionsReceiveOnly

Indicates that the adapter and link partner only support sending pause frames from the link
       partner to the adapter



#### NdisPauseFunctionsSendAndReceive

Indicates that the adapter and link partner support sending and receiving pause frames in both
       transint and receive directions.



#### NdisPauseFunctionsUnknown

Indicates that pause frame negotiation is in progress. The pause frame support that the link
       partner provides is unknown.

### -field DataBackFillSize

The required data backfill size, in bytes, of the driver.

### -field ContextBackFillSize

The required context backfill size, in bytes, of the driver.

### -field SupportedOidList

A list of OIDs that the miniport driver supports. For more information, see 
     <a href="/windows-hardware/drivers/network/oid-gen-supported-list">OID_GEN_SUPPORTED_LIST</a>.

### -field SupportedOidListLength

The size, in bytes, of the OID list at 
     <b>SupportedOidList</b> .

### -field AutoNegotiationFlags

The auto-negotiation settings for the miniport adapter. This member is created from a bitwise OR
     of the following flags:
     





#### NDIS_LINK_STATE_XMIT_LINK_SPEED_AUTO_NEGOTIATED

The adapter has auto-negotiated the transmit link speed with the link partner.



#### NDIS_LINK_STATE_RCV_LINK_SPEED_AUTO_NEGOTIATED

The adapter has auto-negotiated the receive link speed with the link partner.



#### NDIS_LINK_STATE_DUPLEX_AUTO_NEGOTIATED

The adapter has auto-negotiated the duplex state with the link partner.



#### NDIS_LINK_STATE_PAUSE_FUNCTIONS_AUTO_NEGOTIATED

The adapter has auto-negotiated the pause functions with the link partner.

### -field PowerManagementCapabilitiesEx

A pointer to an 
     <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_pm_capabilities">NDIS_PM_CAPABILITIES</a> structure. This
     structure specifies power management capabilities of the miniport adapter. This member is mandatory for
     NDIS 6.20 and later drivers.

## -remarks

A miniport driver passes a pointer to an NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES structure in the 
    <i>MiniportAttributes</i> parameter of the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">
    NdisMSetMiniportAttributes</a> function. A miniport driver calls 
    <b>NdisMSetMiniportAttributes</b> from its 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function
    during initialization. Miniport drivers should set the these attributes after they set the registration
    attributes in the 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_registration_attributes">
    NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a> structure and before they set any other attributes.
    Setting these attribute is mandatory.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_medium">NDIS_MEDIUM</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_registration_attributes">
   NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_pm_capabilities">NDIS_PM_CAPABILITIES</a>



<a href="/windows-hardware/drivers/network/oid-gen-statistics">NDIS_STATISTICS_INFO</a>



<a href="/windows/win32/api/ifdef/ne-ifdef-net_if_access_type">NET_IF_ACCESS_TYPE</a>



<a href="/windows/win32/api/ifdef/ne-ifdef-net_if_connection_type">NET_IF_CONNECTION_TYPE</a>



<a href="/windows/win32/api/ifdef/ne-ifdef-net_if_direction_type">NET_IF_DIRECTION_TYPE</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a>



<a href="/windows-hardware/drivers/network/oid-802-3-current-address">OID_802_3_CURRENT_ADDRESS</a>



<a href="/windows-hardware/drivers/network/oid-802-3-maximum-list-size">OID_802_3_MAXIMUM_LIST_SIZE</a>



<a href="/windows-hardware/drivers/network/oid-802-3-permanent-address">OID_802_3_PERMANENT_ADDRESS</a>



<a href="/windows-hardware/drivers/network/oid-gen-current-lookahead">OID_GEN_CURRENT_LOOKAHEAD</a>



<a href="/windows-hardware/drivers/network/oid-gen-link-speed-ex">OID_GEN_LINK_SPEED_EX</a>



<a href="/windows-hardware/drivers/network/oid-gen-mac-options">OID_GEN_MAC_OPTIONS</a>



<a href="/windows-hardware/drivers/network/oid-gen-maximum-frame-size">OID_GEN_MAXIMUM_FRAME_SIZE</a>



<a href="/windows-hardware/drivers/network/oid-gen-max-link-speed">OID_GEN_MAX_LINK_SPEED</a>



<a href="/windows-hardware/drivers/network/oid-gen-media-connect-status-ex">OID_GEN_MEDIA_CONNECT_STATUS_EX</a>



<a href="/windows-hardware/drivers/network/oid-gen-media-duplex-state">OID_GEN_MEDIA_DUPLEX_STATE</a>



<a href="/windows-hardware/drivers/network/oid-gen-physical-medium">OID_GEN_PHYSICAL_MEDIUM</a>



<a href="/windows-hardware/drivers/network/oid-gen-statistics">OID_GEN_STATISTICS</a>



<a href="/windows-hardware/drivers/network/oid-gen-supported-list">OID_GEN_SUPPORTED_LIST</a>



<a href="/windows-hardware/drivers/network/oid-gen-supported-packet-filters">
   OID_GEN_SUPPORTED_PACKET_FILTERS</a>



<a href="/windows-hardware/drivers/network/oid-pnp-capabilities">OID_PNP_CAPABILITIES</a>