---
UID: NE:wditypes._WDI_SAE_INDICATION_TYPE
title: WDI_SAE_INDICATION_TYPE
description: The WDI_SAE_INDICATION_TYPE enumeration defines the type of information needed to continue SAE authentication with the BSSID, or notification that authentication cannot continue.
tech.root: netvista
ms.date: 02/14/2019
keywords: ["WDI_SAE_INDICATION_TYPE enumeration"]
ms.keywords: WDI_SAE_INDICATION_TYPE, WDI_SAE_INDICATION_TYPE,
req.header: wditypes.hpp
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: WDI_SAE_INDICATION_TYPE
targetos: Windows
f1_keywords:
 - _WDI_SAE_INDICATION_TYPE
 - wditypes/_WDI_SAE_INDICATION_TYPE
 - WDI_SAE_INDICATION_TYPE
 - wditypes/WDI_SAE_INDICATION_TYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wditypes.hpp
api_name:
 - _WDI_SAE_INDICATION_TYPE
 - WDI_SAE_INDICATION_TYPE
---

# WDI_SAE_INDICATION_TYPE enumeration


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The **WDI_SAE_INDICATION_TYPE** enumeration defines the type of information needed to continue SAE authentication with the BSSID, or notification that authentication cannot continue.

## -enum-fields

### -field WDI_SAE_INDICATION_TYPE_COMMIT_REQUEST_PARAMS_NEEDED 

The initial request for parameters to send a Commit request.

### -field WDI_SAE_INDICATION_TYPE_COMMIT_RESPONSE 

Commit response received. The Commit response must be included in the indication.

### -field WDI_SAE_INDICATION_TYPE_CONFIRM_RESPONSE 

Confirm response received. The Confirm response must be included in the indication.

### -field WDI_SAE_INDICATION_TYPE_ERROR 

SAE authentication failed with this BSSID. The SAE status must be included in the indication.

### -field WDI_SAE_INDICATION_TYPE_CONFIRM_REQUEST_RESEND_REQUEST 

Resending the Confirm request to the AP.

## -remarks

This enumeration is a value in the [NDIS_STATUS_WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED](/windows-hardware/drivers/network/ndis-status-wdi-indication-sae-auth-params-needed) indication.

## -see-also

[WPA3-SAE Authentication](/windows-hardware/drivers/network/wpa3-sae-authentication)

[NDIS_STATUS_WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED](/windows-hardware/drivers/network/ndis-status-wdi-indication-sae-auth-params-needed)

