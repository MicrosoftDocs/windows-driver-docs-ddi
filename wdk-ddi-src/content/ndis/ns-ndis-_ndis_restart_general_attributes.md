---
UID: NS:ndis._NDIS_RESTART_GENERAL_ATTRIBUTES
title: _NDIS_RESTART_GENERAL_ATTRIBUTES
author: windows-driver-content
description: The NDIS_RESTART_GENERAL_ATTRIBUTES structure defines the general restart attributes that are associated with a miniport adapter.
old-location: netvista\ndis_restart_general_attributes.htm
old-project: netvista
ms.assetid: f67bd2fe-4553-4b1a-8d39-26777bcc60e0
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: miniport_structures_ref_10a54e42-4d48-4fdc-8a68-43771c319215.xml, _NDIS_RESTART_GENERAL_ATTRIBUTES, ndis/NDIS_RESTART_GENERAL_ATTRIBUTES, PNDIS_RESTART_GENERAL_ATTRIBUTES, *PNDIS_RESTART_GENERAL_ATTRIBUTES, ndis/PNDIS_RESTART_GENERAL_ATTRIBUTES, NDIS_RESTART_GENERAL_ATTRIBUTES, NDIS_RESTART_GENERAL_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], PNDIS_RESTART_GENERAL_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], netvista.ndis_restart_general_attributes
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: See Remarks section
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	ndis.h
apiname: 
-	NDIS_RESTART_GENERAL_ATTRIBUTES
product: Windows
targetos: Windows
req.typenames: *PNDIS_RESTART_GENERAL_ATTRIBUTES, NDIS_RESTART_GENERAL_ATTRIBUTES
---

# _NDIS_RESTART_GENERAL_ATTRIBUTES structure


## -description


The <b>NDIS_RESTART_GENERAL_ATTRIBUTES</b> structure defines the general restart attributes that are
  associated with a miniport adapter.


## -syntax


````
typedef struct _NDIS_RESTART_GENERAL_ATTRIBUTES {
  NDIS_OBJECT_HEADER               Header;
  ULONG                            MtuSize;
  ULONG64                          MaxXmitLinkSpeed;
  ULONG64                          MaxRcvLinkSpeed;
  ULONG                            LookaheadSize;
  ULONG                            MacOptions;
  ULONG                            SupportedPacketFilters;
  ULONG                            MaxMulticastListSize;
  PNDIS_RECEIVE_SCALE_CAPABILITIES RecvScaleCapabilities;
  NET_IF_ACCESS_TYPE               AccessType;
  ULONG                            Flags;
  NET_IF_CONNECTION_TYPE           ConnectionType;
  ULONG                            SupportedStatistics;
  ULONG                            DataBackFillSize;
  ULONG                            ContextBackFillSize;
  PNDIS_OID                        SupportedOidList;
  ULONG                            SupportedOidListLength;
#if (NDIS_SUPPORT_NDIS620)
  ULONG                            MaxLookaheadSizeAccessed;
#endif 
} NDIS_RESTART_GENERAL_ATTRIBUTES, *PNDIS_RESTART_GENERAL_ATTRIBUTES;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_RESTART_GENERAL_ATTRIBUTES</b> structure. NDIS sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to <b>NDIS_OBJECT_TYPE_RESTART_GENERIC_ATTRIBUTES</b>. 
     

To indicate the version of the <b>NDIS_RESTART_GENERAL_ATTRIBUTES</b> structure, NDIS sets the 
     <b>Revision</b> member to one of the following values:






### -field MtuSize

The maximum transfer unit (MTU) size. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569598">OID_GEN_MAXIMUM_FRAME_SIZE</a>.


### -field MaxXmitLinkSpeed

The maximum transmit link speed of the adapter in bits per second. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569602">OID_GEN_MAX_LINK_SPEED</a>.


### -field MaxRcvLinkSpeed

The maximum receive link speed of the adapter in bits per second. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569602">OID_GEN_MAX_LINK_SPEED</a>.


### -field LookaheadSize

The lookahead size for the miniport adapter. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569574">OID_GEN_CURRENT_LOOKAHEAD</a>.


### -field MacOptions

The medium access control (MAC) options for the miniport adapter. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569597">OID_GEN_MAC_OPTIONS</a>.


### -field SupportedPacketFilters

The packet filter flags for the miniport adapter. For more information, see 
     <mshelp:link keywords="netvista.oid_gen_supported_packet_filters" tabindex="0">
     OID_GEN_SUPPORTED_PACKET_FILTERS</mshelp:link>.


### -field MaxMulticastListSize

The maximum multicast address list size for the miniport adapter. For more information, see 
     <mshelp:link keywords="netvista.oid_802_3_maximum_list_size" tabindex="0">
     OID_802_3_MAXIMUM_LIST_SIZE</mshelp:link>.


### -field RecvScaleCapabilities

The receive side scaling (RSS) capabilities of the NIC. If the miniport adapter does not support
     the RSS feature, NDIS sets 
     <b>RecvScaleCapabilities</b> to a pointer to an 
     <mshelp:link keywords="netvista.ndis_receive_scale_capabilities" tabindex="0"><b>
     NDIS_RECEIVE_SCALE_CAPABILITIES</b></mshelp:link> structure that is filled with zeros. For more information about
     RSS, see 
     <mshelp:link keywords="netvista.oid_gen_receive_scale_capabilities" tabindex="0">
     OID_GEN_RECEIVE_SCALE_CAPABILITIES</mshelp:link>.


