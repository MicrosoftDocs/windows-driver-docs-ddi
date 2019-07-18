---
UID: NE:wwan._WWAN_UICC_FILE_ACCESSIBILITY
title: _WWAN_UICC_FILE_ACCESSIBILITY (wwan.h)
description: The WWAN_UICC_FILE_ACCESSIBILITY enumeration specifies accessibility for a UICC file.
tech.root: netvista
ms.assetid: 7C20FC15-7AF0-40B4-8261-C30458885187
ms.date: 04/09/2019
ms.topic: enum
f1_keywords:
 - "wwan/_WWAN_UICC_FILE_ACCESSIBILITY"
ms.keywords: _WWAN_UICC_FILE_ACCESSIBILITY, WWAN_UICC_FILE_ACCESSIBILITY, *PWWAN_UICC_FILE_ACCESSIBILITY, 
req.header: wwan.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: WWAN_UICC_FILE_ACCESSIBILITY, *PWWAN_UICC_FILE_ACCESSIBILITY
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- wwan.h
api_name: 
- _WWAN_UICC_FILE_ACCESSIBILITY
product:
- Windows
targetos: Windows
ms.custom: 19H1
---

# _WWAN_UICC_FILE_ACCESSIBILITY enumeration

## -description

The **WWAN_UICC_FILE_ACCESSIBILITY** enumeration specifies accessibility for a UICC file.

## -enum-fields

### -field WwanUiccFileAccessibilityUnknown

File shareability unknown.

### -field WwanUiccFileAccessibilityNotShareable

A shareable file.

### -field WwanUiccFileAccessibilityShareable

Not a shareable file.

### -field WwanUiccFileAccessibilityMax

The maximum value for this enumeration.

## -remarks

This enumeration is used in the [**WWAN_UICC_FILE_STATUS*](../wwan/ns-wwan-_wwan_uicc_file_status.md) structure.

## -see-also

[MB UICC application and file system access](https://docs.microsoft.com/windows-hardware/drivers/network/mb-uicc-application-and-file-system-access)

[OID_WWAN_UICC_FILE_STATUS](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-uicc-file-status)

[**WWAN_UICC_FILE_STATUS*](../ndiswwan/ns-ndiswwan-_wwan_uicc_file_status.md)
