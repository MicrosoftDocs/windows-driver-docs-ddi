---
UID: NS:ntddk._WHEA_ACPI_HEADER
tech.root: kernel
title: WHEA_ACPI_HEADER (ntddk.h)
ms.date: 03/28/2022
targetos: Windows
description: This topic describes the WHEA_ACPI_HEADER structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddk.h
req.include-header: Ntddk.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: WHEA_ACPI_HEADER, *PWHEA_ACPI_HEADER
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _WHEA_ACPI_HEADER
 - PWHEA_ACPI_HEADER
 - WHEA_ACPI_HEADER
f1_keywords:
 - _WHEA_ACPI_HEADER
 - ntddk/_WHEA_ACPI_HEADER
 - PWHEA_ACPI_HEADER
 - ntddk/PWHEA_ACPI_HEADER
 - WHEA_ACPI_HEADER
 - ntddk/WHEA_ACPI_HEADER
dev_langs:
 - c++
helpviewer_keywords:
 - _WHEA_ACPI_HEADER
---

## -description

This topic describes the **WHEA_ACPI_HEADER** structure.

## -struct-fields

### -field Signature

Defines the **UINT32** member **Signature**

### -field Length

Defines the **UINT32** member **Length**

### -field Revision

Defines the **UINT8** member **Revision**

### -field Checksum

Defines the **UINT8** member **Checksum**

### -field OemId

Defines the **UINT8** member **OemId**

### -field OemTableId

Defines the **UINT64** member **OemTableId**

### -field OemRevision

Defines the **UINT32** member **OemRevision**

### -field CreatorId

Defines the **UINT32** member **CreatorId**

### -field CreatorRevision

Defines the **UINT32** member **CreatorRevision**

## -remarks

## -see-also
