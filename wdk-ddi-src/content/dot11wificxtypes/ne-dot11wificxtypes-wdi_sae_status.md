---
UID: NE:dot11wificxtypes._WDI_SAE_STATUS
tech.root: netvista
title: WDI_SAE_STATUS (dot11wificxtypes.h)
ms.date: 07/01/2021
targetos: Windows
description: The WDI_SAE_STATUS enum defines SAE authentication failure error status codes.
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

The operation completed with failure and none of the other status codes apply.

### -field WDI_SAE_STATUS_RESOURCES 

The driver encountered a resource allocation error.

### -field WDI_SAE_STATUS_INTERNAL_AUTH_FAILURE 

WDI encountered an internal authentication-related failure.

### -field WDI_SAE_STATUS_INVALID_PEER 

The Commit or Confirm response was received from an AP for which WDI did not provide SAE parameters.

### -field WDI_SAE_STATUS_INITIALIZATION_NO_KEY 

WDI doesn't have the password for this association request.

### -field WDI_SAE_STATUS_INITIALIZATION_H2E_NOT_SUPPORTED

AP requires Hash-To-Element support but the driver doesn't support Hash-To-Element.

### -field WDI_SAE_STATUS_INITIALIZATION_PWD_ID_NOT_SUPPORTED

AP requires Password-Identifier, but no Password-Identifier is available.

### -field WDI_SAE_STATUS_COMMIT_MESSAGE_RECEIVED_IN_NOTHING_STATE

Commit message was received in Nothing state.

### -field WDI_SAE_STATUS_COMMIT_MESSAGE_MALFORMED_AUTH_FRAME

A bad Commit frame was received.

### -field WDI_SAE_STATUS_COMMIT_MESSAGE_FAILURE_FROM_PEER

The commit frame from the peer contained an error code.

### -field WDI_SAE_STATUS_COMMIT_MESSAGE_FINITE_GROUP_NOT_PRESENT

The Finite Group was not present in the Commit frame.

### -field WDI_SAE_STATUS_COMMIT_MESSAGE_UNSUPPORTED_FINITE_GROUP

The Finite Group specified in the Commit frame is not supported.

### -field WDI_SAE_STATUS_COMMIT_MESSAGE_ANTICLOGGING_TOKEN_REQUIRED_BUT_NO_TOKEN

The Commit frame contained the error code requiring the anti-clogging token, but the frame did not contain the anti-clogging token.

### -field WDI_SAE_STATUS_COMMIT_MESSAGE_INVALID_SCALAR_ELEMENT_SIZE

The Commit frame did not contain enough space for the Scalar or Element fields.

### -field WDI_SAE_STATUS_COMMIT_MESSAGE_REFLECTION_ATTACK_DETECTED

WDI detected a reflection attack.

### -field WDI_SAE_STATUS_COMMIT_MESSAGE_INTERNAL_COMPUTATION_ERROR

WDI encountered an internal computation error.

### -field WDI_SAE_STATUS_CONFIRM_MESSAGE_RECEIVED_IN_INVALID_STATE

WDI received a Confirm frame when it was not expected.

### -field WDI_SAE_STATUS_CONFIRM_MESSAGE_MALFORMED_AUTH_FRAME

A bad Confirm frame was received.

### -field WDI_SAE_STATUS_CONFIRM_MESSAGE_FAILURE_FROM_PEER

An error was received in the Confirm frame.

### -field WDI_SAE_STATUS_CONFIRM_MESSAGE_BSS_TRANSITION_REQUESTED

WDI doesn't handle the Bss transition request.

### -field WDI_SAE_STATUS_CONFIRM_MESSAGE_INTERNAL_COMPUTATION_ERROR

WDI encountered an internal error.

### -field WDI_SAE_STATUS_CONFIRM_MESSAGE_VERIFICATION_FAILED

WDI failed to match the Verifier from the Confirm frame.

### -field WDI_SAE_STATUS_CONFIRM_MESSAGE_RESEND_REQUEST

The driver requests a new set of Confirm frame parameters to resend the Confirm request to the AP.

### -field WDI_SAE_STATUS_TIMEOUT_WAITING_FOR_COMMIT_REQUEST

The driver timed out waiting for a Commit Request from the OS.

### -field WDI_SAE_STATUS_TIMEOUT_WAITING_FOR_CONFIRM_REQUEST

The driver timed out waiting for a Confirm Request from the OS.

### -field WDI_SAE_STATUS_TIMEOUT_WAITING_FOR_STATUS

The driver timed out waiting for a Status from the OS.

### -field WDI_SAE_STATUS_CONNECTION_CLEANED_UP

### -field WDI_SAE_STATUS_CLEAN_UP_CONTEXT

## -remarks

This enumeration is a value in both the [OID_WDI_SET_SAE_AUTH_PARAMS](/windows-hardware/drivers/netcx/oid-wdi-set-sae-auth-params) command and the [NDIS_STATUS_WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED](/windows-hardware/drivers/netcx/ndis-status-wdi-indication-sae-auth-params-needed) indication.

## -see-also

[WPA3-SAE Authentication](/windows-hardware/drivers/netcx/wpa3-sae-authentication)

[OID_WDI_SET_SAE_AUTH_PARAMS](/windows-hardware/drivers/netcx/oid-wdi-set-sae-auth-params)

[NDIS_STATUS_WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED](/windows-hardware/drivers/netcx/ndis-status-wdi-indication-sae-auth-params-needed)

