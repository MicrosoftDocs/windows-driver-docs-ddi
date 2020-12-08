---
UID: NS:wwan._WWAN_PIN_APP
title: _WWAN_PIN_APP (wwan.h)
description: The WWAN_PIN_APP structure specifies the target application ID for a UICC application whose PIN is being queried.
tech.root: netvista
ms.date: 04/10/2019
keywords: ["WWAN_PIN_APP structure"]
ms.keywords: _WWAN_PIN_APP, WWAN_PIN_APP, *PWWAN_PIN_APP,
req.header: wwan.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: WWAN_PIN_APP, *PWWAN_PIN_APP
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _WWAN_PIN_APP
 - wwan/_WWAN_PIN_APP
 - PWWAN_PIN_APP
 - wwan/PWWAN_PIN_APP
 - WWAN_PIN_APP
 - wwan/WWAN_PIN_APP
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_PIN_APP
---

# _WWAN_PIN_APP structure


## -description

The **WWAN_PIN_APP** structure specifies the target application ID for a UICC application whose PIN is being queried.

## -struct-fields

### -field Version

The version number of the structure that follows. In Windows 10, version 1903, this version must be set to **1**.

### -field AppIdLength

The size of the application ID, in bytes, as defined in Section 8.3 of the [ETSI TS 102 221 technical specification](https://go.microsoft.com/fwlink/p/?linkid=864594). For 2G cards, this field must be set to zero (0).

### -field AppId

The application ID. Only the first **AppIdLength** bytes are meaningful. If the application ID is longer than **WWAN_UICC_APP_ID_MAX_LEN** bytes, then **AppIdLength** specifies the actual length but only the first **WWAN_UICC_APP_ID_MAX_LEN** bytes are in this field.

## -remarks

This structure is used in the [**NDIS_WWAN_PIN_APP**](../ndiswwan/ns-ndiswwan-_ndis_wwan_pin_app.md) structure.

## -see-also

[MB UICC application and file system access](/windows-hardware/drivers/network/mb-uicc-application-and-file-system-access)

[OID_WWAN_PIN_EX2](/windows-hardware/drivers/network/oid-wwan-pin-ex2)

[**NDIS_WWAN_PIN_APP**](../ndiswwan/ns-ndiswwan-_ndis_wwan_pin_app.md)
