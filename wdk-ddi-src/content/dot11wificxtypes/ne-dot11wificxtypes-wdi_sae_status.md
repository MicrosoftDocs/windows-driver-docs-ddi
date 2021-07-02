---
UID: NE:dot11wificxtypes._WDI_SAE_STATUS
tech.root: netvista
title: WDI_SAE_STATUS (dot11wificxtypes.h)
ms.date: 07/01/2021
targetos: Windows
description: 
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dot11wificxtypes.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dot11wificxtypes.h
api_name:
 - _WDI_SAE_STATUS
 - WDI_SAE_STATUS
f1_keywords:
 - _WDI_SAE_STATUS
 - dot11wificxtypes/_WDI_SAE_STATUS
 - WDI_SAE_STATUS
 - dot11wificxtypes/WDI_SAE_STATUS
dev_langs:
 - c++
---

## -description

The **WDI_SAE_STATUS** enumeration defines SAE authentication failure error status codes. This enumeration is used to provide failure codes from the OS to the WiFiCx driver, or from the driver to the OS.

## -enum-fields

### -field WDI_SAE_STATUS_SUCCESS 

The operation completed successfully.

### -field WDI_SAE_STATUS_FAILURE 

The operation completed with failure.

### -field WDI_SAE_STATUS_RESOURCES 

The driver encountered a resource allocation error.

### -field WDI_SAE_STATUS_INTERNAL_AUTH_FAILURE 

### -field WDI_SAE_STATUS_INVALID_PEER 

### -field WDI_SAE_STATUS_INITIALIZATION_NO_KEY 

### -field WDI_SAE_STATUS_INITIALIZATION_H2E_NOT_SUPPORTED

### -field WDI_SAE_STATUS_INITIALIZATION_PWD_ID_NOT_SUPPORTED

### -field WDI_SAE_STATUS_COMMIT_MESSAGE_RECEIVED_IN_NOTHING_STATE

### -field WDI_SAE_STATUS_COMMIT_MESSAGE_MALFORMED_AUTH_FRAME

### -field WDI_SAE_STATUS_COMMIT_MESSAGE_FAILURE_FROM_PEER

### -field WDI_SAE_STATUS_COMMIT_MESSAGE_FINITE_GROUP_NOT_PRESENT

### -field WDI_SAE_STATUS_COMMIT_MESSAGE_UNSUPPORTED_FINITE_GROUP

### -field WDI_SAE_STATUS_COMMIT_MESSAGE_ANTICLOGGING_TOKEN_REQUIRED_BUT_NO_TOKEN

### -field WDI_SAE_STATUS_COMMIT_MESSAGE_INVALID_SCALAR_ELEMENT_SIZE

### -field WDI_SAE_STATUS_COMMIT_MESSAGE_REFLECTION_ATTACK_DETECTED

### -field WDI_SAE_STATUS_COMMIT_MESSAGE_INTERNAL_COMPUTATION_ERROR

### -field WDI_SAE_STATUS_CONFIRM_MESSAGE_RECEIVED_IN_INVALID_STATE

### -field WDI_SAE_STATUS_CONFIRM_MESSAGE_MALFORMED_AUTH_FRAME

### -field WDI_SAE_STATUS_CONFIRM_MESSAGE_FAILURE_FROM_PEER

### -field WDI_SAE_STATUS_CONFIRM_MESSAGE_BSS_TRANSITION_REQUESTED

### -field WDI_SAE_STATUS_CONFIRM_MESSAGE_INTERNAL_COMPUTATION_ERROR

### -field WDI_SAE_STATUS_CONFIRM_MESSAGE_VERIFICATION_FAILED

### -field WDI_SAE_STATUS_CONFIRM_MESSAGE_RESEND_REQUEST

The driver requests a new set of Confirm frame parameters to resend the Confirm request to the AP.

### -field WDI_SAE_STATUS_TIMEOUT_WAITING_FOR_COMMIT_REQUEST

### -field WDI_SAE_STATUS_TIMEOUT_WAITING_FOR_CONFIRM_REQUEST

### -field WDI_SAE_STATUS_TIMEOUT_WAITING_FOR_STATUS

### -field WDI_SAE_STATUS_CONNECTION_CLEANED_UP

### -field WDI_SAE_STATUS_CLEAN_UP_CONTEXT

## -remarks

This enumeration is a value in both the [OID_WDI_SET_SAE_AUTH_PARAMS](/windows-hardware/drivers/netcx/oid-wdi-set-sae-auth-params) command and the [NDIS_STATUS_WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED](/windows-hardware/drivers/netcx/ndis-status-wdi-indication-sae-auth-params-needed) indication.

## -see-also

[WPA3-SAE Authentication](/windows-hardware/drivers/netcx/wpa3-sae-authentication)

[OID_WDI_SET_SAE_AUTH_PARAMS](/windows-hardware/drivers/netcx/oid-wdi-set-sae-auth-params)

[NDIS_STATUS_WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED](/windows-hardware/drivers/netcx/ndis-status-wdi-indication-sae-auth-params-needed)

