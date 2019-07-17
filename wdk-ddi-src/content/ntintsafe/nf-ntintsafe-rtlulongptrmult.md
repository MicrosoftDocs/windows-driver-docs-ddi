---
UID: NF:ntintsafe.RtlULongPtrMult
title: RtlULongPtrMult function (ntintsafe.h)
description: Multiplies one value of type ULONG_PTR by another.
old-location: kernel\rtlulongptrmult.htm
tech.root: kernel
ms.assetid: 6E66CD0B-7CAD-4BF1-A6DD-56C5029A929E
ms.date: 04/30/2018
ms.keywords: RtlULongPtrMult, RtlULongPtrMult function [Kernel-Mode Driver Architecture], kernel.rtlulongptrmult, ntintsafe/RtlULongPtrMult
ms.topic: function
f1_keywords:
 - "ntintsafe/RtlULongPtrMult"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntintsafe.h
api_name:
- RtlULongPtrMult
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlULongPtrMult function


## -description


Multiplies one value of type <b>ULONG_PTR</b> by another.


## -parameters




### -param ulMultiplicand

<p>The value to be multiplied by <i>Multiplier</i>.</p>


### -param ulMultiplier

<p>The value by which to multiply <i>Multiplicand</i>.</p>


### -param pulResult

<p>A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.</p>




## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.



