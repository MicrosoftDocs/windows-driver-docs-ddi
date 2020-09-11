---
UID: NE:fwpsk.FWPS_FIELDS_INBOUND_TRANSPORT_V4_
title: FWPS_FIELDS_INBOUND_TRANSPORT_V4_ (fwpsk.h)
description: The FWPS_FIELDS_INBOUND_TRANSPORT_V4 enumeration type specifies the data field identifiers for the FWPS_LAYER_INBOUND_TRANSPORT_V4 and FWPS_LAYER_INBOUND_TRANSPORT_V4_DISCARD run-time filtering layers.
old-location: netvista\fwps_fields_inbound_transport_v4.htm
tech.root: netvista
ms.assetid: 6d5aebf1-22df-4825-a7d3-81b7900f4d87
ms.date: 05/02/2018
keywords: ["FWPS_FIELDS_INBOUND_TRANSPORT_V4_ enumeration"]
ms.keywords: FWPS_FIELDS_INBOUND_TRANSPORT_V4, FWPS_FIELDS_INBOUND_TRANSPORT_V4 enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELDS_INBOUND_TRANSPORT_V4_, FWPS_FIELD_INBOUND_TRANSPORT_V4_FLAGS, FWPS_FIELD_INBOUND_TRANSPORT_V4_INTERFACE_INDEX, FWPS_FIELD_INBOUND_TRANSPORT_V4_INTERFACE_TYPE, FWPS_FIELD_INBOUND_TRANSPORT_V4_IP_LOCAL_ADDRESS, FWPS_FIELD_INBOUND_TRANSPORT_V4_IP_LOCAL_ADDRESS_TYPE, FWPS_FIELD_INBOUND_TRANSPORT_V4_IP_LOCAL_INTERFACE, FWPS_FIELD_INBOUND_TRANSPORT_V4_IP_LOCAL_PORT, FWPS_FIELD_INBOUND_TRANSPORT_V4_IP_PROTOCOL, FWPS_FIELD_INBOUND_TRANSPORT_V4_IP_REMOTE_ADDRESS, FWPS_FIELD_INBOUND_TRANSPORT_V4_IP_REMOTE_PORT, FWPS_FIELD_INBOUND_TRANSPORT_V4_MAX, FWPS_FIELD_INBOUND_TRANSPORT_V4_PROFILE_ID, FWPS_FIELD_INBOUND_TRANSPORT_V4_SUB_INTERFACE_INDEX, FWPS_FIELD_INBOUND_TRANSPORT_V4_TUNNEL_TYPE, fwpsk/FWPS_FIELDS_INBOUND_TRANSPORT_V4, fwpsk/FWPS_FIELD_INBOUND_TRANSPORT_V4_FLAGS, fwpsk/FWPS_FIELD_INBOUND_TRANSPORT_V4_INTERFACE_INDEX, fwpsk/FWPS_FIELD_INBOUND_TRANSPORT_V4_INTERFACE_TYPE, fwpsk/FWPS_FIELD_INBOUND_TRANSPORT_V4_IP_LOCAL_ADDRESS, fwpsk/FWPS_FIELD_INBOUND_TRANSPORT_V4_IP_LOCAL_ADDRESS_TYPE, fwpsk/FWPS_FIELD_INBOUND_TRANSPORT_V4_IP_LOCAL_INTERFACE, fwpsk/FWPS_FIELD_INBOUND_TRANSPORT_V4_IP_LOCAL_PORT, fwpsk/FWPS_FIELD_INBOUND_TRANSPORT_V4_IP_PROTOCOL, fwpsk/FWPS_FIELD_INBOUND_TRANSPORT_V4_IP_REMOTE_ADDRESS, fwpsk/FWPS_FIELD_INBOUND_TRANSPORT_V4_IP_REMOTE_PORT, fwpsk/FWPS_FIELD_INBOUND_TRANSPORT_V4_MAX, fwpsk/FWPS_FIELD_INBOUND_TRANSPORT_V4_PROFILE_ID, fwpsk/FWPS_FIELD_INBOUND_TRANSPORT_V4_SUB_INTERFACE_INDEX, fwpsk/FWPS_FIELD_INBOUND_TRANSPORT_V4_TUNNEL_TYPE, netvista.fwps_fields_inbound_transport_v4, wfp_ref_5_const_3_data_fields_e98b5edb-d24a-4eed-a907-13c7f089b342.xml
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
targetos: Windows
req.typenames: FWPS_FIELDS_INBOUND_TRANSPORT_V4
f1_keywords:
 - FWPS_FIELDS_INBOUND_TRANSPORT_V4_
 - fwpsk/FWPS_FIELDS_INBOUND_TRANSPORT_V4_
 - FWPS_FIELDS_INBOUND_TRANSPORT_V4
 - fwpsk/FWPS_FIELDS_INBOUND_TRANSPORT_V4
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - fwpsk.h
api_name:
 - FWPS_FIELDS_INBOUND_TRANSPORT_V4
