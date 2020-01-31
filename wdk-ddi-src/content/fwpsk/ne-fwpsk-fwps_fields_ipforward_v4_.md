---
UID: NE:fwpsk.FWPS_FIELDS_IPFORWARD_V4_
title: FWPS_FIELDS_IPFORWARD_V4_ (fwpsk.h)
description: The FWPS_FIELDS_IPFORWARD_V4 enumeration type specifies the data field identifiers for the FWPS_LAYER_IPFORWARD_V4 and FWPS_LAYER_IPFORWARD_V4_DISCARD run-time filtering layers.
old-location: netvista\fwps_fields_ipforward_v4.htm
tech.root: netvista
ms.assetid: af915976-2a2c-4cf4-a3e0-60ddea8e172c
ms.date: 05/02/2018
ms.keywords: FWPS_FIELDS_IPFORWARD_V4, FWPS_FIELDS_IPFORWARD_V4 enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELDS_IPFORWARD_V4_, FWPS_FIELD_IPFORWARD_V4_ARRIVAL_INTERFACE_PROFILE_ID, FWPS_FIELD_IPFORWARD_V4_DESTINATION_INTERFACE_INDEX, FWPS_FIELD_IPFORWARD_V4_DESTINATION_SUB_INTERFACE_INDEX, FWPS_FIELD_IPFORWARD_V4_FLAGS, FWPS_FIELD_IPFORWARD_V4_IP_DESTINATION_ADDRESS, FWPS_FIELD_IPFORWARD_V4_IP_DESTINATION_ADDRESS_TYPE, FWPS_FIELD_IPFORWARD_V4_IP_FORWARD_INTERFACE, FWPS_FIELD_IPFORWARD_V4_IP_LOCAL_INTERFACE, FWPS_FIELD_IPFORWARD_V4_IP_PHYSICAL_ARRIVAL_INTERFACE, FWPS_FIELD_IPFORWARD_V4_IP_PHYSICAL_NEXTHOP_INTERFACE, FWPS_FIELD_IPFORWARD_V4_IP_SOURCE_ADDRESS, FWPS_FIELD_IPFORWARD_V4_MAX, FWPS_FIELD_IPFORWARD_V4_NEXTHOP_INTERFACE_PROFILE_ID, FWPS_FIELD_IPFORWARD_V4_SOURCE_INTERFACE_INDEX, FWPS_FIELD_IPFORWARD_V4_SOURCE_SUB_INTERFACE_INDEX, fwpsk/FWPS_FIELDS_IPFORWARD_V4, fwpsk/FWPS_FIELD_IPFORWARD_V4_ARRIVAL_INTERFACE_PROFILE_ID, fwpsk/FWPS_FIELD_IPFORWARD_V4_DESTINATION_INTERFACE_INDEX, fwpsk/FWPS_FIELD_IPFORWARD_V4_DESTINATION_SUB_INTERFACE_INDEX, fwpsk/FWPS_FIELD_IPFORWARD_V4_FLAGS, fwpsk/FWPS_FIELD_IPFORWARD_V4_IP_DESTINATION_ADDRESS, fwpsk/FWPS_FIELD_IPFORWARD_V4_IP_DESTINATION_ADDRESS_TYPE, fwpsk/FWPS_FIELD_IPFORWARD_V4_IP_FORWARD_INTERFACE, fwpsk/FWPS_FIELD_IPFORWARD_V4_IP_LOCAL_INTERFACE, fwpsk/FWPS_FIELD_IPFORWARD_V4_IP_PHYSICAL_ARRIVAL_INTERFACE, fwpsk/FWPS_FIELD_IPFORWARD_V4_IP_PHYSICAL_NEXTHOP_INTERFACE, fwpsk/FWPS_FIELD_IPFORWARD_V4_IP_SOURCE_ADDRESS, fwpsk/FWPS_FIELD_IPFORWARD_V4_MAX, fwpsk/FWPS_FIELD_IPFORWARD_V4_NEXTHOP_INTERFACE_PROFILE_ID, fwpsk/FWPS_FIELD_IPFORWARD_V4_SOURCE_INTERFACE_INDEX, fwpsk/FWPS_FIELD_IPFORWARD_V4_SOURCE_SUB_INTERFACE_INDEX, netvista.fwps_fields_ipforward_v4, wfp_ref_5_const_3_data_fields_cff20018-8ff1-43dc-937d-92a1a91137e3.xml
f1_keywords:
 - "fwpsk/FWPS_FIELDS_IPFORWARD_V4"
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Unless otherwise noted, supported starting with Windows Vista.
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
- fwpsk.h
api_name:
- FWPS_FIELDS_IPFORWARD_V4
product:
- Windows
targetos: Windows
req.typenames: FWPS_FIELDS_IPFORWARD_V4
---

