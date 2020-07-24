---
UID: NE:wditypes._WDI_SAE_INDICATION_TYPE
title: WDI_SAE_INDICATION_TYPE
author: windows-driver-content
description: The WDI_SAE_INDICATION_TYPE enumeration defines the type of information needed to continue SAE authentication with the BSSID, or notification that authentication cannot continue.
tech.root: netvista
ms.assetid: 685c8f66-5b3a-4bb5-8579-18197e661e73
ms.author: windowsdriverdev
ms.date: 02/14/2019
keywords: ["WDI_SAE_INDICATION_TYPE enumeration"]
f1_keywords:
 - "wditypes/WDI_SAE_INDICATION_TYPE"
 - "WDI_SAE_INDICATION_TYPE"
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
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - wditypes.hpp
api_name: 
 - WDI_SAE_INDICATION_TYPE
targetos: Windows
---

# WDI_SAE_INDICATION_TYPE enumeration

## -description

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

This enumeration is a value in the [NDIS_STATUS_WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wdi-indication-sae-auth-params-needed) indication.

## -see-also

[WPA3-SAE Authentication](https://docs.microsoft.com/windows-hardware/drivers/network/wpa3-sae-authentication)

[NDIS_STATUS_WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wdi-indication-sae-auth-params-needed)
