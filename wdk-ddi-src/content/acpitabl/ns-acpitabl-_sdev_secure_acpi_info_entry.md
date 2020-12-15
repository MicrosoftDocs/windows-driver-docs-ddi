---
UID: NS:acpitabl._SDEV_SECURE_ACPI_INFO_ENTRY
title: _SDEV_SECURE_ACPI_INFO_ENTRY (acpitabl.h)
description: Defines an information entry for a secure ACPI device for use in a secure device table.
old-location: acpi\sdev_secure_acpi_info_entry.htm
tech.root: acpi
ms.date: 08/14/2020
keywords: ["SDEV_SECURE_ACPI_INFO_ENTRY structure"]
ms.keywords: "*PSDEV_SECURE_ACPI_INFO_ENTRY, PSDEV_SECURE_ACPI_INFO_ENTRY, PSDEV_SECURE_ACPI_INFO_ENTRY structure pointer [ACPI Devices], SDEV_SECURE_ACPI_INFO_ENTRY, SDEV_SECURE_ACPI_INFO_ENTRY structure [ACPI Devices], _SDEV_SECURE_ACPI_INFO_ENTRY, acpi.sdev_secure_acpi_info_entry, acpitabl/PSDEV_SECURE_ACPI_INFO_ENTRY, acpitabl/SDEV_SECURE_ACPI_INFO_ENTRY"
req.header: acpitabl.h
req.include-header: Acpitabl.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: SDEV_SECURE_ACPI_INFO_ENTRY, *PSDEV_SECURE_ACPI_INFO_ENTRY
f1_keywords:
 - _SDEV_SECURE_ACPI_INFO_ENTRY
 - acpitabl/_SDEV_SECURE_ACPI_INFO_ENTRY
 - PSDEV_SECURE_ACPI_INFO_ENTRY
 - acpitabl/PSDEV_SECURE_ACPI_INFO_ENTRY
 - SDEV_SECURE_ACPI_INFO_ENTRY
 - acpitabl/SDEV_SECURE_ACPI_INFO_ENTRY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - acpitabl.h
api_name:
 - _SDEV_SECURE_ACPI_INFO_ENTRY
 - SDEV_SECURE_ACPI_INFO_ENTRY
---

# _SDEV_SECURE_ACPI_INFO_ENTRY structure


## -description

The **_SDEV_SECURE_ACPI_INFO_ENTRY** structure defines an information entry for a secure ACPI device for use in a secure device table.

## -struct-fields

### -field Header

The **SDEV_ENTRY_HEADER** header.

### -field IdentifierOffset

The identifier offset value.

### -field IdentifierLength

The length of the identifier.

### -field VendorInfoOffset

The vendor information offset value.

### -field VendorInfoLength

The length of the vendor information.

### -field SecureResourcesOffset

The secure resources offset value.

### -field SecureResourcesLength

The length of the secure resources information.

## -remarks

## -see-also

