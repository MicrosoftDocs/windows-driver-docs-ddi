---
UID: NS:acpitabl._ACPI_PLD_JOINT_BUFFER
title: _ACPI_PLD_JOINT_BUFFER structure (acpitabl.h)
description: Describes the ACPI PLD joint descriptor buffer, revision 1 (Microsoft custom PLD buffer extension, 128-bits).
ms.date: 11/19/2020
keywords: ["ACPI_PLD_JOINT_BUFFER structure"]
ms.keywords: _ACPI_PLD_JOINT_BUFFER, ACPI_PLD_JOINT_BUFFER, *PACPI_PLD_JOINT_BUFFER,
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
req.typenames: ACPI_PLD_JOINT_BUFFER, *PACPI_PLD_JOINT_BUFFER
targetos: Windows
tech.root: acpi
f1_keywords:
 - _ACPI_PLD_JOINT_BUFFER
 - acpitabl/_ACPI_PLD_JOINT_BUFFER
 - PACPI_PLD_JOINT_BUFFER
 - acpitabl/PACPI_PLD_JOINT_BUFFER
 - ACPI_PLD_JOINT_BUFFER
 - acpitabl/ACPI_PLD_JOINT_BUFFER
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acpitabl.h
api_name:
 - _ACPI_PLD_JOINT_BUFFER
---

# _ACPI_PLD_JOINT_BUFFER structure

## -description

Describes the ACPI PLD joint descriptor buffer, revision 1 (Microsoft custom PLD buffer extension, 128-bits).

## -struct-fields

### -field Revision

### -field JointType

### -field SourceEdge

### -field TargetCabinetNumber

### -field TargetPanel

### -field TargetEdge

### -field Reserved1

### -field MovementOrientation

### -field ForwardMovementRange

### -field BackwardMovementRange

### -field HorizontalOffset

### -field VerticalOffset

### -field GapOffset

### -field Rotation

### -field Reserved2

## -remarks

The GUID is defined as follows:

```cpp
DEFINE_GUID(ACPI_PLD_JOINT_BUFFER_GUID,
    0xf01cfc40, 0x3c75, 0x4523, 0x9e, 0x44, 0x21, 0x5c, 0xb1, 0x54, 0xbd, 0xa6);
```

## -see-also