### -field AccessType

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568739">NET_IF_ACCESS_TYPE</a> NDIS network interface
     access type.


### -field Flags

Reserved.


### -field ConnectionType

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568741">NET_IF_CONNECTION_TYPE</a> NDIS network
     interface connection type.


### -field SupportedStatistics

The supported statistics. For more information, see the 
     <b>SupportedStatistics</b> member of the 
     <mshelp:link keywords="netvista.ndis_miniport_adapter_general_attributes" tabindex="0"><b>
     NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</b></mshelp:link> structure.


### -field DataBackFillSize

The required data backfill size, in bytes, of the driver.


### -field ContextBackFillSize

The required context backfill size, in bytes, of the driver.


### -field SupportedOidList

A list of OIDs that the miniport driver supports. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569642">OID_GEN_SUPPORTED_LIST</a>.


### -field SupportedOidListLength

The size, in bytes, of the OID list that is specified in the 
     <b>SupportedOidList</b> member.


### -field MaxLookaheadSizeAccessed

A ULONG value for the maximum size, in bytes, of the lookahead size requirement for receive
     queues. A miniport adapter that supports lookahead in VM queues splits a received packet at an offset
     equal to or greater than the requested lookahead size and DMAs the lookahead data and the post-lookahead
     data to separate shared memory segments.


##### - Header.NDIS_RESTART_GENERAL_ATTRIBUTES_REVISION_2

Added the 
       <b>MaxLookaheadSizeAccessed</b> member for NDIS 6.2. 
       

NDIS sets the 
       <b>Size</b> member to <b>NDIS_SIZEOF_RESTART_GENERAL_ATTRIBUTES_REVISION_2</b>.


##### - Header.NDIS_RESTART_GENERAL_ATTRIBUTES_REVISION_1

Original version for NDIS 6.0 and NDIS 6.1.
       

NDIS sets the 
       <b>Size</b> member to <b>NDIS_SIZEOF_RESTART_GENERAL_ATTRIBUTES_REVISION_1</b>.


## -remarks


NDIS passes an NDIS_RESTART_GENERAL_ATTRIBUTES structure to drivers during restart operations. For
    example, when NDIS calls a miniport driver's 
    <a href="..\ndis\nc-ndis-miniport_restart.md">MiniportRestart</a> function, NDIS passes a
    pointer to an 
    <a href="..\ndis\ns-ndis-_ndis_restart_attributes.md">NDIS_RESTART_ATTRIBUTES</a> structure to
    the miniport driver in the 
    <b>RestartAttributes</b> member of the 
    <mshelp:link keywords="netvista.ndis_miniport_restart_parameters" tabindex="0"><b>
    NDIS_MINIPORT_RESTART_PARAMETERS</b></mshelp:link> structure.

If the 
    <b>Oid</b> member in the NDIS_RESTART_ATTRIBUTES structure is 
    <mshelp:link keywords="netvista.oid_gen_miniport_restart_attributes" tabindex="0">
    OID_GEN_MINIPORT_RESTART_ATTRIBUTES</mshelp:link>, the 
    <b>Data</b> member of NDIS_RESTART_ATTRIBUTES contains an NDIS_RESTART_GENERAL_ATTRIBUTES structure.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569642">OID_GEN_SUPPORTED_LIST</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569574">OID_GEN_CURRENT_LOOKAHEAD</a>

<mshelp:link keywords="netvista.ndis_receive_scale_capabilities" tabindex="0"><b>
   NDIS_RECEIVE_SCALE_CAPABILITIES</b></mshelp:link>

<mshelp:link keywords="netvista.oid_gen_supported_packet_filters" tabindex="0">
   OID_GEN_SUPPORTED_PACKET_FILTERS</mshelp:link>

<mshelp:link keywords="netvista.oid_gen_miniport_restart_attributes" tabindex="0">
   OID_GEN_MINIPORT_RESTART_ATTRIBUTES</mshelp:link>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568741">NET_IF_CONNECTION_TYPE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568739">NET_IF_ACCESS_TYPE</a>

<mshelp:link keywords="netvista.ndis_miniport_adapter_general_attributes" tabindex="0"><b>
   NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</b></mshelp:link>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-statistics">OID_GEN_STATISTICS</a>

<a href="..\ndis\nc-ndis-miniport_restart.md">MiniportRestart</a>

<mshelp:link keywords="netvista.ndis_miniport_restart_parameters" tabindex="0"><b>
   NDIS_MINIPORT_RESTART_PARAMETERS</b></mshelp:link>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569602">OID_GEN_MAX_LINK_SPEED</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569598">OID_GEN_MAXIMUM_FRAME_SIZE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569597">OID_GEN_MAC_OPTIONS</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-802-3-maximum-list-size">OID_802_3_MAXIMUM_LIST_SIZE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568742">NET_IF_DIRECTION_TYPE</a>

<a href="..\ndis\ns-ndis-_ndis_restart_attributes.md">NDIS_RESTART_ATTRIBUTES</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569774">OID_PNP_CAPABILITIES</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RESTART_GENERAL_ATTRIBUTES structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

