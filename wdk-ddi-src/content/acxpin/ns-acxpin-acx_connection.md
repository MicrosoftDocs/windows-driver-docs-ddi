---
UID: NS:acxpin._ACX_CONNECTION
tech.root: audio
title: ACX_CONNECTION
ms.date: 04/12/2022
targetos: Windows
description: The ACX_CONNECTION structure is used to define a connection between two pins.
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
req.typenames: ACX_CONNECTION, *PACX_CONNECTION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxpin.h
api_name:
 - _ACX_CONNECTION
 - PACX_CONNECTION
 - ACX_CONNECTION
f1_keywords:
 - _ACX_CONNECTION
 - acxpin/_ACX_CONNECTION
 - PACX_CONNECTION
 - acxpin/PACX_CONNECTION
 - ACX_CONNECTION
 - acxpin/ACX_CONNECTION
dev_langs:
 - c++
---

## -description

The **ACX_CONNECTION** structure is used to define a connection between two pins.

## -struct-fields

### -field Size

The size of this **ACX_CONNECTION** structure for verification purposes.

### -field Flags

A combination of [ACX_CONNECTION_FLAGS](ne-acxpin-acx_connection_flags.md) values that indicate how to identify the pins of the *FromObject* and *ToObject*.

### -field FromObject

An **ACXOBJECT** representing the source.

### -field FromPin

The pin associated with the *FromObject*.

### -field FromPin.Object

An **ACXPIN** object used to identify the *FromPin* object.

### -field FromPin.Id

The ID used to identify the *FromPin* object.

### -field ToObject

An **ACXOBJECT** representing the sink.

### -field ToPin

### -field ToPin.Object

An **ACXPIN** object used to identify the *ToPin* object.

### -field ToPin.Id

The ID used to identify the *ToPin* object.

## -remarks

## -see-also

- [acxpin.h header](index.md)

READY2GO

EDITCOMPLETE
