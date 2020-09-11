---
UID: NF:ntintsafe.RtlULongAdd
title: RtlULongAdd function (ntintsafe.h)
description: Adds two values of type ULONG.
old-location: kernel\rtlulongadd.htm
tech.root: kernel
ms.assetid: 03E5C0DB-E245-43E2-80C0-0C1D67673038
ms.date: 04/30/2018
keywords: ["RtlULongAdd function"]
ms.keywords: RtlULongAdd, RtlULongAdd function [Kernel-Mode Driver Architecture], kernel.rtlulongadd, ntintsafe/RtlULongAdd
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
 - RtlULongAdd
 - ntintsafe/RtlULongAdd
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlULongAdd
---

# RtlULongAdd function


## -description

Adds two values of type <b>ULONG</b>.

## -parameters

### -param ulAugend 

[in]
The first value in the equation.

### -param ulAddend 

[in]
The value to add to <i>ulAugend</i>.

### -param pulResult 

[out]
A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

