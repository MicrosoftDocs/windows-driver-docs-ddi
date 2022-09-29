---
UID: NE:wditypes._WDI_SAE_REQUEST_TYPE
title: WDI_SAE_REQUEST_TYPE
description: The WDI_SAE_REQUEST_TYPE enumeration defines the type of Simultaneous Authentication of Equals (SAE) request frame to send to the BSSID.
tech.root: netvista
ms.date: 12/28/2021
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
 - _WDI_SAE_REQUEST_TYPE
 - WDI_SAE_REQUEST_TYPE
---

# WDI_SAE_REQUEST_TYPE enumeration


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The **WDI_SAE_REQUEST_TYPE** enumeration defines the type of Simultaneous Authentication of Equals (SAE) request frame to send to the BSSID.

## -enum-fields

### -field WDI_SAE_REQUEST_TYPE_COMMIT_REQUEST:0 

Send a Commit request. SAECommitRequest will be included.

### -field WDI_SAE_REQUEST_TYPE_CONFIRM_REQUEST:1 

Send a Confirm request. SAEConfirmRequest will be included.

### -field WDI_SAE_REQUEST_TYPE_FAILURE:2 

Request SAE authentication parameters failed. SAEStatus will be included.

### -field WDI_SAE_REQUEST_TYPE_SUCCESS:3 

Request SAE authentication parameters succeeded.

### -field WDI_SAE_REQUEST_TYPE_COMMIT_REQUEST_H2E:4

Send a Commit Request using H2E. When Anti-Clogging token is specified, it will be encoded as Anti-Clogging Element instead of a field.

## -remarks

This enumeration is a value in the [OID_WDI_SET_SAE_AUTH_PARAMS](/windows-hardware/drivers/network/oid-wdi-set-sae-auth-params) command.

## -see-also

[WPA3-SAE Authentication](/windows-hardware/drivers/network/wpa3-sae-authentication)

[OID_WDI_SET_SAE_AUTH_PARAMS](/windows-hardware/drivers/network/oid-wdi-set-sae-auth-params)

