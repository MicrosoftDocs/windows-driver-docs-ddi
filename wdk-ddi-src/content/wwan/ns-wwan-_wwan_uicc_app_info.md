---
UID: NS:wwan._WWAN_UICC_APP_INFO
title: _WWAN_UICC_APP_INFO (wwan.h)
description: The WWAN_UICC_APP_INFO structure describes information about a UICC application.
tech.root: netvista
ms.assetid: 1F3B41B3-0781-42A1-9ADD-1F1F6BBDC4E6
ms.date: 04/08/2019
f1_keywords:
 - "wwan/_WWAN_UICC_APP_INFO"
ms.keywords: _WWAN_UICC_APP_INFO, WWAN_UICC_APP_INFO, *PWWAN_UICC_APP_INFO, 
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
req.typenames: WWAN_UICC_APP_INFO, *PWWAN_UICC_APP_INFO
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- wwan.h
api_name: 
- _WWAN_UICC_APP_INFO
product:
- Windows
targetos: Windows
ms.custom: 19H1
---

# _WWAN_UICC_APP_INFO structure

## -description

The **WWAN_UICC_APP_INFO** structure describes information about a UICC application.

## -struct-fields

### -field AppType

A [**WWAN_UICC_APP_TYPE**](../wwan/ne-wwan-_wwan_uicc_app_type.md) value that specifies the type of the UICC application.
 
### -field AppIdSize

The size of the application ID in bytes, as defined in Section 8.3 of the [ETSI TS 102 221 technical specification](https://go.microsoft.com/fwlink/p/?linkid=864594). This field is set to zero (0) for the **WwanUiccAppTypeMf**, **WwanUiccAppTypeMfSIM**, or **WwanUiccAppTypeMfRUIM** app types.
 
### -field AppId

The application ID. Only the first **AppIdSize** bytes are meaningful. If the application ID is longer than **WWAN_UICC_APP_ID_MAX_LEN** bytes, then **AppIdSize** specifies the actual length but only the first **WWAN_UICC_APP_ID_MAX_LEN** bytes are in this field. This field is valid only when **AppType** is not **WwanUiccAppTypeMf**, **WwanUiccAppTypeMfSIM**, or **WwanUiccAppTypeMfRUIM**.
 
### -field AppNameLength

The length, in characters, of the application name.

### -field AppName

A UTF-8 string specifying the name of the application. The length of this field is specified by **AppNameLength**. If the length is greater than or equal to **WWAN_UICC_APP_NAME_MAX_LEN** bytes, this field contains the first **WWAN_UICC_APP_NAME_MAX_LEN - 1** bytes of the name. The string is always null-terminated.

### -field NumPins

The number of application PIN references. In other words, the number of elements of **PinRef** that are valid. Applications on a virtual R-UIM have no PIN references.

### -field PinRef

A byte array specifying the application PIN references for this application (keys for PIN1 and possibly UPIN), as defined in Section 9.4.2 of the [ETSI TS 102 221 technical specification](https://go.microsoft.com/fwlink/p/?linkid=864594). In the case of a single-verification card, or an MBB driver and/or modem that does not support different application keys for different applications, this field must be **0x01**.

## -remarks

This structure is used in the [**WWAN_UICC_APP_LIST**](../wwan/ns-wwan-_wwan_uicc_app_list.md) structure.

The following constants are defined in the Wwan.h header for this structure.

`#define WWAN_UICC_APP_ID_MAX_LEN 32`  
`#define WWAN_UICC_APP_NAME_MAX_LEN 256`  
`#define WWAN_UICC_PINREF_MAX 8`  

## -see-also

[MB UICC application and file system access](https://docs.microsoft.com/windows-hardware/drivers/network/mb-uicc-application-and-file-system-access)

[OID_WWAN_UICC_APP_LIST](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-uicc-app-list)

[**WWAN_UICC_APP_LIST**](../wwan/ns-wwan-_wwan_uicc_app_list.md)

[**WWAN_UICC_APP_TYPE**](../wwan/ne-wwan-_wwan_uicc_app_type.md)
