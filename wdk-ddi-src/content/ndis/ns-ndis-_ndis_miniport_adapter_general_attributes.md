---
UID: NS:ndis._NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES
title: "_NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES"
author: windows-driver-content
description: An NDIS miniport driver sets up an NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES structure to define the general miniport driver attributes that are associated with a miniport adapter.
old-location: netvista\ndis_miniport_adapter_general_attributes.htm
tech.root: netvista
ms.assetid: 5423d073-02a5-468b-b91e-713ac67a5253
ms.date: 5/2/2018
ms.keywords: "*PNDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES, NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES, NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES, PNDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES, miniport_structures_ref_42ce6caf-9d6f-47ee-ad20-749b0058c71e.xml, ndis/NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES, ndis/PNDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES, netvista.ndis_miniport_adapter_general_attributes"
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES
product:
- Windows
targetos: Windows
req.typenames: NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES, *PNDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES
---

# _NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES structure


## -description


An NDIS miniport driver sets up an <b>NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</b> structure to define the
  general miniport driver attributes that are associated with a miniport adapter.


## -struct-fields




### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
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
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff565910">NDIS_MEDIUM</a>.


### -field PhysicalMediumType

The physical medium type for the miniport adapter. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569621">OID_GEN_PHYSICAL_MEDIUM</a>



### -field MtuSize

The maximum transfer unit (MTU) size. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569598">OID_GEN_MAXIMUM_FRAME_SIZE</a>.


### -field MaxXmitLinkSpeed

The maximum transmit link speed of the adapter in bits per second. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569602">OID_GEN_MAX_LINK_SPEED</a>.


### -field XmitLinkSpeed

The current transmit link speed of the adapter in bits per second. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569594">OID_GEN_LINK_SPEED_EX</a>.


### -field MaxRcvLinkSpeed

The maximum receive link speed of the adapter in bits per second. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569602">OID_GEN_MAX_LINK_SPEED</a>.


### -field RcvLinkSpeed

The current receive link speed of the adapter in bits per second. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569594">OID_GEN_LINK_SPEED_EX</a>.


### -field MediaConnectState

The media connect state for the miniport adapter. For more information, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-media-connect-status-ex">
     OID_GEN_MEDIA_CONNECT_STATUS_EX</a>.


### -field MediaDuplexState

The media duplex state for the miniport adapter. For more information, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-media-duplex-state">OID_GEN_MEDIA_DUPLEX_STATE</a>.


### -field LookaheadSize

The lookahead size for the miniport adapter. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569574">OID_GEN_CURRENT_LOOKAHEAD</a>.


### -field PowerManagementCapabilities

The Plug and Play (PnP) capabilities of the miniport adapter. For more information about PnP
     capabilities, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569774">OID_PNP_CAPABILITIES</a>. If the miniport
     adapter is not power management-aware, the miniport driver should set 
     <b>PowerManagementCapabilities</b> to <b>NULL</b>. NDIS 6.20 and later drivers must use the 
     <b>PowerManagementCapabilitiesEx</b> member instead.


### -field MacOptions

The MAC options for the miniport adapter. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569597">OID_GEN_MAC_OPTIONS</a>.


### -field SupportedPacketFilters

The packet filter flags for the miniport adapter. For more information, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-supported-packet-filters">
     OID_GEN_SUPPORTED_PACKET_FILTERS</a>.


### -field MaxMulticastListSize

The multicast address list size for the miniport adapter. For more information, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-802-3-maximum-list-size">
     OID_802_3_MAXIMUM_LIST_SIZE</a>.


### -field MacAddressLength

The MAC address length, in bytes. The MAC address length is specific to the type of media.


### -field PermanentMacAddress

The permanent MAC address. For example, the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569074">OID_802_3_PERMANENT_ADDRESS</a> OID
     specifies the permanent MAC address for IEEE 802.3 drivers.


### -field CurrentMacAddress

