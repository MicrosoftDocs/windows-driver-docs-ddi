---
UID: NE:wditypes._WDI_SAE_STATUS
title: WDI_SAE_STATUS
description: The WDI_SAE_STATUS enumeration defines SAE authentication failure error status codes.
tech.root: netvista
ms.date: 12/28/2021
keywords: ["WDI_SAE_STATUS enumeration"]
ms.keywords: WDI_SAE_STATUS, WDI_SAE_STATUS,
req.header: wditypes.hpp
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: WDI_SAE_STATUS
targetos: Windows
f1_keywords:
 - _WDI_SAE_STATUS
 - wditypes/_WDI_SAE_STATUS
 - WDI_SAE_STATUS
 - wditypes/WDI_SAE_STATUS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wditypes.hpp
api_name:
 - _WDI_SAE_STATUS
 - WDI_SAE_STATUS
---

# WDI_SAE_STATUS enumeration


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The **WDI_SAE_STATUS** enumeration defines SAE authentication failure error status codes. This enumeration is used to provide failure codes from the OS to the miniport driver, or from the driver to the OS.

## -enum-fields

### -field WDI_SAE_STATUS_SUCCESS 

The operation completed successfully.

### -field WDI_SAE_STATUS_FAILURE 

The operation completed with failure.

### -field WDI_SAE_STATUS_RESOURCES 

WDI or the driver encountered a resource allocation error.

### -field WDI_SAE_STATUS_INTERNAL_AUTH_FAILURE 

WDI encountered an internal authentication-related failure.

### -field WDI_SAE_STATUS_INVALID_PEER 

The Commit or Confirm response was received from an AP for which WDI did not provide SAE parameters.

### -field WDI_SAE_STATUS_INITIALIZATION_NO_KEY 

WDI does not have the password for this association request.

### -field WDI_SAE_STATUS_COMMIT_MESSAGE_RECEIVED_IN_NOTHING_STATE 

The Commit message was received in the Nothing state.

### -field WDI_SAE_STATUS_COMMIT_MESSAGE_MALFORMED_AUTH_FRAME 

A bad Commit frame was received.

### -field WDI_SAE_STATUS_COMMIT_MESSAGE_FAILURE_FROM_PEER 

The Commit frame from the peer contained an error code.

### -field WDI_SAE_STATUS_COMMIT_MESSAGE_FINITE_GROUP_NOT_PRESENT 

The Finite group was not present in the Commit frame.

### -field WDI_SAE_STATUS_COMMIT_MESSAGE_UNSUPPORTED_FINITE_GROUP 

The Finite group specified in the Commit frame is not supported.

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

WDI does not handle the BSS transition request.

### -field WDI_SAE_STATUS_CONFIRM_MESSAGE_INTERNAL_COMPUTATION_ERROR 

WDI encountered an internal error.

### -field WDI_SAE_STATUS_CONFIRM_MESSAGE_VERIFICATION_FAILED 

WDI failed to match the Verifier from the Confirm frame.

### -field WDI_SAE_STATUS_CONFIRM_MESSAGE_RESEND_REQUEST 

The driver requests a new set of Confirm frame parameters to resend the Confirm request to the AP.

### -field WDI_SAE_STATUS_INITIALIZATION_H2E_NOT_SUPPORTED

AP requires Hash-To-Element support but the driver doesn't support Hash-To-Element.

### -field WDI_SAE_STATUS_INITIALIZATION_PWD_ID_NOT_SUPPORTED

AP requires Password-Identifier, but no Password-Identifier is available.

### -field WDI_SAE_STATUS_TIMEOUT_WAITING_FOR_COMMIT_REQUEST

The driver timed out waiting for a Commit Request from the OS.

### -field WDI_SAE_STATUS_TIMEOUT_WAITING_FOR_CONFIRM_REQUEST

The driver timed out waiting for a Confirm Request from the OS.

### -field WDI_SAE_STATUS_TIMEOUT_WAITING_FOR_STATUS

The driver timed out waiting for a Status from the OS.

### -field WDI_SAE_STATUS_CONNECTION_CLEANED_UP

Internal handling code.

### -field WDI_SAE_STATUS_CLEAN_UP_CONTEXT

Internal handling code.

## -remarks

This enumeration is a value in both the [OID_WDI_SET_SAE_AUTH_PARAMS](/windows-hardware/drivers/network/oid-wdi-set-sae-auth-params) command and the [NDIS_STATUS_WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED](/windows-hardware/drivers/network/ndis-status-wdi-indication-sae-auth-params-needed) indication.

## -see-also

[WPA3-SAE Authentication](/windows-hardware/drivers/network/wpa3-sae-authentication)

[OID_WDI_SET_SAE_AUTH_PARAMS](/windows-hardware/drivers/network/oid-wdi-set-sae-auth-params)

[NDIS_STATUS_WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED](/windows-hardware/drivers/network/ndis-status-wdi-indication-sae-auth-params-needed)

