---
UID: NE:dot11wificxtypes._WDI_SAE_INDICATION_TYPE
tech.root: netvista
title: WDI_SAE_INDICATION_TYPE (dot11wificxtypes.h)
ms.date: 09/15/2021
targetos: Windows
description: The WDI_SAE_INDICATION_TYPE enum defines the type of information needed to continue SAE authentication with the BSSID, or notification that authentication cannot continue.
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
 - _WDI_SAE_INDICATION_TYPE
 - WDI_SAE_INDICATION_TYPE
f1_keywords:
 - _WDI_SAE_INDICATION_TYPE
 - dot11wificxtypes/_WDI_SAE_INDICATION_TYPE
 - WDI_SAE_INDICATION_TYPE
 - dot11wificxtypes/WDI_SAE_INDICATION_TYPE
dev_langs:
 - c++
---

## -description

> [!IMPORTANT]
> This topic is part of the [WiFiCx driver model](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx.md). WiFiCx is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features. The previous Wi-Fi driver model [WDI](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide.md) is in maintenance mode and will only receive high priority fixes.

The **WDI_SAE_INDICATION_TYPE** enumeration defines the type of information needed to continue SAE authentication with the BSSID, or notification that authentication cannot continue.

## -enum-fields

### -field WDI_SAE_INDICATION_TYPE_COMMIT_REQUEST_PARAMS_NEEDED:0 

The initial request for parameters to send a Commit request.

### -field WDI_SAE_INDICATION_TYPE_COMMIT_RESPONSE :1

Commit response received. The Commit response must be included in the indication.

### -field WDI_SAE_INDICATION_TYPE_CONFIRM_RESPONSE:2

Confirm response received. The Confirm response must be included in the indication.

### -field WDI_SAE_INDICATION_TYPE_ERROR:3

SAE authentication failed with this BSSID. The SAE status must be included in the indication.

### -field WDI_SAE_INDICATION_TYPE_CONFIRM_REQUEST_RESEND_REQUEST:4

Resending the Confirm request to the AP.

## -remarks

This enumeration is a value in the [NDIS_STATUS_WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED](/windows-hardware/drivers/netcx/ndis-status-wdi-indication-sae-auth-params-needed) indication.

## -see-also

[WPA3-SAE Authentication](/windows-hardware/drivers/netcx/wpa3-sae-authentication)

[NDIS_STATUS_WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED](/windows-hardware/drivers/netcx/ndis-status-wdi-indication-sae-auth-params-needed)
