---
UID: NS:acpitabl._SDEV_SECURE_RESOURCE_ID_ENTRY
title: _SDEV_SECURE_RESOURCE_ID_ENTRY (acpitabl.h)
ms.date: 05/11/2020
ms.topic: language-reference
ms.keywords: _SDEV_SECURE_RESOURCE_ID_ENTRY, SDEV_SECURE_RESOURCE_ID_ENTRY, *PSDEV_SECURE_RESOURCE_ID_ENTRY
description: Defines a resource ID entry for a secure ACPI device for use in a secure device table.
tech.root: acpi
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acpitabl.h
req.include-header: Acpitabl.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: Windows
req.typenames: SDEV_SECURE_RESOURCE_ID_ENTRY, *PSDEV_SECURE_RESOURCE_ID_ENTRY
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- acpitabl.h
api_name:
- _SDEV_SECURE_RESOURCE_ID_ENTRY
- SDEV_SECURE_RESOURCE_ID_ENTRY
f1_keywords:
- acpitabl/_SDEV_SECURE_RESOURCE_ID_ENTRY
- acpitabl/SDEV_SECURE_RESOURCE_ID_ENTRY
dev_langs:
- c++
product:
- Windows
targetos: Windows
---

# _SDEV_SECURE_RESOURCE_ID_ENTRY structure

## -description

The **_SDEV_SECURE_RESOURCE_ID_ENTRY** structure defines a resource ID entry for a secure ACPI device for use in a secure device table.

## -struct-fields

### -field Header

The **SDEV_ENTRY_HEADER** header.

### -field HardwareIdentifierOffset

The hardware identifier offset value.

### -field HardwareIdentifierLength

The hardware identifier length value.

### -field SubsystemIdentifierOffset

The subsystem identifier offset value.

### -field SubsystemIdentifierLength

The subsystem identifier length value.

### -field HardwareRevision

The hardware revision value.

### -field HardwareRevisionPresent

The hardware revision present value.

## -remarks

## -see-also
