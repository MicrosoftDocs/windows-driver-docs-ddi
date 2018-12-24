---
UID: NS:ndis._NDIS_BIND_PARAMETERS
title: "_NDIS_BIND_PARAMETERS"
description: NDIS initializes an NDIS_BIND_PARAMETERS structure with information that defines the characteristics of a binding and passes it to a protocol driver.
old-location: netvista\ndis_bind_parameters.htm
tech.root: netvista
ms.assetid: 0a4866a8-a2f2-447b-8aa9-73203b7fc4bb
ms.date: 05/02/2018
ms.keywords: "*PNDIS_BIND_PARAMETERS, NDIS_BIND_PARAMETERS, NDIS_BIND_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_BIND_PARAMETERS, PNDIS_BIND_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_BIND_PARAMETERS, ndis/NDIS_BIND_PARAMETERS, ndis/PNDIS_BIND_PARAMETERS, netvista.ndis_bind_parameters, protocol_structures_ref_25c90ff2-4a09-41f2-8b66-666a91dbfe17.xml"
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
-	NDIS_BIND_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_BIND_PARAMETERS, *PNDIS_BIND_PARAMETERS
---

# _NDIS_BIND_PARAMETERS structure


## -description


NDIS initializes an <b>NDIS_BIND_PARAMETERS</b> structure with information that defines the characteristics
  of a binding and passes it to a protocol driver.


## -struct-fields




### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_BIND_PARAMETERS</b> structure. NDIS sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_BIND_PARAMETERS.
     

To indicate the version of the NDIS_BIND_PARAMETERS structure, NDIS sets the 
     <b>Revision</b> member to one of the following values:





#### NDIS_BIND_PARAMETERS_REVISION_4

Added various members for NDIS 6.30.

NDIS sets the 
        <b>Size</b> member to NDIS_SIZEOF_BIND_PARAMETERS_REVISION_4.



#### NDIS_BIND_PARAMETERS_REVISION_3

Added the 
        <b>ReceiveFilterCapabilities</b>, 
        <b>PowerManagementCapabilitiesEx</b>, and 
        <b>NicSwitchCapabilities</b> members for NDIS 6.20.

NDIS sets the 
        <b>Size</b> member to NDIS_SIZEOF_BIND_PARAMETERS_REVISION_3.



#### NDIS_BIND_PARAMETERS_REVISION_2

Added the 
        <b>HDSplitCurrentConfig</b> member for NDIS 6.1.

NDIS sets the 
        <b>Size</b> member to NDIS_SIZEOF_BIND_PARAMETERS_REVISION_2.



#### NDIS_BIND_PARAMETERS_REVISION_1

Original version for NDIS 6.0.

NDIS sets the 
        <b>Size</b> member to NDIS_SIZEOF_BIND_PARAMETERS_REVISION_1.


### -field ProtocolSection

A pointer to a Unicode string that contains a registry path. The path starts from the protocol
     driver's service key and continues down the registry hierarchy to the miniport adapter name (for
     example, 
     <b>Tcpip\Parameters\Adapters\\</b>\<<i>miniport adapter name</i>\>). The miniport adapter name is the name of the
     bottom-most miniport adapter in the driver stack. If there is a MUX intermediate driver in the stack,
     the bottom-most miniport adapter is a virtual miniport. Otherwise, the bottom-most miniport adapter is a
     miniport adapter for a physical device.
     

The protocol driver can use this registry path to read configuration parameters that are specific to
     the binding between the driver and the underlying miniport adapter.


### -field AdapterName

A pointer to a Unicode string that contains the name of the underlying miniport adapter to which 
     <i>ProtocolBindAdapterEx</i> should bind.


### -field PhysicalDeviceObject

The physical device object for the underlying miniport adapter.


### -field MediaType

The 
     <b>NdisMedium</b><i>Xxx</i> type that the underlying miniport adapter supports. For more information
     about 
     <b>NdisMedium</b><i>Xxx</i> types, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff565910">NDIS_MEDIUM</a>.


### -field MtuSize

The maximum transfer unit (MTU) size. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569598">OID_GEN_MAXIMUM_FRAME_SIZE</a>.


### -field MaxXmitLinkSpeed

The maximum transmit link speed of the underlying adapter in bits per second. For more
     information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569602">OID_GEN_MAX_LINK_SPEED</a>.


### -field XmitLinkSpeed

The current transmit link speed of the underlying adapter in bits per second. For more
     information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569594">OID_GEN_LINK_SPEED_EX</a>.


### -field MaxRcvLinkSpeed

The maximum receive link speed of the underlying adapter in bits per second. For more information,
     see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569602">OID_GEN_MAX_LINK_SPEED</a>.


### -field RcvLinkSpeed

The current receive link speed of the underlying adapter in bits per second. For more information,
     see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569594">OID_GEN_LINK_SPEED_EX</a>.


### -field MediaConnectState

The media connect state for the underlying miniport adapter. For more information, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-media-connect-status-ex">
     OID_GEN_MEDIA_CONNECT_STATUS_EX</a>.


