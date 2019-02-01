---
UID: NS:acpitabl._ACPI_PLD_INTERFACE_INSTANCE_UNICODE_BUFFER
title: _ACPI_PLD_INTERFACE_INSTANCE_UNICODE_BUFFER structure (acpitabl.h)
description: Describes the ACPI PLD interface instance Unicode descriptor buffer, revision 1 (Microsoft custom PLD buffer extension, 128-bits).
ms.assetid: c3ded0b4-c497-4b7c-bc88-fec4cbdf8aef
ms.date: 10/02/2018
ms.topic: struct
ms.keywords: _ACPI_PLD_INTERFACE_INSTANCE_UNICODE_BUFFER, ACPI_PLD_INTERFACE_INSTANCE_UNICODE_BUFFER, *PACPI_PLD_INTERFACE_INSTANCE_UNICODE_BUFFER, 
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
req.typenames: ACPI_PLD_INTERFACE_INSTANCE_UNICODE_BUFFER, *PACPI_PLD_INTERFACE_INSTANCE_UNICODE_BUFFER
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	acpitabl.h
api_name: 
-	_ACPI_PLD_INTERFACE_INSTANCE_UNICODE_BUFFER
product:
-	Windows
targetos: Windows
---

# _ACPI_PLD_INTERFACE_INSTANCE_UNICODE_BUFFER structure

## -description

Describes the ACPI PLD interface instance Unicode descriptor buffer, revision 1 (Microsoft custom PLD buffer extension, 128-bits).

## -struct-fields

### -field ReferenceString
 
The ReferenceString field of the ACPI_PLD_INTERFACE_INSTANCE_UNICODE_BUFFER structure.

## -remarks

The GUID is defined as follows:

```C++
DEFINE_GUID(ACPI_PLD_INTERFACE_INSTANCE_UNICODE_BUFFER_GUID,
    0x1face3f6, 0x1a60, 0x4686, 0x98, 0x33, 0xec, 0x84, 0x02, 0xd4, 0x3b, 0x04);
```

## -see-also
