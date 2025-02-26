---
UID: NF:dbgmodel.IDebugHostMemory3.CanonicalizeLocation
tech.root: debugger
title: IDebugHostMemory3::CanonicalizeLocation
ms.date: 02/24/2025
targetos: Windows
description: The CanonicalizeLocation method transforms a given location to its "canonical representation", which is a chosen standard form.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dbgmodel.h
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
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostMemory3::CanonicalizeLocation
f1_keywords:
 - IDebugHostMemory3::CanonicalizeLocation
 - dbgmodel/IDebugHostMemory3::CanonicalizeLocation
dev_langs:
 - c++
helpviewer_keywords:
 - CanonicalizeLocation
---

## -description

CanonicalizeLocation is a method that transforms a given location to its "canonical representation", which is a chosen standard form. It can handle different types of locations, for example, virtual memory and register, that can be represented in several ways.

A classic example where this function might be helpful involve the Debugging Tools for Windows (dbgeng) that historically sign extends 32-bit addresses to 64-bits, creating difficulties in representing and distinguishing certain address regions in high address aware 32-bit processes.

Please note that comparing locations or addresses gotten from components which report sign extended addresses against zero extended ones could result in unforeseen failures. You can evade such mishaps by calling CanonicalizeLocation() beforehand. Keep in mind that this method doesn't transform the type of a location. To transform the type, you should call LinearizeLocation().

## -parameters

### -param context

The current context.

### -param location

The location you want to canonicalize.

### -param pCanonicalizedLocation

Pointer to where the canonicalized location will be stored.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

Although this method changes a location's representation to its canonical form, it doesN't alter the actual type of the location. Use the [LinearizeLocation() method](nf-dbgmodel-idebughostmemory3-linearizelocation.md) to perform such type transformation.

## -see-also

[IDebugHostMemory3 interface](nn-dbgmodel-idebughostmemory3.md)