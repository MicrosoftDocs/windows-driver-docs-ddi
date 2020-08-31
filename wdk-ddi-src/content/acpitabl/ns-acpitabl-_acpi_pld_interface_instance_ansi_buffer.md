---
UID: NS:acpitabl._ACPI_PLD_INTERFACE_INSTANCE_ANSI_BUFFER
title: _ACPI_PLD_INTERFACE_INSTANCE_ANSI_BUFFER structure (acpitabl.h)
description: Describes the ACPI PLD interface instance ANSI descriptor buffers, revision 1 (Microsoft custom PLD buffer extension, 128-bits).
ms.assetid: 07cfe6a5-2680-4d04-8628-701e5a1af0dd
ms.date: 08/13/2020
keywords: ["ACPI_PLD_INTERFACE_INSTANCE_ANSI_BUFFER structure"]
ms.keywords: _ACPI_PLD_INTERFACE_INSTANCE_ANSI_BUFFER, ACPI_PLD_INTERFACE_INSTANCE_ANSI_BUFFER, *PACPI_PLD_INTERFACE_INSTANCE_ANSI_BUFFER,
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
req.typenames: ACPI_PLD_INTERFACE_INSTANCE_ANSI_BUFFER, *PACPI_PLD_INTERFACE_INSTANCE_ANSI_BUFFER
targetos: Windows
f1_keywords:
 - _ACPI_PLD_INTERFACE_INSTANCE_ANSI_BUFFER
 - acpitabl/_ACPI_PLD_INTERFACE_INSTANCE_ANSI_BUFFER
 - PACPI_PLD_INTERFACE_INSTANCE_ANSI_BUFFER
 - acpitabl/PACPI_PLD_INTERFACE_INSTANCE_ANSI_BUFFER
 - ACPI_PLD_INTERFACE_INSTANCE_ANSI_BUFFER
 - acpitabl/ACPI_PLD_INTERFACE_INSTANCE_ANSI_BUFFER
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acpitabl.h
api_name:
 - _ACPI_PLD_INTERFACE_INSTANCE_ANSI_BUFFER
---

# _ACPI_PLD_INTERFACE_INSTANCE_ANSI_BUFFER structure


## -description

Describes the ACPI PLD interface instance ANSI descriptor buffers, revision 1 (Microsoft custom PLD buffer extension, 128-bits).

## -struct-fields

### -field ReferenceString

The ReferenceString field of the ACPI_PLD_INTERFACE_INSTANCE_ANSI_BUFFER structure.

## -remarks

The GUID is defined as follows:

```cpp
DEFINE_GUID(ACPI_PLD_INTERFACE_INSTANCE_ANSI_BUFFER_GUID,
    0x1facea4b, 0xda66, 0x484c, 0xba, 0x5b, 0x51, 0x27, 0xe0, 0x5f, 0x95, 0xb2);
```

## -see-also

