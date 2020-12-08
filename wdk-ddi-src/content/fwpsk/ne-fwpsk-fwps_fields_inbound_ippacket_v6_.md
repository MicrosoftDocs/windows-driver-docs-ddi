---
UID: NE:fwpsk.FWPS_FIELDS_INBOUND_IPPACKET_V6_
title: FWPS_FIELDS_INBOUND_IPPACKET_V6_ (fwpsk.h)
description: The FWPS_FIELDS_INBOUND_IPPACKET_V6 enumeration type specifies the data field identifiers for the FWPS_LAYER_INBOUND_IPPACKET_V6 and FWPS_LAYER_INBOUND_IPPACKET_V6_DISCARD run-time filtering layers.
old-location: netvista\fwps_fields_inbound_ippacket_v6.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["FWPS_FIELDS_INBOUND_IPPACKET_V6_ enumeration"]
ms.keywords: FWPS_FIELDS_INBOUND_IPPACKET_V6, FWPS_FIELDS_INBOUND_IPPACKET_V6 enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELDS_INBOUND_IPPACKET_V6_, FWPS_FIELD_INBOUND_IPPACKET_V6_FLAGS, FWPS_FIELD_INBOUND_IPPACKET_V6_INTERFACE_INDEX, FWPS_FIELD_INBOUND_IPPACKET_V6_INTERFACE_TYPE, FWPS_FIELD_INBOUND_IPPACKET_V6_IP_LOCAL_ADDRESS, FWPS_FIELD_INBOUND_IPPACKET_V6_IP_LOCAL_ADDRESS_TYPE, FWPS_FIELD_INBOUND_IPPACKET_V6_IP_LOCAL_INTERFACE, FWPS_FIELD_INBOUND_IPPACKET_V6_IP_REMOTE_ADDRESS, FWPS_FIELD_INBOUND_IPPACKET_V6_MAX, FWPS_FIELD_INBOUND_IPPACKET_V6_SUB_INTERFACE_INDEX, FWPS_FIELD_INBOUND_IPPACKET_V6_TUNNEL_TYPE, fwpsk/FWPS_FIELDS_INBOUND_IPPACKET_V6, fwpsk/FWPS_FIELD_INBOUND_IPPACKET_V6_FLAGS, fwpsk/FWPS_FIELD_INBOUND_IPPACKET_V6_INTERFACE_INDEX, fwpsk/FWPS_FIELD_INBOUND_IPPACKET_V6_INTERFACE_TYPE, fwpsk/FWPS_FIELD_INBOUND_IPPACKET_V6_IP_LOCAL_ADDRESS, fwpsk/FWPS_FIELD_INBOUND_IPPACKET_V6_IP_LOCAL_ADDRESS_TYPE, fwpsk/FWPS_FIELD_INBOUND_IPPACKET_V6_IP_LOCAL_INTERFACE, fwpsk/FWPS_FIELD_INBOUND_IPPACKET_V6_IP_REMOTE_ADDRESS, fwpsk/FWPS_FIELD_INBOUND_IPPACKET_V6_MAX, fwpsk/FWPS_FIELD_INBOUND_IPPACKET_V6_SUB_INTERFACE_INDEX, fwpsk/FWPS_FIELD_INBOUND_IPPACKET_V6_TUNNEL_TYPE, netvista.fwps_fields_inbound_ippacket_v6, wfp_ref_5_const_3_data_fields_7185d69a-4508-4b06-b2e3-edee65a7f8c0.xml
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows Vista.
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
req.typenames: FWPS_FIELDS_INBOUND_IPPACKET_V6
f1_keywords:
 - FWPS_FIELDS_INBOUND_IPPACKET_V6_
 - fwpsk/FWPS_FIELDS_INBOUND_IPPACKET_V6_
 - FWPS_FIELDS_INBOUND_IPPACKET_V6
 - fwpsk/FWPS_FIELDS_INBOUND_IPPACKET_V6
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - fwpsk.h
api_name:
 - FWPS_FIELDS_INBOUND_IPPACKET_V6
---

# FWPS_FIELDS_INBOUND_IPPACKET_V6_ enumeration


## -description

The FWPS_FIELDS_INBOUND_IPPACKET_V6 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_INBOUND_IPPACKET_V6 and FWPS_LAYER_INBOUND_IPPACKET_V6_DISCARD 
  <a href="/windows/desktop/FWP/management-filtering-layer-identifiers-">run-time filtering layers</a>.

## -enum-fields

### -field FWPS_FIELD_INBOUND_IPPACKET_V6_IP_LOCAL_ADDRESS

The local IP address.

### -field FWPS_FIELD_INBOUND_IPPACKET_V6_IP_REMOTE_ADDRESS

The remote IP address.

### -field FWPS_FIELD_INBOUND_IPPACKET_V6_IP_LOCAL_ADDRESS_TYPE

The local IP address type. The possible values are defined by the 
     <a href="/windows/win32/api/nldef/ne-nldef-nl_address_type">NL_ADDRESS_TYPE</a> enumeration

### -field FWPS_FIELD_INBOUND_IPPACKET_V6_IP_LOCAL_INTERFACE

The locally unique identifier (<a href="/windows-hardware/drivers/ddi/igpupvdev/ns-igpupvdev-_luid">LUID</a>) for the network interface associated with the
     local IP address.

### -field FWPS_FIELD_INBOUND_IPPACKET_V6_INTERFACE_INDEX

The index of the network interface, as enumerated by the network stack.

### -field FWPS_FIELD_INBOUND_IPPACKET_V6_SUB_INTERFACE_INDEX

The index of the logical network interface, as enumerated by the network stack.

### -field FWPS_FIELD_INBOUND_IPPACKET_V6_FLAGS

A bitwise OR of a combination of filtering condition flags. For information about the possible
     flags, see 
     <a href="/windows-hardware/drivers/network/filtering-condition-flags">Filtering Condition Flags</a>.

### -field FWPS_FIELD_INBOUND_IPPACKET_V6_INTERFACE_TYPE

The type of the network interface, as defined by the Internet Assigned Numbers Authority (IANA).
     For more information, see 
     <a href="https://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a>.

### -field FWPS_FIELD_INBOUND_IPPACKET_V6_TUNNEL_TYPE

The encapsulation method used by a tunnel if the 
     <b>IfType</b> member of the IP_ADAPTER_ADDRESSES structure is IF_TYPE_TUNNEL. The tunnel type is defined
     by IANA. For more information, see 
     <a href="https://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a> and the
     Windows SDK.

### -field FWPS_FIELD_INBOUND_IPPACKET_V6_COMPARTMENT_ID

The compartment that the network interface belongs to.

<div class="alert"><b>Note</b>  Supported starting with Windows 10, version 1703.</div>
<div> </div>

### -field FWPS_FIELD_INBOUND_IPPACKET_V6_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.

## -see-also

<a href="/windows-hardware/drivers/ddi/igpupvdev/ns-igpupvdev-_luid">LUID</a>



<a href="/windows/win32/api/nldef/ne-nldef-nl_address_type">NL_ADDRESS_TYPE</a>
