---
UID: NF:ntintsafe.RtlInt8Add
title: RtlInt8Add function (ntintsafe.h)
description: Adds two values of type INT8.
old-location: kernel\rtlint8add.htm
tech.root: kernel
ms.assetid: E97C3EA9-2244-458E-BE5E-6312023118A3
ms.date: 04/30/2018
keywords: ["RtlInt8Add function"]
ms.keywords: RtlInt8Add, RtlInt8Add function [Kernel-Mode Driver Architecture], kernel.rtlint8add, ntintsafe/RtlInt8Add
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
 - RtlInt8Add
 - ntintsafe/RtlInt8Add
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlInt8Add
---

# RtlInt8Add function


## -description

Adds two values of type <b>INT8</b>.

## -parameters

### -param i8Augend 

[in]
The first value in the equation.

### -param i8Addend 

[in]
The value to add to <i>i8Augend</i>.

### -param pi8Result 

[out]
A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

