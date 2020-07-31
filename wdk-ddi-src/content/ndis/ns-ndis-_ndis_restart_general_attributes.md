---
UID: NS:ndis._NDIS_RESTART_GENERAL_ATTRIBUTES
title: _NDIS_RESTART_GENERAL_ATTRIBUTES (ndis.h)
description: The NDIS_RESTART_GENERAL_ATTRIBUTES structure defines the general restart attributes that are associated with a miniport adapter.
old-location: netvista\ndis_restart_general_attributes.htm
tech.root: netvista
ms.assetid: f67bd2fe-4553-4b1a-8d39-26777bcc60e0
ms.date: 05/02/2018
keywords: ["_NDIS_RESTART_GENERAL_ATTRIBUTES structure"]
ms.keywords: "*PNDIS_RESTART_GENERAL_ATTRIBUTES, NDIS_RESTART_GENERAL_ATTRIBUTES, NDIS_RESTART_GENERAL_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], PNDIS_RESTART_GENERAL_ATTRIBUTES, PNDIS_RESTART_GENERAL_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RESTART_GENERAL_ATTRIBUTES, miniport_structures_ref_10a54e42-4d48-4fdc-8a68-43771c319215.xml, ndis/NDIS_RESTART_GENERAL_ATTRIBUTES, ndis/PNDIS_RESTART_GENERAL_ATTRIBUTES, netvista.ndis_restart_general_attributes"
f1_keywords:
 - "ndis/NDIS_RESTART_GENERAL_ATTRIBUTES"
 - "NDIS_RESTART_GENERAL_ATTRIBUTES"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndis.h
api_name:
- NDIS_RESTART_GENERAL_ATTRIBUTES
targetos: Windows
req.typenames: NDIS_RESTART_GENERAL_ATTRIBUTES, *PNDIS_RESTART_GENERAL_ATTRIBUTES
---

# _NDIS_RESTART_GENERAL_ATTRIBUTES structure


## -description


The <b>NDIS_RESTART_GENERAL_ATTRIBUTES</b> structure defines the general restart attributes that are
  associated with a miniport adapter.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_RESTART_GENERAL_ATTRIBUTES</b> structure. NDIS sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to <b>NDIS_OBJECT_TYPE_RESTART_GENERIC_ATTRIBUTES</b>. 
     

To indicate the version of the <b>NDIS_RESTART_GENERAL_ATTRIBUTES</b> structure, NDIS sets the 
     <b>Revision</b> member to one of the following values:





#### NDIS_RESTART_GENERAL_ATTRIBUTES_REVISION_2

Added the 
       <b>MaxLookaheadSizeAccessed</b> member for NDIS 6.2. 
       

NDIS sets the 
       <b>Size</b> member to <b>NDIS_SIZEOF_RESTART_GENERAL_ATTRIBUTES_REVISION_2</b>.





#### NDIS_RESTART_GENERAL_ATTRIBUTES_REVISION_1

Original version for NDIS 6.0 and NDIS 6.1.
       

NDIS sets the 
       <b>Size</b> member to <b>NDIS_SIZEOF_RESTART_GENERAL_ATTRIBUTES_REVISION_1</b>.


### -field MtuSize

The maximum transfer unit (MTU) size. For more information, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-maximum-frame-size">OID_GEN_MAXIMUM_FRAME_SIZE</a>.


### -field MaxXmitLinkSpeed

The maximum transmit link speed of the adapter in bits per second. For more information, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-max-link-speed">OID_GEN_MAX_LINK_SPEED</a>.


### -field MaxRcvLinkSpeed

The maximum receive link speed of the adapter in bits per second. For more information, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-max-link-speed">OID_GEN_MAX_LINK_SPEED</a>.


### -field LookaheadSize

The lookahead size for the miniport adapter. For more information, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-current-lookahead">OID_GEN_CURRENT_LOOKAHEAD</a>.


### -field MacOptions

The medium access control (MAC) options for the miniport adapter. For more information, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-mac-options">OID_GEN_MAC_OPTIONS</a>.


### -field SupportedPacketFilters

The packet filter flags for the miniport adapter. For more information, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-supported-packet-filters">
     OID_GEN_SUPPORTED_PACKET_FILTERS</a>.


### -field MaxMulticastListSize

