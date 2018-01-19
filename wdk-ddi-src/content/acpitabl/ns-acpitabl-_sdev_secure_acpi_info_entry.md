---
UID: NS:acpitabl._SDEV_SECURE_ACPI_INFO_ENTRY
title: _SDEV_SECURE_ACPI_INFO_ENTRY
author: windows-driver-content
description: Defines an information entry for a secure ACPI device for use in a secure device table.
old-location: acpi\sdev_secure_acpi_info_entry.htm
old-project: acpi
ms.assetid: A3FDE9B0-DD6E-4FF5-AD9A-7DF7BF276EFA
ms.author: windowsdriverdev
ms.date: 12/31/2017
ms.keywords: _SDEV_SECURE_ACPI_INFO_ENTRY, *PSDEV_SECURE_ACPI_INFO_ENTRY, SDEV_SECURE_ACPI_INFO_ENTRY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: acpitabl.h
req.include-header: Acpitabl.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SDEV_SECURE_ACPI_INFO_ENTRY
req.alt-loc: acpitabl.h
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
req.typenames: *PSDEV_SECURE_ACPI_INFO_ENTRY, SDEV_SECURE_ACPI_INFO_ENTRY
---

# _SDEV_SECURE_ACPI_INFO_ENTRY structure



## -description
Defines an information entry for a secure ACPI device for use in a secure device table.



## -syntax

````
typedef struct _SDEV_SECURE_ACPI_INFO_ENTRY {
  SDEV_ENTRY_HEADER Header;
  USHORT            IdentifierOffset;
  USHORT            IdentifierLength;
  USHORT            VendorInfoOffset;
  USHORT            VendorInfoLength;
} SDEV_SECURE_ACPI_INFO_ENTRY, *PSDEV_SECURE_ACPI_INFO_ENTRY;
````


## -struct-fields

### -field Header

A header. 


### -field IdentifierOffset

An identifier offset value.


### -field IdentifierLength

The length of the identifier.


### -field VendorInfoOffset

A vendor information offset value.


### -field VendorInfoLength

The length of the vendor information. 


## -remarks
