---
UID: NS:acpitabl._ACPI_PLD_INTERFACE_INSTANCE_GUID_BUFFER
title: _ACPI_PLD_INTERFACE_INSTANCE_GUID_BUFFER structure (acpitabl.h)
description: Describes the ACPI PLD interface instance GUID descriptor buffer, revision 1 (Microsoft custom PLD buffer extension, 128-bits).
ms.assetid: 2a4ad06c-2d79-49e0-b830-b6956e9c55c8
ms.date: 10/02/2018
keywords: ["_ACPI_PLD_INTERFACE_INSTANCE_GUID_BUFFER structure"]
f1_keywords:
 - "acpitabl/_ACPI_PLD_INTERFACE_INSTANCE_GUID_BUFFER"
 - "_ACPI_PLD_INTERFACE_INSTANCE_GUID_BUFFER"
ms.keywords: _ACPI_PLD_INTERFACE_INSTANCE_GUID_BUFFER, ACPI_PLD_INTERFACE_INSTANCE_GUID_BUFFER, *PACPI_PLD_INTERFACE_INSTANCE_GUID_BUFFER, 
req.header: acpitabl.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: ACPI_PLD_INTERFACE_INSTANCE_GUID_BUFFER, *PACPI_PLD_INTERFACE_INSTANCE_GUID_BUFFER
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- acpitabl.h
api_name: 
- _ACPI_PLD_INTERFACE_INSTANCE_GUID_BUFFER
targetos: Windows
---

# _ACPI_PLD_INTERFACE_INSTANCE_GUID_BUFFER structure

## -description

Describes the ACPI PLD interface instance GUID descriptor buffer, revision 1 (Microsoft custom PLD buffer extension, 128-bits).

## -struct-fields

### -field ReferenceGuid
 
The ReferenceString field of the ACPI_PLD_INTERFACE_INSTANCE_GUID_BUFFER structure.

## -remarks

The GUID is defined as follows:

```C++
DEFINE_GUID(ACPI_PLD_INTERFACE_INSTANCE_GUID_BUFFER_GUID,
    0x1face9db, 0x2530, 0x4248, 0x8e, 0xe3, 0x51, 0x05, 0x3a, 0xef, 0x47, 0xc2);
```

## -see-also