The maximum multicast address list size for the miniport adapter. For more information, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-802-3-maximum-list-size">
     OID_802_3_MAXIMUM_LIST_SIZE</a>.


### -field RecvScaleCapabilities

The receive side scaling (RSS) capabilities of the NIC. If the miniport adapter does not support
     the RSS feature, NDIS sets 
     <b>RecvScaleCapabilities</b> to a pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_scale_capabilities">
     NDIS_RECEIVE_SCALE_CAPABILITIES</a> structure that is filled with zeros. For more information about
     RSS, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-receive-scale-capabilities">
     OID_GEN_RECEIVE_SCALE_CAPABILITIES</a>.


### -field AccessType

A 
     <a href="https://docs.microsoft.com/windows/win32/api/ifdef/ne-ifdef-net_if_access_type">NET_IF_ACCESS_TYPE</a> NDIS network interface
     access type.


### -field Flags

Reserved.


### -field ConnectionType

A 
     <a href="https://docs.microsoft.com/windows/win32/api/ifdef/ne-ifdef-net_if_connection_type">NET_IF_CONNECTION_TYPE</a> NDIS network
     interface connection type.


### -field SupportedStatistics

The supported statistics. For more information, see the 
     <b>SupportedStatistics</b> member of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_general_attributes">
     NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</a> structure.


### -field DataBackFillSize

The required data backfill size, in bytes, of the driver.


### -field ContextBackFillSize

The required context backfill size, in bytes, of the driver.


### -field SupportedOidList

A list of OIDs that the miniport driver supports. For more information, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-supported-list">OID_GEN_SUPPORTED_LIST</a>.


### -field SupportedOidListLength

The size, in bytes, of the OID list that is specified in the 
     <b>SupportedOidList</b> member.


### -field MaxLookaheadSizeAccessed

A ULONG value for the maximum size, in bytes, of the lookahead size requirement for receive
     queues. A miniport adapter that supports lookahead in VM queues splits a received packet at an offset
     equal to or greater than the requested lookahead size and DMAs the lookahead data and the post-lookahead
     data to separate shared memory segments.


## -remarks



NDIS passes an NDIS_RESTART_GENERAL_ATTRIBUTES structure to drivers during restart operations. For
    example, when NDIS calls a miniport driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_restart">MiniportRestart</a> function, NDIS passes a
    pointer to an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_restart_attributes">NDIS_RESTART_ATTRIBUTES</a> structure to
    the miniport driver in the 
    <b>RestartAttributes</b> member of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_restart_parameters">
    NDIS_MINIPORT_RESTART_PARAMETERS</a> structure.

If the 
    <b>Oid</b> member in the NDIS_RESTART_ATTRIBUTES structure is 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-miniport-restart-attributes">
    OID_GEN_MINIPORT_RESTART_ATTRIBUTES</a>, the 
    <b>Data</b> member of NDIS_RESTART_ATTRIBUTES contains an NDIS_RESTART_GENERAL_ATTRIBUTES structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_restart">MiniportRestart</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_general_attributes">
   NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_restart_parameters">
   NDIS_MINIPORT_RESTART_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_scale_capabilities">
   NDIS_RECEIVE_SCALE_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_restart_attributes">NDIS_RESTART_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows/win32/api/ifdef/ne-ifdef-net_if_access_type">NET_IF_ACCESS_TYPE</a>



<a href="https://docs.microsoft.com/windows/win32/api/ifdef/ne-ifdef-net_if_connection_type">NET_IF_CONNECTION_TYPE</a>



<a href="https://docs.microsoft.com/windows/win32/api/ifdef/ne-ifdef-net_if_direction_type">NET_IF_DIRECTION_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-802-3-maximum-list-size">OID_802_3_MAXIMUM_LIST_SIZE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-current-lookahead">OID_GEN_CURRENT_LOOKAHEAD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-mac-options">OID_GEN_MAC_OPTIONS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-maximum-frame-size">OID_GEN_MAXIMUM_FRAME_SIZE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-max-link-speed">OID_GEN_MAX_LINK_SPEED</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-miniport-restart-attributes">
   OID_GEN_MINIPORT_RESTART_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-statistics">OID_GEN_STATISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-supported-list">OID_GEN_SUPPORTED_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-supported-packet-filters">
   OID_GEN_SUPPORTED_PACKET_FILTERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-pnp-capabilities">OID_PNP_CAPABILITIES</a>
 

 