The current MAC address. For example, the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569069">OID_802_3_CURRENT_ADDRESS</a> OID
     specifies the current MAC address for IEEE 802.3 drivers.


### -field RecvScaleCapabilities

The receive side scaling (RSS) capabilities of the NIC. If the miniport adapter does not support
     the RSS feature, set 
     <b>RecvScaleCapabilities</b> to <b>NULL</b>. For more information about RSS, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-receive-scale-capabilities">
     OID_GEN_RECEIVE_SCALE_CAPABILITIES</a>.


### -field AccessType

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568739">NET_IF_ACCESS_TYPE</a> NDIS network interface
     access type.


### -field DirectionType

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568742">NET_IF_DIRECTION_TYPE</a> NDIS network
     interface direction type.


### -field ConnectionType

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568741">NET_IF_CONNECTION_TYPE</a> NDIS network
     interface connection type.


### -field IfType

The Internet Assigned Numbers Authority (IANA) interface type. For example,
     IF_TYPE_ETHERNET_CSMACD (6) is the value for 
     <b>IfType</b> that is assigned to any Ethernet-like interface. For a list if interface types, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff565767">NDIS Interface Types</a>.


### -field IfConnectorPresent

A Boolean value that indicates if a connector is present. Set this value to <b>TRUE</b> if there is a
     physical adapter.


### -field SupportedStatistics

The supported statistics.
     

<div class="alert"><b>Note</b>  NDIS 6.0 drivers must support all statistics and must report them when the drivers
     are queried for 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-statistics">OID_GEN_STATISTICS</a>.</div>
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
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569642">OID_GEN_SUPPORTED_LIST</a>.


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
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566748">NDIS_PM_CAPABILITIES</a> structure. This
     structure specifies power management capabilities of the miniport adapter. This member is mandatory for
     NDIS 6.20 and later drivers.


## -remarks



A miniport driver passes a pointer to an NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES structure in the 
    <i>MiniportAttributes</i> parameter of the 
    <a href="https://msdn.microsoft.com/861626af-23ea-40dc-a91a-7da42d4b0a1c">
    NdisMSetMiniportAttributes</a> function. A miniport driver calls 
    <b>NdisMSetMiniportAttributes</b> from its 
    <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> function
    during initialization. Miniport drivers should set the these attributes after they set the registration
    attributes in the 
    <a href="https://msdn.microsoft.com/8f0d539a-50c5-4ecd-b62d-6b32fe7cfaba">
    NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a> structure and before they set any other attributes.
    Setting these attribute is mandatory. 




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565910">NDIS_MEDIUM</a>



<a href="https://msdn.microsoft.com/8f0d539a-50c5-4ecd-b62d-6b32fe7cfaba">
   NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566748">NDIS_PM_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-statistics">NDIS_STATISTICS_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568739">NET_IF_ACCESS_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568741">NET_IF_CONNECTION_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568742">NET_IF_DIRECTION_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563672">NdisMSetMiniportAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569069">OID_802_3_CURRENT_ADDRESS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-802-3-maximum-list-size">OID_802_3_MAXIMUM_LIST_SIZE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569074">OID_802_3_PERMANENT_ADDRESS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569574">OID_GEN_CURRENT_LOOKAHEAD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569594">OID_GEN_LINK_SPEED_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569597">OID_GEN_MAC_OPTIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569598">OID_GEN_MAXIMUM_FRAME_SIZE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569602">OID_GEN_MAX_LINK_SPEED</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-media-connect-status-ex">OID_GEN_MEDIA_CONNECT_STATUS_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-media-duplex-state">OID_GEN_MEDIA_DUPLEX_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569621">OID_GEN_PHYSICAL_MEDIUM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-statistics">OID_GEN_STATISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569642">OID_GEN_SUPPORTED_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-supported-packet-filters">
   OID_GEN_SUPPORTED_PACKET_FILTERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569774">OID_PNP_CAPABILITIES</a>
 

 

