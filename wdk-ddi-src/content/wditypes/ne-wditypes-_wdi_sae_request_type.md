---
UID: NE:wditypes._WDI_SAE_REQUEST_TYPE
title: WDI_SAE_REQUEST_TYPE
description: The WDI_SAE_REQUEST_TYPE enumeration defines the type of Simultaneous Authentication of Equals (SAE) request frame to send to the BSSID.
tech.root: netvista
ms.date: 02/14/2019
keywords: ["WDI_SAE_REQUEST_TYPE enumeration"]
ms.keywords: WDI_SAE_REQUEST_TYPE, WDI_SAE_REQUEST_TYPE,
req.header: wditypes.hpp
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: WDI_SAE_REQUEST_TYPE
targetos: Windows
f1_keywords:
 - _WDI_SAE_REQUEST_TYPE
 - wditypes/_WDI_SAE_REQUEST_TYPE
 - WDI_SAE_REQUEST_TYPE
 - wditypes/WDI_SAE_REQUEST_TYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wditypes.hpp
api_name:
 - WDI_SAE_REQUEST_TYPE
---

# WDI_SAE_REQUEST_TYPE enumeration


## -description

The **WDI_SAE_REQUEST_TYPE** enumeration defines the type of Simultaneous Authentication of Equals (SAE) request frame to send to the BSSID.

## -enum-fields

### -field WDI_SAE_REQUEST_TYPE_COMMIT_REQUEST 

Send a Commit request. SAECommitRequest will be included.

### -field WDI_SAE_REQUEST_TYPE_CONFIRM_REQUEST 

Send a Confirm request. SAEConfirmRequest will be included.

### -field WDI_SAE_REQUEST_TYPE_FAILURE 

Request SAE authentication parameters failed. SAEStatus will be included.

### -field WDI_SAE_REQUEST_TYPE_SUCCESS 

Request SAE authentication parameters succeeded.

## -remarks

This enumeration is a value in the [OID_WDI_SET_SAE_AUTH_PARAMS](/windows-hardware/drivers/network/oid-wdi-set-sae-auth-params) command.

## -see-also

[WPA3-SAE Authentication](/windows-hardware/drivers/network/wpa3-sae-authentication)

[OID_WDI_SET_SAE_AUTH_PARAMS](/windows-hardware/drivers/network/oid-wdi-set-sae-auth-params)
