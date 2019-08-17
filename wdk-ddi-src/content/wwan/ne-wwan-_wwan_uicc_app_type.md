---
UID: NE:wwan._WWAN_UICC_APP_TYPE
title: _WWAN_UICC_APP_TYPE (wwan.h)
description: The WWAN_UICC_APP_TYPE enumeration specifies the type for a UICC application.
tech.root: netvista
ms.assetid: 32EA323E-E02A-4194-88F3-A18BDA4816AB
ms.date: 04/08/2019
ms.topic: enum
f1_keywords:
 - "wwan/_WWAN_UICC_APP_TYPE"
ms.keywords: _WWAN_UICC_APP_TYPE, WWAN_UICC_APP_TYPE, *PWWAN_UICC_APP_TYPE, 
req.header: wwan.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: WWAN_UICC_APP_TYPE, *PWWAN_UICC_APP_TYPE
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- wwan.h
api_name: 
- _WWAN_UICC_APP_TYPE
product:
- Windows
targetos: Windows
ms.custom: 19H1
---

# _WWAN_UICC_APP_TYPE enumeration

## -description

The **WWAN_UICC_APP_TYPE** enumeration specifies the type for a UICC application.

## -enum-fields

### -field WwanUiccAppTypeUnknown

Unknown type.

### -field WwanUiccAppTypeMf

Legacy SIM directories rooted at the MF.

### -field WwanUiccAppTypeMfSIM

Legacy SIM directories rooted at the DF_GSM.

### -field WwanUiccAppTypeMfRUIM

Legacy SIM directories rooted at the DF_CDMA.

### -field WwanUiccAppTypeUSIM

A USIM application.

### -field WwanUiccAppTypeCSIM

A CSIM application.

### -field WwanUiccAppTypeISIM

An ISIM application.

### -field WwanUiccAppTypeMax

The maximum value for this enumeration.

## -remarks

This enumeration is used in the [**WWAN_UICC_APP_INFO**](../wwan/ns-wwan-_wwan_uicc_app_info.md) structure.

## -see-also

[MB UICC application and file system access](https://docs.microsoft.com/windows-hardware/drivers/network/mb-uicc-application-and-file-system-access)

[OID_WWAN_UICC_APP_LIST](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-uicc-app-list)

[**WWAN_UICC_APP_INFO**](../wwan/ns-wwan-_wwan_uicc_app_info.md)
