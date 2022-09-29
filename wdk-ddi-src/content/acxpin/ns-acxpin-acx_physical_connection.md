---
UID: NS:acxpin._ACX_PHYSICAL_CONNECTION
tech.root: audio
title: ACX_PHYSICAL_CONNECTION
ms.date: 04/12/2022
targetos: Windows
description: The ACX_PHYSICAL_CONNECTION structure describes a physical audio connection between two ACXCIRCUIT objects.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acxpin.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACX_PHYSICAL_CONNECTION, *PACX_PHYSICAL_CONNECTION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxpin.h
api_name:
 - _ACX_PHYSICAL_CONNECTION
 - PACX_PHYSICAL_CONNECTION
 - ACX_PHYSICAL_CONNECTION
f1_keywords:
 - _ACX_PHYSICAL_CONNECTION
 - acxpin/_ACX_PHYSICAL_CONNECTION
 - PACX_PHYSICAL_CONNECTION
 - acxpin/PACX_PHYSICAL_CONNECTION
 - ACX_PHYSICAL_CONNECTION
 - acxpin/ACX_PHYSICAL_CONNECTION
dev_langs:
 - c++
---

## -description

The **ACX_PHYSICAL_CONNECTION** structure describes a physical audio connection between two ACXCIRCUIT objects.

## -struct-fields

### -field Size

The size of all of the data in the **ACX_PHYSICAL_CONNECTION** structure in bytes.

### -field Flags

A value from the [ACX_PHYSICAL_CONNECTION_FLAGS](ne-acxpin-acx_physical_connection_flags.md) enum that specifies the type of physical connection.

### -field FromPin

A union that identifies the from pin of the physical connection.

### -field FromPin.Object

An **ACXPIN** object used to identify the *FromPin*.

### -field FromPin.Id

The ID used to identify the *FromPin*.

### -field TargetName

A string containing the name of the target pin.

### -field TargetPinId

The ID of the target pin.

## -remarks

## -see-also

- [ACX_PHYSICAL_CONNECTION_FLAGS](ne-acxpin-acx_physical_connection_flags.md)
- [acxpin.h header](index.md)