### -field MediaDuplexState

The media duplex state for the underlying miniport adapter. For more information, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-media-duplex-state">OID_GEN_MEDIA_DUPLEX_STATE</a>.


### -field LookaheadSize

The lookahead size for the underlying miniport adapter. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569574">OID_GEN_CURRENT_LOOKAHEAD</a>.


### -field PowerManagementCapabilities

The Plug and Play capabilities of the underlying miniport adapter. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569774">OID_PNP_CAPABILITIES</a>. NDIS 6.20 and
     later drivers must use the 
     <b>PowerManagementCapabilitiesEx</b> member instead.


### -field SupportedPacketFilters

A set of flags that identify the types of network packets that the underlying miniport adapter can
     filter. For more information, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-supported-packet-filters">
     OID_GEN_SUPPORTED_PACKET_FILTERS</a>.


### -field MaxMulticastListSize

The multicast address list size for the underlying miniport adapter. For more information, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-802-3-maximum-list-size">
     OID_802_3_MAXIMUM_LIST_SIZE</a>.


### -field MacAddressLength

The MAC address length, in bytes. The MAC address length is specific to the type of media.


### -field CurrentMacAddress

The current MAC address. For example, the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569069">OID_802_3_CURRENT_ADDRESS</a> OID
     specifies the current MAC address for IEEE 802.3 drivers.


### -field PhysicalMediumType

The physical medium type for the miniport adapter. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569621">OID_GEN_PHYSICAL_MEDIUM</a>.


### -field RcvScaleCapabilities

The <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-receive-side-scaling2">receive side scaling (RSS)</a> capabilities of the NIC. For more information, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-receive-scale-capabilities">
     OID_GEN_RECEIVE_SCALE_CAPABILITIES</a>.


### -field BoundIfNetluid

The NDIS 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568747">NET_LUID</a> value, that is also the network interface
     name (
     <i>ifName</i> in RFC 2863), of the highest level interface that is stacked on the
     miniport adapter. That is, if there are virtual miniports or filter modules that are installed over the
     miniport adapter, this is the NET_LUID value of the highest level virtual miniport or filter
     module.


### -field BoundIfIndex

The NDIS network interface index of the highest level interface that is stacked on the miniport
     adapter. That is, if there are virtual miniports or filter modules that are installed over the miniport
     adapter, this is the ifIndex of the highest level virtual miniport or filter module.


### -field LowestIfNetluid

The NDIS 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568747">NET_LUID</a> value, that is also the network interface
     name (
     <i>ifName</i> in RFC 2863), of the lowest level interface on a binding. That is, the
     NDIS network interface of the miniport adapter at the bottom of a filter stack.


### -field LowestIfIndex

The NDIS network interface index of lowest level interface on a binding. That is, the NDIS network
     interface of the miniport adapter at the bottom of a filter stack.


### -field AccessType

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568739">NET_IF_ACCESS_TYPE</a> NDIS network interface
     access type.


### -field DirectionType

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568742">NET_IF_DIRECTION_TYPE</a> NDIS network
     interface direction type.


### -field ConnectionType

The NDIS network interface connection type. Use <b>NET_IF_CONNECTION_DEDICATED</b> for a typical Ethernet
     adapter. The following valuse are valid:
     





#### NET_IF_CONNECTION_DEDICATED

Specifies the dedicated connection type. The connection comes up automatically when media sense
       is <b>TRUE</b>. For example, an Ethernet connection is dedicated.



#### NET_IF_CONNECTION_PASSIVE

Specifies the passive connection type. The other end must bring up the connection to the local
       station. For example, the RAS interface is passive.



#### NET_IF_CONNECTION_DEMAND

Specifies the demand-dial connection type. A demand-dial connection comes up in response to a
       local action--for example, sending a packet.


### -field IfType

The Internet Assigned Numbers Authority (IANA) interface type. For example,
     IF_TYPE_ETHERNET_CSMACD (6) is the value for 
     <b>IfType</b> that is assigned to any Ethernet-like interface. For a list if
     interface types, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff565767">NDIS Interface Types</a>.


### -field IfConnectorPresent

A Boolean value that indicates if a connector is present. NDIS sets this value to <b>TRUE</b> if there is
     a physical adapter.


### -field ActivePorts

To be determined.


### -field DataBackFillSize

The required data backfill size, in bytes, of the underlying driver stack.


### -field ContextBackFillSize

The required context backfill size, in bytes, of the underlying driver stack.


### -field MacOptions

The MAC options for the miniport adapter. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569597">OID_GEN_MAC_OPTIONS</a>.


### -field CompartmentId

The compartment to which the underlying interface belongs or one of the following values:
     





#### NET_IF_COMPARTMENT_ID_UNSPECIFIED

Specifies that the compartment identifier is not used or specified.



#### NET_IF_COMPARTMENT_ID_PRIMARY

