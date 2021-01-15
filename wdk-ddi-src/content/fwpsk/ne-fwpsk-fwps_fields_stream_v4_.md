---
UID: NE:fwpsk.FWPS_FIELDS_STREAM_V4_
title: FWPS_FIELDS_STREAM_V4_ (fwpsk.h)
description: The FWPS_FIELDS_STREAM_V4 enumeration type specifies the data field identifiers for the FWPS_LAYER_STREAM_V4 and FWPS_LAYER_STREAM_V4_DISCARD run-time filtering layers.
old-location: netvista\fwps_fields_stream_v4.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["FWPS_FIELDS_STREAM_V4_ enumeration"]
ms.keywords: FWPS_FIELDS_STREAM_V4, FWPS_FIELDS_STREAM_V4 enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELDS_STREAM_V4_, FWPS_FIELD_STREAM_V4_DIRECTION, FWPS_FIELD_STREAM_V4_FLAGS, FWPS_FIELD_STREAM_V4_IP_LOCAL_ADDRESS, FWPS_FIELD_STREAM_V4_IP_LOCAL_ADDRESS_TYPE, FWPS_FIELD_STREAM_V4_IP_LOCAL_PORT, FWPS_FIELD_STREAM_V4_IP_REMOTE_ADDRESS, FWPS_FIELD_STREAM_V4_IP_REMOTE_PORT, FWPS_FIELD_STREAM_V4_MAX, fwpsk/FWPS_FIELDS_STREAM_V4, fwpsk/FWPS_FIELD_STREAM_V4_DIRECTION, fwpsk/FWPS_FIELD_STREAM_V4_FLAGS, fwpsk/FWPS_FIELD_STREAM_V4_IP_LOCAL_ADDRESS, fwpsk/FWPS_FIELD_STREAM_V4_IP_LOCAL_ADDRESS_TYPE, fwpsk/FWPS_FIELD_STREAM_V4_IP_LOCAL_PORT, fwpsk/FWPS_FIELD_STREAM_V4_IP_REMOTE_ADDRESS, fwpsk/FWPS_FIELD_STREAM_V4_IP_REMOTE_PORT, fwpsk/FWPS_FIELD_STREAM_V4_MAX, netvista.fwps_fields_stream_v4, wfp_ref_5_const_3_data_fields_767d81c5-f927-4512-812d-396966457b7a.xml
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
req.typenames: FWPS_FIELDS_STREAM_V4
f1_keywords:
 - FWPS_FIELDS_STREAM_V4_
 - fwpsk/FWPS_FIELDS_STREAM_V4_
 - FWPS_FIELDS_STREAM_V4
 - fwpsk/FWPS_FIELDS_STREAM_V4
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - fwpsk.h
api_name:
 - FWPS_FIELDS_STREAM_V4_
 - FWPS_FIELDS_STREAM_V4
---

# FWPS_FIELDS_STREAM_V4_ enumeration


## -description

The FWPS_FIELDS_STREAM_V4 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_STREAM_V4 and FWPS_LAYER_STREAM_V4_DISCARD 
  <a href="/windows/desktop/FWP/management-filtering-layer-identifiers-">run-time filtering layers</a>.

## -enum-fields

### -field FWPS_FIELD_STREAM_V4_IP_LOCAL_ADDRESS

The local IP address.

### -field FWPS_FIELD_STREAM_V4_IP_LOCAL_ADDRESS_TYPE

The local IP address type. The possible values are defined by the 
     <a href="/windows/win32/api/nldef/ne-nldef-nl_address_type">NL_ADDRESS_TYPE</a> enumeration.

### -field FWPS_FIELD_STREAM_V4_IP_REMOTE_ADDRESS

The remote IP address.

### -field FWPS_FIELD_STREAM_V4_IP_LOCAL_PORT

The local transport protocol port number.

### -field FWPS_FIELD_STREAM_V4_IP_REMOTE_PORT

The remote transport protocol port number.

### -field FWPS_FIELD_STREAM_V4_DIRECTION

The possible values are:

<ul><li>FWP_DIRECTION_INBOUND</li><li>FWP_DIRECTION_OUTBOUND</li></ul>

### -field FWPS_FIELD_STREAM_V4_FLAGS

A bitwise OR of a combination of filtering condition flags. For information about the possible
     flags, see 
     <a href="/windows-hardware/drivers/network/filtering-condition-flags">Filtering Condition Flags</a>.
     

<div class="alert"><b>Note</b>  Supported in Windows Server 2008, Windows Vista SP1, and later versions of
     Windows.</div>
<div> </div>

### -field FWPS_FIELD_STREAM_V4_COMPARTMENT_ID

The compartment that the network interface belongs to.

<div class="alert"><b>Note</b>  Supported starting with Windows 10, version 1703.</div>
<div> </div>

### -field FWPS_FIELD_STREAM_V4_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.

## -see-also

<a href="/windows/win32/api/nldef/ne-nldef-nl_address_type">NL_ADDRESS_TYPE</a>

