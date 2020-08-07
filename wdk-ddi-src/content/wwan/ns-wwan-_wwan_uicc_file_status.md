---
UID: NS:wwan._WWAN_UICC_FILE_STATUS
title: _WWAN_UICC_FILE_STATUS (wwan.h)
description: The WWAN_UICC_FILE_STATUS structure describes the status of a UICC file. 
tech.root: netvista
ms.assetid: A5B1B756-4E1C-42AA-84AA-CEA847D94708
ms.date: 04/09/2019
keywords: ["WWAN_UICC_FILE_STATUS structure"]
f1_keywords:
 - "wwan/_WWAN_UICC_FILE_STATUS"
 - "_WWAN_UICC_FILE_STATUS"
ms.keywords: _WWAN_UICC_FILE_STATUS, WWAN_UICC_FILE_STATUS, *PWWAN_UICC_FILE_STATUS, 
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
req.typenames: WWAN_UICC_FILE_STATUS, *PWWAN_UICC_FILE_STATUS
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- wwan.h
api_name: 
- _WWAN_UICC_FILE_STATUS
targetos: Windows
ms.custom: 19H1
---

# _WWAN_UICC_FILE_STATUS structure

## -description

The **WWAN_UICC_FILE_STATUS** structure describes the status of a UICC file. 

## -struct-fields

### -field Version

The version number of the structure that follows. In Windows 10, version 1903, this version must be set to **1**.
 
### -field StatusWord1

A return parameter specific to the UICC command.

### -field StatusWord2

A return parameter specific to the UICC command.

### -field FileAccessibility

A [**WWAN_UICC_FILE_ACCESSIBILITY**](../wwan/ne-wwan-_wwan_uicc_file_accessibility.md) value that specifies the UICC file accessibility.

### -field FileType

A [**WWAN_UICC_FILE_TYPE**](../wwan/ne-wwan-_wwan_uicc_file_type.md) value that specifies the UICC file type.

### -field FileStructure

A [**WWAN_UICC_FILE_STRUCTURE**](../wwan/ne-wwan-_wwan_uicc_file_structure.md) value that specifies the UICC file structure.

### -field ItemCount

The number of items in the UICC file. For transparent and TLV viles, this is set to **1**.

### -field ItemSize

The size of each item, in bytes. For transparent or TLV files, this is the size of the entire EF. For record-based files, this represents the total number of records.

### -field FileLockStatus

A [**WWAN_PIN_TYPE**](../wwan/ne-wwan-_wwan_pin_type.md) value that specifies the access condition for each operation (READ, UPDATE, ACTIVATE, and DEACTIVATE in that order) on the file.

## -remarks

This structure is used in the [**NDIS_WWAN_UICC_FILE_STATUS**](../ndiswwan/ns-ndiswwan-_ndis_wwan_uicc_file_status.md) structure.

## -see-also

[MB UICC application and file system access](https://docs.microsoft.com/windows-hardware/drivers/network/mb-uicc-application-and-file-system-access)

[OID_WWAN_UICC_FILE_STATUS](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-uicc-file-status)

[**NDIS_WWAN_UICC_FILE_STATUS**](../ndiswwan/ns-ndiswwan-_ndis_wwan_uicc_file_status.md)