Specifies the default compartment identifier. Third party interface providers must always
       specify NET_IF_COMPARTMENT_ID_PRIMARY. All other values are reserved for Microsoft internal
       use.


### -field DefaultOffloadConfiguration

A pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566599">NDIS_OFFLOAD</a> structure. This structure
     specifies the capabilities for a task-offload-capable miniport adapter. For more information, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-tcp-offload-current-config">
     OID_TCP_OFFLOAD_CURRENT_CONFIG</a>.


### -field TcpConnectionOffloadCapabilities

A pointer to an 
     <a href="https://msdn.microsoft.com/d37a773d-0a83-4592-9c21-3ceaa6454549">
     NDIS_TCP_CONNECTION_OFFLOAD</a> structure that indicates the current offload capabilities that are
     provided by the underlying miniport adapter.


### -field BoundAdapterName

A pointer to a Unicode string that contains the name of the highest-level miniport adapter that is
     stacked on the underlying miniport adapter. That is, if there are filter intermediate driver virtual
     miniports that are installed over the miniport adapter, this member is the name of the highest-level
     filter intermediate driver virtual miniport.


### -field HDSplitCurrentConfig

A pointer to an 
      <a href="https://msdn.microsoft.com/866fe9e6-0cb1-45cd-84b4-4e2df9c9c45a">
      NDIS_HD_SPLIT_CURRENT_CONFIG</a> structure. This structure specifies the current header-data split
      configuration of the underlying miniport adapter. This value can be <b>NULL</b> if the miniport adapter does
      not support header-data split.


### -field ReceiveFilterCapabilities

A pointer to an 
     <a href="https://msdn.microsoft.com/aecc1fe0-03f9-44be-9a38-b689eee4c5a6">
     NDIS_RECEIVE_FILTER_CAPABILITIES</a> structure. This structure specifies the generic filtering
     capabilities that are currently enabled on the underlying miniport adapter. This value can be <b>NULL</b> if the miniport adapter does not
     support receive filtering.


### -field PowerManagementCapabilitiesEx

A pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566748">NDIS_PM_CAPABILITIES</a> structure. This
     structure specifies power management capabilities of the miniport adapter. This member is mandatory for
     NDIS 6.20 and later drivers.


### -field NicSwitchCapabilities

A pointer to an 
     <a href="https://msdn.microsoft.com/bc4b56bd-583f-4b41-b5a7-90958ce65f42">
     NDIS_NIC_SWITCH_CAPABILITIES</a> structure. This structure specifies the NIC switch capabilities of
     the underlying miniport adapter. This value can be <b>NULL</b> if the miniport adapter does not support NIC
     switch features.


### -field NDKEnabled

NDIS sets this value to <b>TRUE</b> if the network direct kernel provider interface (NDKPI) is currently enabled on the underlying miniport adapter.


### -field NDKCapabilities

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451560">NDIS_NDK_CAPABILITIES</a> structure. This structure specifies the NDKPI capabilities that are currently enabled on the underlying miniport adapter. This value can be <b>NULL</b> if the miniport adapter does not support NDKPI.


### -field SriovCapabilities

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451677">NDIS_SRIOV_CAPABILITIES</a> structure. This structure specifies the single root I/O virtualization (SR-IOV) capabilities that are currently enabled on the underlying miniport adapter. This value can be <b>NULL</b> if the miniport adapter does not support SR-IOV features.


### -field NicSwitchArray

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451584">NDIS_NIC_SWITCH_INFO_ARRAY</a> structure.  This array enumerates the NIC switches that have been created on the miniport adapter. NIC switches can only be created if SR-IOV is supported and enabled on the adapter. 

<div class="alert"><b>Note</b>  Starting with Windows Server 2012, Windows supports only the default NIC switch on the miniport adapter. Therefore, this array can contain only one element. </div>
<div> </div>

## -remarks



NDIS passes a pointer to an NDIS_BIND_PARAMETERS structure in the 
    <i>BindParameters</i> parameter of the 
    <a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">
    ProtocolBindAdapterEx</a> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565696">NDIS_HD_SPLIT_CURRENT_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565910">NDIS_MEDIUM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566583">NDIS_NIC_SWITCH_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451584">NDIS_NIC_SWITCH_INFO_ARRAY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566599">NDIS_OFFLOAD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566748">NDIS_PM_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/aecc1fe0-03f9-44be-9a38-b689eee4c5a6">
   NDIS_RECEIVE_FILTER_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451677">NDIS_SRIOV_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567875">NDIS_TCP_CONNECTION_OFFLOAD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568739">NET_IF_ACCESS_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568742">NET_IF_DIRECTION_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568747">NET_LUID</a>



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



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-receive-scale-capabilities">
   OID_GEN_RECEIVE_SCALE_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-supported-packet-filters">
   OID_GEN_SUPPORTED_PACKET_FILTERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569774">OID_PNP_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-tcp-offload-current-config">OID_TCP_OFFLOAD_CURRENT_CONFIG</a>



<a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">ProtocolBindAdapterEx</a>
 

 

