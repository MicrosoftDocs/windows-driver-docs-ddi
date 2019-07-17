---
UID: NE:fwpsk.FWPS_FIELDS_ALE_ENDPOINT_CLOSURE_V4_
title: FWPS_FIELDS_ALE_ENDPOINT_CLOSURE_V4_ (fwpsk.h)
description: The FWPS_FIELDS_ALE_ENDPOINT_CLOSURE_V4 enumeration type specifies the data field identifiers for the FWPS_LAYER_ALE_ENDPOINT_CLOSURE_V4 run-time filtering layer.
old-location: netvista\fwps_fields_ale_endpoint_closure_v4.htm
tech.root: netvista
ms.assetid: 5d8479e8-b22c-4c2b-ad49-2b41dae34c88
ms.date: 05/02/2018
ms.keywords: FWPS_FIELDS_ALE_ENDPOINT_CLOSURE_V4, FWPS_FIELDS_ALE_ENDPOINT_CLOSURE_V4 enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELDS_ALE_ENDPOINT_CLOSURE_V4_, FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_ALE_APP_ID, FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_ALE_PACKAGE_ID, FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_ALE_USER_ID, FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_FLAGS, FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_IP_LOCAL_ADDRESS, FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_IP_LOCAL_ADDRESS_TYPE, FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_IP_LOCAL_INTERFACE, FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_IP_LOCAL_PORT, FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_IP_PROTOCOL, FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_IP_REMOTE_ADDRESS, FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_IP_REMOTE_PORT, FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_MAX, fwpsk/FWPS_FIELDS_ALE_ENDPOINT_CLOSURE_V4, fwpsk/FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_ALE_APP_ID, fwpsk/FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_ALE_PACKAGE_ID, fwpsk/FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_ALE_USER_ID, fwpsk/FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_FLAGS, fwpsk/FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_IP_LOCAL_ADDRESS, fwpsk/FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_IP_LOCAL_ADDRESS_TYPE, fwpsk/FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_IP_LOCAL_INTERFACE, fwpsk/FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_IP_LOCAL_PORT, fwpsk/FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_IP_PROTOCOL, fwpsk/FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_IP_REMOTE_ADDRESS, fwpsk/FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_IP_REMOTE_PORT, fwpsk/FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_MAX, netvista.fwps_fields_ale_endpoint_closure_v4, wfp_ref_5_const_3_data_fields_07afa825-78b7-456c-82f6-b57dd97bd533.xml
ms.topic: enum
f1_keywords:
 - "fwpsk/FWPS_FIELDS_ALE_ENDPOINT_CLOSURE_V4"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- fwpsk.h
api_name:
- FWPS_FIELDS_ALE_ENDPOINT_CLOSURE_V4
product:
- Windows
targetos: Windows
req.typenames: FWPS_FIELDS_ALE_ENDPOINT_CLOSURE_V4
---

# FWPS_FIELDS_ALE_ENDPOINT_CLOSURE_V4_ enumeration


## -description


The FWPS_FIELDS_ALE_ENDPOINT_CLOSURE_V4 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_ALE_ENDPOINT_CLOSURE_V4 
  <a href="https://docs.microsoft.com/windows/desktop/FWP/management-filtering-layer-identifiers-">run-time filtering layer</a>.


## -enum-fields




### -field FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_ALE_APP_ID

The full path of the application.


### -field FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_ALE_USER_ID

The identifier of the local user.


### -field FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_IP_LOCAL_ADDRESS

The local IP address.


### -field FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_IP_LOCAL_ADDRESS_TYPE

The local IP address type. The possible values are defined by the 
     <a href="https://docs.microsoft.com/windows/desktop/api/nldef/ne-nldef-nl_address_type">NL_ADDRESS_TYPE</a> enumeration.


### -field FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_IP_LOCAL_PORT

The local transport protocol port number.


### -field FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_IP_PROTOCOL

The IP protocol number, as specified in RFC 1700.


### -field FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_IP_REMOTE_ADDRESS

The remote IP address.


### -field FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_IP_REMOTE_PORT

The remote transport protocol port number.


### -field FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_IP_LOCAL_INTERFACE

The locally unique identifier (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/igpupvdev/ns-igpupvdev-_luid">LUID</a>) for the network interface associated with the
     local IP address.


### -field FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_FLAGS

A bitwise OR of a combination of filtering condition flags. For information about the possible
     flags, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/filtering-condition-flags">Filtering Condition Flags</a>.


### -field FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_ALE_PACKAGE_ID

The package identifier is a security identifier (SID) that identifies the associated AppContainer process. For more information about the SID structure, see the description for the SID structure in the Microsoft Windows SDK documentation.

<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div>
<div> </div>

### -field FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_ALE_SECURITY_ATTRIBUTE_FQBN_VALUE

The fully qualified binary name (FQBN) value of the application.

<div class="alert"><b>Note</b>  Supported starting with Windows 10.</div>
<div> </div>

### -field FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_COMPARTMENT_ID

The compartment that the network interface belongs to.

<div class="alert"><b>Note</b>  Supported starting with Windows 10, version 1703.</div>
<div> </div>


### -field FWPS_FIELD_ALE_ENDPOINT_CLOSURE_V4_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/igpupvdev/ns-igpupvdev-_luid">LUID</a>



<a href="https://docs.microsoft.com/windows/desktop/api/nldef/ne-nldef-nl_address_type">NL_ADDRESS_TYPE</a>
 

 

