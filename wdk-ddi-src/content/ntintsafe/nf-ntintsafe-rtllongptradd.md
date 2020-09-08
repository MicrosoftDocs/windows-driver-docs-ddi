---
UID: NF:ntintsafe.RtlLongPtrAdd
title: RtlLongPtrAdd function (ntintsafe.h)
description: Adds two values of type LONG_PTR.
old-location: kernel\rtllongptradd.htm
tech.root: kernel
ms.assetid: D0036070-A23D-4525-AE80-E10B20330F97
ms.date: 04/30/2018
keywords: ["RtlLongPtrAdd function"]
ms.keywords: RtlLongPtrAdd, RtlLongPtrAdd function [Kernel-Mode Driver Architecture], kernel.rtllongptradd, ntintsafe/RtlLongPtrAdd
req.header: ntintsafe.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlLongPtrAdd
 - ntintsafe/RtlLongPtrAdd
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlLongPtrAdd
---

# RtlLongPtrAdd function


## -description

Adds two values of type <b>LONG_PTR</b>.

## -parameters

### -param lAugend

<p>The first value in the equation.</p>

### -param lAddend

<p>The value to add to <i>u8Augend</i>.</p>

### -param plResult

<p>A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.</p>

## -remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

