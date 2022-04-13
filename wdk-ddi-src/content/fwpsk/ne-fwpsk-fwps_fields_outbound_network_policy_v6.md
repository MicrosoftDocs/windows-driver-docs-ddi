---
UID: NE:fwpsk.FWPS_FIELDS_OUTBOUND_NETWORK_CONNECTION_POLICY_V6_
tech.root: netvista
title: FWPS_FIELDS_OUTBOUND_NETWORK_POLICY_V6
ms.date: 03/28/2022
targetos: Windows
description: The FWPS_FIELDS_OUTBOUND_NETWORK_POLICY_V6 enumeration type specifies the data field identifiers for the FWPS_LAYER_OUTBOUND_NETWORK_CONNECTION_POLICY_V6 run-time filtering layer.
prerelease: true
req.construct-type: enumeration
req.ddi-compliance: 
req.header: fwpsk.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: WIN11_NEXT
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - fwpsk.h
api_name:
 - FWPS_FIELDS_OUTBOUND_NETWORK_CONNECTION_POLICY_V6_
 - FWPS_FIELDS_OUTBOUND_NETWORK_POLICY_V6
f1_keywords:
 - FWPS_FIELDS_OUTBOUND_NETWORK_CONNECTION_POLICY_V6_
 - fwpsk/FWPS_FIELDS_OUTBOUND_NETWORK_CONNECTION_POLICY_V6_
 - FWPS_FIELDS_OUTBOUND_NETWORK_POLICY_V6
 - fwpsk/FWPS_FIELDS_OUTBOUND_NETWORK_POLICY_V6
dev_langs:
 - c++
helpviewer_keywords:
 - FWPS_FIELDS_OUTBOUND_NETWORK_CONNECTION_POLICY_V6_
---

## -description

The FWPS_FIELDS_OUTBOUND_NETWORK_POLICY_V6 enumeration type specifies the data field identifiers for the FWPS_LAYER_OUTBOUND_NETWORK_CONNECTION_POLICY_V6 [run-time filtering layer](/windows-hardware/drivers/network/run-time-filtering-layer-identifiers).

## -enum-fields

### -field FWPS_FIELD_OUTBOUND_NETWORK_CONNECTION_POLICY_V6_ALE_APP_ID

The full path of the application.

### -field FWPS_FIELD_OUTBOUND_NETWORK_CONNECTION_POLICY_V6_ALE_USER_ID

The identifier of the local user.

### -field FWPS_FIELD_OUTBOUND_NETWORK_CONNECTION_POLICY_V6_IP_LOCAL_ADDRESS

The local IP address.

### -field FWPS_FIELD_OUTBOUND_NETWORK_CONNECTION_POLICY_V6_IP_LOCAL_ADDRESS_TYPE

The local IP address type. The possible values are defined by the [**NL_ADDRESS_TYPE**](/windows/win32/api/nldef/ne-nldef-nl_address_type) enumeration.

### -field FWPS_FIELD_OUTBOUND_NETWORK_CONNECTION_POLICY_V6_IP_LOCAL_PORT

The local transport protocol port number.

### -field FWPS_FIELD_OUTBOUND_NETWORK_CONNECTION_POLICY_V6_IP_PROTOCOL

The IP protocol number, as specified in RFC 1700.

### -field FWPS_FIELD_OUTBOUND_NETWORK_CONNECTION_POLICY_V6_IP_REMOTE_ADDRESS

The remote IP address.

### -field FWPS_FIELD_OUTBOUND_NETWORK_CONNECTION_POLICY_V6_IP_DESTINATION_ADDRESS_TYPE

The destination IP address type. The possible values are defined by the [**NL_ADDRESS_TYPE**](/windows/win32/api/nldef/ne-nldef-nl_address_type) enumeration.

### -field FWPS_FIELD_OUTBOUND_NETWORK_CONNECTION_POLICY_V6_IP_REMOTE_PORT

The remote transport protocol port number.

### -field FWPS_FIELD_OUTBOUND_NETWORK_CONNECTION_POLICY_V6_FLAGS

A bitwise OR of a combination of filtering condition flags. For information about the possible flags, see [**Filtering Condition Flags**](/windows-hardware/drivers/network/filtering-condition-flags).


### -field FWPS_FIELD_OUTBOUND_NETWORK_CONNECTION_POLICY_V6_ALE_ORIGINAL_APP_ID

The full path of the original application for proxy connections. If the application has not been proxied, this path is identical to the xxx_ALE_APP_ID.

### -field FWPS_FIELD_OUTBOUND_NETWORK_CONNECTION_POLICY_V6_ALE_PACKAGE_ID

The package identifier is a security identifier (SID) that identifies the associated AppContainer process. For more information about the SID structure, see the description for the SID structure in the Microsoft Windows SDK documentation.

### -field FWPS_FIELD_OUTBOUND_NETWORK_CONNECTION_POLICY_V6_ALE_SECURITY_ATTRIBUTE_FQBN_VALUE

The fully qualified binary name (FQBN) value of the application.

### -field FWPS_FIELD_OUTBOUND_NETWORK_CONNECTION_POLICY_V6_COMPARTMENT_ID

The compartment that the network interface belongs to.

### -field FWPS_FIELD_OUTBOUND_NETWORK_CONNECTION_POLICY_V6_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS header files and binaries.

## -remarks

## -see-also

[**NL_ADDRESS_TYPE**](/windows/win32/api/nldef/ne-nldef-nl_address_type)

[**Filtering Condition Flags**](/windows-hardware/drivers/network/filtering-condition-flags)

