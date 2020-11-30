---
UID: NS:acpitabl._ACPI_PLD_INTERFACE_CLASS_BUFFER
title: _ACPI_PLD_INTERFACE_CLASS_BUFFER structure (acpitabl.h)
description: Describes the ACPI PLD interface class descriptor buffer, revision 1 (Microsoft custom PLD buffer extension, 128-bits).
ms.assetid: f817f194-41c2-4193-a803-768e5914c91a
ms.date: 11/19/2020
keywords: ["ACPI_PLD_INTERFACE_CLASS_BUFFER structure"]
ms.keywords: _ACPI_PLD_INTERFACE_CLASS_BUFFER, ACPI_PLD_INTERFACE_CLASS_BUFFER, *PACPI_PLD_INTERFACE_CLASS_BUFFER,
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
req.typenames: ACPI_PLD_INTERFACE_CLASS_BUFFER, *PACPI_PLD_INTERFACE_CLASS_BUFFER
targetos: Windows
tech.root: acpi
f1_keywords:
 - _ACPI_PLD_INTERFACE_CLASS_BUFFER
 - acpitabl/_ACPI_PLD_INTERFACE_CLASS_BUFFER
 - PACPI_PLD_INTERFACE_CLASS_BUFFER
 - acpitabl/PACPI_PLD_INTERFACE_CLASS_BUFFER
 - ACPI_PLD_INTERFACE_CLASS_BUFFER
 - acpitabl/ACPI_PLD_INTERFACE_CLASS_BUFFER
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acpitabl.h
api_name:
 - _ACPI_PLD_INTERFACE_CLASS_BUFFER
---

# _ACPI_PLD_INTERFACE_CLASS_BUFFER structure

## -description

Describes the ACPI PLD interface class descriptor buffer, revision 1 (Microsoft custom PLD buffer extension, 128-bits).

## -struct-fields

### -field ClassGuid

The ClassGuid field of the ACPI_PLD_INTERFACE_CLASS_BUFFER structure.

## -remarks

The GUID is defined as follows:

```cpp
DEFINE_GUID(ACPI_PLD_INTERFACE_CLASS_BUFFER_GUID,
    0x1facec76, 0x96a8, 0x4d9e, 0x84, 0x6e, 0x3a, 0x6d, 0x68, 0x7c, 0x32, 0xfc);
```

## -see-also
