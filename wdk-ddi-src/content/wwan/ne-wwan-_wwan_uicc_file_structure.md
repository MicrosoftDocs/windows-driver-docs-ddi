---
UID: NE:wwan._WWAN_UICC_FILE_STRUCTURE
title: _WWAN_UICC_FILE_STRUCTURE (wwan.h)
description: The WWAN_UICC_FILE_STRUCTURE enumeration specifies the structure of a UICC file.
tech.root: netvista
ms.assetid: 60C04ECB-B85B-4884-893B-8F6BF2D31B97
ms.date: 04/09/2019
ms.topic: enum
f1_keywords:
 - "wwan/_WWAN_UICC_FILE_STRUCTURE"
ms.keywords: _WWAN_UICC_FILE_STRUCTURE, WWAN_UICC_FILE_STRUCTURE, *PWWAN_UICC_FILE_STRUCTURE, 
req.header: wwan.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: WWAN_UICC_FILE_STRUCTURE, *PWWAN_UICC_FILE_STRUCTURE
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- wwan.h
api_name: 
- _WWAN_UICC_FILE_STRUCTURE
product:
- Windows
targetos: Windows
ms.custom: 19H1
---

# _WWAN_UICC_FILE_STRUCTURE enumeration

## -description

The **WWAN_UICC_FILE_STRUCTURE** enumeration specifies the structure of a UICC file.

## -enum-fields

### -field WwanUiccFileStructureUnknown

An unknown file structure.

### -field WwanUiccFileStructureTransparent

A single record of variable length.

### -field WwanUiccFileStructureCyclic

A cyclic set of records, each of the same length.

### -field WwanUiccFileStructureLinear

A linear set of records, each of the same length.

### -field WwanUiccFileStructureBerTLV

A set of data values accessible by tag.

### -field WwanUiccFileStructureMax

The maximum value for this enumeration.

## -remarks

This enumeration is used in the [**WWAN_UICC_FILE_STATUS*](../wwan/ns-wwan-_wwan_uicc_file_status.md) structure.

## -see-also

[MB UICC application and file system access](https://docs.microsoft.com/windows-hardware/drivers/network/mb-uicc-application-and-file-system-access)

[OID_WWAN_UICC_FILE_STATUS](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-uicc-file-status)

[**WWAN_UICC_FILE_STATUS*](../ndiswwan/ns-ndiswwan-_wwan_uicc_file_status.md)
