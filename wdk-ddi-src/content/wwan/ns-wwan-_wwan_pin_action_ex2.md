---
UID: NS:wwan._WWAN_PIN_ACTION_EX2
title: _WWAN_PIN_ACTION_EX2 (wwan.h)
description: The WWAN_PIN_ACTION_EX2 structure specifies the PIN action to take for a UICC application.
tech.root: netvista
ms.date: 04/10/2019
keywords: ["WWAN_PIN_ACTION_EX2 structure"]
ms.keywords: _WWAN_PIN_ACTION_EX2, WWAN_PIN_ACTION_EX2, *PWWAN_PIN_ACTION_EX2,
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
req.typenames: WWAN_PIN_ACTION_EX2, *PWWAN_PIN_ACTION_EX2
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _WWAN_PIN_ACTION_EX2
 - wwan/_WWAN_PIN_ACTION_EX2
 - PWWAN_PIN_ACTION_EX2
 - wwan/PWWAN_PIN_ACTION_EX2
 - WWAN_PIN_ACTION_EX2
 - wwan/WWAN_PIN_ACTION_EX2
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_PIN_ACTION_EX2
 - PWWAN_PIN_ACTION_EX2
 - WWAN_PIN_ACTION_EX2
---

# _WWAN_PIN_ACTION_EX2 structure


## -description

The **WWAN_PIN_ACTION_EX2** structure specifies the PIN action to take for a UICC application.

## -struct-fields

### -field PinType

A [**WWAN_PIN_TYPE**](../wwan/ne-wwan-_wwan_pin_type.md) value that specifies the PIN type for the application.

### -field PinOperation

A [**WWAN_PIN_OPERATION**](../wwan/ne-wwan-_wwan_pin_operation.md) value that specifies the operation to perform on the PIN.

### -field Pin

A string representing the PIN value with which to perform the action, or the PIN value required to enable or disable PIN settings. This field applies for all values of **PinOperation**.

### -field NewPin

A string representing the new PIN value to set when **PinOperation** is **WwanPinOperationChange** or **WwanPinOperationEnter**, for a **PinType** of **WwanPinTypePuk1** or **WwanPinTypePuk2**.

### -field AppIdLength

The size of the application ID, in bytes, as defined in Section 8.3 of the [ETSI TS 102 221 technical specification](https://go.microsoft.com/fwlink/p/?linkid=864594). For 2G cards, this field must be set to zero (0).

### -field AppId

The application ID. Only the first **AppIdLength** bytes are meaningful. If the application ID is longer than **WWAN_UICC_APP_ID_MAX_LEN** bytes, then **AppIdLength** specifies the actual length but only the first **WWAN_UICC_APP_ID_MAX_LEN** bytes are in this field.

## -remarks

This structure is used in the [**NDIS_WWAN_SET_PIN_EX2**](../ndiswwan/ns-ndiswwan-_ndis_wwan_set_pin_ex2.md) structure.

## -see-also

[MB UICC application and file system access](/windows-hardware/drivers/network/mb-uicc-application-and-file-system-access)

[OID_WWAN_PIN_EX2](/windows-hardware/drivers/network/oid-wwan-pin-ex2)

[**NDIS_WWAN_SET_PIN_EX2**](../ndiswwan/ns-ndiswwan-_ndis_wwan_set_pin_ex2.md)

