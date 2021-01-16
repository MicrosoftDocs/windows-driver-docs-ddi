---
UID: NE:fwpsk.FWPS_FIELDS_NAME_RESOLUTION_CACHE_V4_
title: FWPS_FIELDS_NAME_RESOLUTION_CACHE_V4_ (fwpsk.h)
description: The FWPS_FIELDS_NAME_RESOLUTION_CACHE_V4 enumeration type specifies the data field identifiers for the FWPS_LAYER_NAME_RESOLUTION_CACHE_V4 run-time filtering layer.
old-location: netvista\fwps_fields_name_resolution_cache_v4.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["FWPS_FIELDS_NAME_RESOLUTION_CACHE_V4_ enumeration"]
ms.keywords: FWPS_FIELDS_NAME_RESOLUTION_CACHE_V4, FWPS_FIELDS_NAME_RESOLUTION_CACHE_V4 enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELDS_NAME_RESOLUTION_CACHE_V4_, FWPS_FIELD_NAME_RESOLUTION_CACHE_V4_ALE_APP_ID, FWPS_FIELD_NAME_RESOLUTION_CACHE_V4_ALE_USER_ID, FWPS_FIELD_NAME_RESOLUTION_CACHE_V4_IP_REMOTE_ADDRESS, FWPS_FIELD_NAME_RESOLUTION_CACHE_V4_MAX, FWPS_FIELD_NAME_RESOLUTION_CACHE_V4_PEER_NAME, fwpsk/FWPS_FIELDS_NAME_RESOLUTION_CACHE_V4, fwpsk/FWPS_FIELD_NAME_RESOLUTION_CACHE_V4_ALE_APP_ID, fwpsk/FWPS_FIELD_NAME_RESOLUTION_CACHE_V4_ALE_USER_ID, fwpsk/FWPS_FIELD_NAME_RESOLUTION_CACHE_V4_IP_REMOTE_ADDRESS, fwpsk/FWPS_FIELD_NAME_RESOLUTION_CACHE_V4_MAX, fwpsk/FWPS_FIELD_NAME_RESOLUTION_CACHE_V4_PEER_NAME, netvista.fwps_fields_name_resolution_cache_v4, wfp_ref_5_const_3_data_fields_b0351c61-f624-4a2f-8c20-bdbad78e143f.xml
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting withn Windows 7.
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
req.typenames: FWPS_FIELDS_NAME_RESOLUTION_CACHE_V4
f1_keywords:
 - FWPS_FIELDS_NAME_RESOLUTION_CACHE_V4_
 - fwpsk/FWPS_FIELDS_NAME_RESOLUTION_CACHE_V4_
 - FWPS_FIELDS_NAME_RESOLUTION_CACHE_V4
 - fwpsk/FWPS_FIELDS_NAME_RESOLUTION_CACHE_V4
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - fwpsk.h
api_name:
 - FWPS_FIELDS_NAME_RESOLUTION_CACHE_V4_
 - FWPS_FIELDS_NAME_RESOLUTION_CACHE_V4
---

# FWPS_FIELDS_NAME_RESOLUTION_CACHE_V4_ enumeration


## -description

The FWPS_FIELDS_NAME_RESOLUTION_CACHE_V4 enumeration type specifies the data field identifiers for
  the FWPS_LAYER_NAME_RESOLUTION_CACHE_V4 
  <a href="/windows/desktop/FWP/management-filtering-layer-identifiers-">run-time filtering layer</a>.

## -enum-fields

### -field FWPS_FIELD_NAME_RESOLUTION_CACHE_V4_ALE_USER_ID

The identifier of the local user.

### -field FWPS_FIELD_NAME_RESOLUTION_CACHE_V4_ALE_APP_ID

The full path of the application.

### -field FWPS_FIELD_NAME_RESOLUTION_CACHE_V4_IP_REMOTE_ADDRESS

The remote IP address.

### -field FWPS_FIELD_NAME_RESOLUTION_CACHE_V4_PEER_NAME

The machine name that is associated with the destination IP address.

### -field FWPS_FIELD_NAME_RESOLUTION_CACHE_V4_COMPARTMENT_ID

The compartment that the network interface belongs to.

<div class="alert"><b>Note</b>  Supported starting with Windows 10, version 1703.</div>
<div> </div>

### -field FWPS_FIELD_NAME_RESOLUTION_CACHE_V4_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.