---

# FWPS_FIELDS_INBOUND_TRANSPORT_V4_ enumeration


## -description

The FWPS_FIELDS_INBOUND_TRANSPORT_V4 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_INBOUND_TRANSPORT_V4 and FWPS_LAYER_INBOUND_TRANSPORT_V4_DISCARD 
  <a href="https://docs.microsoft.com/windows/desktop/FWP/management-filtering-layer-identifiers-">run-time filtering layers</a>.

## -enum-fields

### -field FWPS_FIELD_INBOUND_TRANSPORT_V4_IP_PROTOCOL

The IP protocol number, as specified in RFC 1700.

### -field FWPS_FIELD_INBOUND_TRANSPORT_V4_IP_LOCAL_ADDRESS

The local IP address.

### -field FWPS_FIELD_INBOUND_TRANSPORT_V4_IP_REMOTE_ADDRESS

The remote IP address.

### -field FWPS_FIELD_INBOUND_TRANSPORT_V4_IP_LOCAL_ADDRESS_TYPE

The local IP address type. The possible values are defined by the 
     <a href="https://docs.microsoft.com/windows/desktop/api/nldef/ne-nldef-nl_address_type">NL_ADDRESS_TYPE</a> enumeration.

### -field FWPS_FIELD_INBOUND_TRANSPORT_V4_IP_LOCAL_PORT

The local transport protocol port number.

### -field FWPS_FIELD_INBOUND_TRANSPORT_V4_IP_REMOTE_PORT

The remote transport protocol port number.

### -field FWPS_FIELD_INBOUND_TRANSPORT_V4_IP_LOCAL_INTERFACE

The locally unique identifier (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/igpupvdev/ns-igpupvdev-_luid">LUID</a>) for the network interface associated with the
     local IP address.

### -field FWPS_FIELD_INBOUND_TRANSPORT_V4_INTERFACE_INDEX

The index of the network interface, as enumerated by the network stack.

### -field FWPS_FIELD_INBOUND_TRANSPORT_V4_SUB_INTERFACE_INDEX

The index of the logical network interface, as enumerated by the network stack.

### -field FWPS_FIELD_INBOUND_TRANSPORT_V4_FLAGS

A bitwise OR of a combination of filtering condition flags. For information about the possible
     flags, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/filtering-condition-flags">Filtering Condition Flags</a>.

### -field FWPS_FIELD_INBOUND_TRANSPORT_V4_INTERFACE_TYPE

The type of the local network interface, as defined by the Internet Assigned Numbers Authority
     (IANA). For more information, see 
     <a href="https://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a>.

### -field FWPS_FIELD_INBOUND_TRANSPORT_V4_TUNNEL_TYPE

The encapsulation method used by a tunnel if the 
     <b>IfType</b> member of the IP_ADAPTER_ADDRESSES structure is IF_TYPE_TUNNEL. The tunnel type is defined
     by IANA. For more information, see 
     <a href="https://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a> and the
     Windows SDK.

### -field FWPS_FIELD_INBOUND_TRANSPORT_V4_PROFILE_ID

The profile identifier (network category) of the network interface. The possible network category
     values are: public (1), private (2), or domain (3).
     

<div class="alert"><b>Note</b>  Supported starting with Windows 7.</div>
<div> </div>

### -field FWPS_FIELD_INBOUND_TRANSPORT_V4_IPSEC_SECURITY_REALM_ID

The IPsec security realm identifier.

### -field FWPS_FIELD_INBOUND_TRANSPORT_V4_COMPARTMENT_ID

The compartment that the network interface belongs to.

<div class="alert"><b>Note</b>  Supported starting with Windows 10, version 1703.</div>
<div> </div>

### -field FWPS_FIELD_INBOUND_TRANSPORT_V4_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.

## -remarks

The following macros in 
    <i>Fwpsk.h</i> are defined with FWPS_FIELDS_INBOUND_TRANSPORT_V4 enumeration
    values:


```

#define FWPS_FIELD_INBOUND_TRANSPORT_V4_ICMP_TYPE \
        FWPS_FIELD_INBOUND_TRANSPORT_V4_IP_LOCAL_PORT

#define FWPS_FIELD_INBOUND_TRANSPORT_V4_ICMP_CODE \
        FWPS_FIELD_INBOUND_TRANSPORT_V4_IP_REMOTE_PORT

```

These macros are used to access the following IPV4 data fields:

FWPS_FIELD_INBOUND_TRANSPORT_V4_ICMP_TYPE  
The ICMP type field, as specified in RFC 792.

FWPS_FIELD_INBOUND_TRANSPORT_V4_ICMP_CODE  
The ICMP code field, as specified in RFC 792.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/igpupvdev/ns-igpupvdev-_luid">LUID</a>



<a href="https://docs.microsoft.com/windows/desktop/api/nldef/ne-nldef-nl_address_type">NL_ADDRESS_TYPE</a>