# FWPS_FIELDS_IPFORWARD_V4_ enumeration


## -description


The FWPS_FIELDS_IPFORWARD_V4 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_IPFORWARD_V4 and FWPS_LAYER_IPFORWARD_V4_DISCARD 
  <a href="https://docs.microsoft.com/windows/desktop/FWP/management-filtering-layer-identifiers-">run-time filtering layers</a>.


## -enum-fields




### -field FWPS_FIELD_IPFORWARD_V4_IP_SOURCE_ADDRESS

The source IP address.


### -field FWPS_FIELD_IPFORWARD_V4_IP_DESTINATION_ADDRESS

The destination IP address.


### -field FWPS_FIELD_IPFORWARD_V4_IP_DESTINATION_ADDRESS_TYPE

The destination IP address type. The possible values are defined by the 
     <a href="https://docs.microsoft.com/windows/desktop/api/nldef/ne-nldef-nl_address_type">NL_ADDRESS_TYPE</a> enumeration.


### -field FWPS_FIELD_IPFORWARD_V4_IP_LOCAL_INTERFACE

The locally unique identifier (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/igpupvdev/ns-igpupvdev-_luid">LUID</a>) for the network interface associated with the
     local IP address.


### -field FWPS_FIELD_IPFORWARD_V4_IP_FORWARD_INTERFACE

The LUID for the network interface on which the packet being forwarded is to be sent out.


### -field FWPS_FIELD_IPFORWARD_V4_SOURCE_INTERFACE_INDEX

The index of the source network interface, as enumerated by the network stack.


### -field FWPS_FIELD_IPFORWARD_V4_SOURCE_SUB_INTERFACE_INDEX

The index of the source logical network interface, as enumerated by the network stack.


### -field FWPS_FIELD_IPFORWARD_V4_DESTINATION_INTERFACE_INDEX

The index of the destination network interface, as enumerated by the network stack.


### -field FWPS_FIELD_IPFORWARD_V4_DESTINATION_SUB_INTERFACE_INDEX

The index of the destination logical network interface, as enumerated by the network stack.


### -field FWPS_FIELD_IPFORWARD_V4_FLAGS

A bitwise OR of a combination of filtering condition flags. For information about the possible
     flags, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/filtering-condition-flags">Filtering Condition Flags</a>.


### -field FWPS_FIELD_IPFORWARD_V4_IP_PHYSICAL_ARRIVAL_INTERFACE

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/igpupvdev/ns-igpupvdev-_luid">LUID</a> for the physical network interface that the
     packet first arrived on.
     

<div class="alert"><b>Note</b>  Supported starting with Windows 7.</div>
<div> </div>

### -field FWPS_FIELD_IPFORWARD_V4_ARRIVAL_INTERFACE_PROFILE_ID

The profile identifier (network category) of the arrival interface. The possible network category
     values are: public (1), private (2), or domain (3).
     

<div class="alert"><b>Note</b>  Supported starting with Windows 7.</div>
<div> </div>

### -field FWPS_FIELD_IPFORWARD_V4_IP_PHYSICAL_NEXTHOP_INTERFACE

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/igpupvdev/ns-igpupvdev-_luid">LUID</a> for the physical network interface that will be
     used to continue forwarding of the outbound packet.
     

<div class="alert"><b>Note</b>  Supported starting with Windows 7.</div>
<div> </div>

### -field FWPS_FIELD_IPFORWARD_V4_NEXTHOP_INTERFACE_PROFILE_ID

The profile identifier (network category) of the next-hop interface. The possible network category
     values are: public (1), private (2), or domain (3).
     

<div class="alert"><b>Note</b>  Supported starting with Windows 7.</div>
<div> </div>

### -field FWPS_FIELD_IPFORWARD_V4_COMPARTMENT_ID

The compartment that the network interface belongs to.

<div class="alert"><b>Note</b>  Supported starting with Windows 10, version 1703.</div>
<div> </div>

### -field FWPS_FIELD_IPFORWARD_V4_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/igpupvdev/ns-igpupvdev-_luid">LUID</a>



<a href="https://docs.microsoft.com/windows/desktop/api/nldef/ne-nldef-nl_address_type">NL_ADDRESS_TYPE</a>
 

 

