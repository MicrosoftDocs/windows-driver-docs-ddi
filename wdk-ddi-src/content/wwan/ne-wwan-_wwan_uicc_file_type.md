---
UID: NE:wwan._WWAN_UICC_FILE_TYPE
title: _WWAN_UICC_FILE_TYPE (wwan.h)
description: The WWAN_UICC_FILE_TYPE enumeration specifies the type for a UICC file.
tech.root: netvista
ms.assetid: A404E722-2533-4C98-9F20-C75829E94C7F
ms.date: 04/09/2019
keywords: ["_WWAN_UICC_FILE_TYPE enumeration"]
f1_keywords:
 - "wwan/_WWAN_UICC_FILE_TYPE"
 - "_WWAN_UICC_FILE_TYPE"
ms.keywords: _WWAN_UICC_FILE_TYPE, WWAN_UICC_FILE_TYPE, *PWWAN_UICC_FILE_TYPE, 
req.header: wwan.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: WWAN_UICC_FILE_TYPE, *PWWAN_UICC_FILE_TYPE
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- wwan.h
api_name: 
- _WWAN_UICC_FILE_TYPE
targetos: Windows
ms.custom: 19H1
---

# _WWAN_UICC_FILE_TYPE enumeration

## -description

The **WWAN_UICC_FILE_TYPE** enumeration specifies the type for a UICC file.

## -enum-fields

### -field WwanUiccFileTypeUnknown

File type unknown.

### -field WwanUiccFileTypeWorkingEf

A working EF file.

### -field WwanUiccFileTypeInternalEf

An internal EF file.

### -field WwanUiccFileTypeDfOrAdf

A dedicated file, a directory that is the parent of other nodes. This might be a DF or ADF.

### -field WwanUiccFileTypeMax

The maximum value for this enumeration.

## -remarks

This enumeration is used in the [**WWAN_UICC_FILE_STATUS*](../wwan/ns-wwan-_wwan_uicc_file_status.md) structure.

## -see-also

[MB UICC application and file system access](https://docs.microsoft.com/windows-hardware/drivers/network/mb-uicc-application-and-file-system-access)

[OID_WWAN_UICC_FILE_STATUS](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-uicc-file-status)

[**WWAN_UICC_FILE_STATUS*](../wwan/ns-wwan-_wwan_uicc_file_status.md)
