---
UID: NF:ntintsafe.RtlLongPtrMult
title: RtlLongPtrMult function (ntintsafe.h)
description: Multiplies one value of type LONG_PTR by another.
old-location: kernel\rtllongptrmult.htm
tech.root: kernel
ms.assetid: AF602DBE-E106-4105-B56B-DE9EE7691A05
ms.date: 04/30/2018
keywords: ["RtlLongPtrMult function"]
ms.keywords: RtlLongPtrMult, RtlLongPtrMult function [Kernel-Mode Driver Architecture], kernel.rtllongptrmult, ntintsafe/RtlLongPtrMult
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
 - RtlLongPtrMult
 - ntintsafe/RtlLongPtrMult
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlLongPtrMult
---

# RtlLongPtrMult function


## -description

Multiplies one value of type <b>LONG_PTR</b> by another.

## -parameters

### -param lMultiplicand 

[in]
The value to be multiplied by <i>lMultiplier</i>.

### -param lMultiplier 

[in]
The value by which to multiply <i>lMultiplicand</i>.

### -param plResult 

[out]
A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

