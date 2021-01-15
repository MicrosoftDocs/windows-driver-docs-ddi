---
UID: NE:fwpsk.FWPS_FIELDS_ALE_RESOURCE_RELEASE_V6_
title: FWPS_FIELDS_ALE_RESOURCE_RELEASE_V6_ (fwpsk.h)
description: The FWPS_FIELDS_ALE_RESOURCE_RELEASE_V6 enumeration type specifies the data field identifiers for the FWPS_LAYER_ALE_RESOURCE_RELEASE_V6 run-time filtering layer.
old-location: netvista\fwps_fields_ale_resource_release_v6.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["FWPS_FIELDS_ALE_RESOURCE_RELEASE_V6_ enumeration"]
ms.keywords: FWPS_FIELDS_ALE_RESOURCE_RELEASE_V6, FWPS_FIELDS_ALE_RESOURCE_RELEASE_V6 enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELDS_ALE_RESOURCE_RELEASE_V6_, FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_ALE_APP_ID, FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_ALE_PACKAGE_ID, FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_ALE_USER_ID, FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_FLAGS, FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_IP_LOCAL_ADDRESS, FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_IP_LOCAL_ADDRESS_TYPE, FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_IP_LOCAL_INTERFACE, FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_IP_LOCAL_PORT, FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_IP_PROTOCOL, FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_MAX, fwpsk/FWPS_FIELDS_ALE_RESOURCE_RELEASE_V6, fwpsk/FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_ALE_APP_ID, fwpsk/FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_ALE_PACKAGE_ID, fwpsk/FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_ALE_USER_ID, fwpsk/FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_FLAGS, fwpsk/FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_IP_LOCAL_ADDRESS, fwpsk/FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_IP_LOCAL_ADDRESS_TYPE, fwpsk/FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_IP_LOCAL_INTERFACE, fwpsk/FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_IP_LOCAL_PORT, fwpsk/FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_IP_PROTOCOL, fwpsk/FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_MAX, netvista.fwps_fields_ale_resource_release_v6, wfp_ref_5_const_3_data_fields_9f6f966e-3799-4c75-bfcb-0a3e711e3aea.xml
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 7.
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
req.typenames: FWPS_FIELDS_ALE_RESOURCE_RELEASE_V6
f1_keywords:
 - FWPS_FIELDS_ALE_RESOURCE_RELEASE_V6_
 - fwpsk/FWPS_FIELDS_ALE_RESOURCE_RELEASE_V6_
 - FWPS_FIELDS_ALE_RESOURCE_RELEASE_V6
 - fwpsk/FWPS_FIELDS_ALE_RESOURCE_RELEASE_V6
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - fwpsk.h
api_name:
 - FWPS_FIELDS_ALE_RESOURCE_RELEASE_V6_
 - FWPS_FIELDS_ALE_RESOURCE_RELEASE_V6
---

# FWPS_FIELDS_ALE_RESOURCE_RELEASE_V6_ enumeration


## -description

The FWPS_FIELDS_ALE_RESOURCE_RELEASE_V6 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_ALE_RESOURCE_RELEASE_V6 
  <a href="/windows/desktop/FWP/management-filtering-layer-identifiers-">run-time filtering layer</a>.

## -enum-fields

### -field FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_ALE_APP_ID

The full path of the application.

### -field FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_ALE_USER_ID

The identifier of the local user.

### -field FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_IP_LOCAL_ADDRESS

The local IP address.

### -field FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_IP_LOCAL_ADDRESS_TYPE

The local IP address type. The possible values are defined by the 
     <a href="/windows/win32/api/nldef/ne-nldef-nl_address_type">NL_ADDRESS_TYPE</a> enumeration.

### -field FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_IP_LOCAL_PORT

The local transport protocol port number.

### -field FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_IP_PROTOCOL

The IP protocol number, as specified in RFC 1700.

### -field FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_IP_LOCAL_INTERFACE

The locally unique identifier (<a href="/windows-hardware/drivers/ddi/igpupvdev/ns-igpupvdev-_luid">LUID</a>) for the network interface associated with the
     local IP address.

### -field FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_FLAGS

A bitwise OR of a combination of filtering condition flags. For information about the possible
     flags, see 
     <a href="/windows-hardware/drivers/network/filtering-condition-flags">Filtering Condition Flags</a>.

### -field FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_ALE_PACKAGE_ID

The package identifier is a security identifier (SID) that identifies the associated AppContainer process. For more information about the SID structure, see the description for the SID structure in the Microsoft Windows SDK documentation.

<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div>
<div> </div>

### -field FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_ALE_SECURITY_ATTRIBUTE_FQBN_VALUE

The fully qualified binary name (FQBN) value of the application.

<div class="alert"><b>Note</b>  Supported starting with Windows 10.</div>
<div> </div>

### -field FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_COMPARTMENT_ID

The compartment that the network interface belongs to.

<div class="alert"><b>Note</b>  Supported starting with Windows 10, version 1703.</div>
<div> </div>

### -field FWPS_FIELD_ALE_RESOURCE_RELEASE_V6_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.

## -see-also

<a href="/windows-hardware/drivers/ddi/igpupvdev/ns-igpupvdev-_luid">LUID</a>



<a href="/windows/win32/api/nldef/ne-nldef-nl_address_type">NL_ADDRESS_TYPE</a>

