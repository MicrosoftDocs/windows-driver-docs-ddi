---
UID: NF:acxpin.AcxPinGetType
tech.root: audio
title: AcxPinGetType
ms.date: 04/11/2022
targetos: Windows
description: The AcxPinGetType function returns the type of the specified pin.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxpin.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - acxpin.h
api_name:
 - AcxPinGetType
f1_keywords:
 - AcxPinGetType
 - acxpin/AcxPinGetType
dev_langs:
 - c++
---

## -description

The **AcxPinGetType** function returns the type of the specified pin.

## -parameters

### -param AcxPin [in]

The pin for which to get the type.

## -returns

Returns a value from the [ACX_PIN_TYPE](ne-acxpin-acx_pin_type.md) enum.

## -remarks

The return value indicates if the pin is a source, a sink, or some other type.

## -see-also

- [ACX_PIN_TYPE](ne-acxpin-acx_pin_type.md)
- [acxpin.h header](index.md)


