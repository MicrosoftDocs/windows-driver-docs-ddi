---
UID: NF:ntintsafe.RtlULongLongMult
title: RtlULongLongMult function (ntintsafe.h)
description: Multiplies one value of type ULONGLONG by another.
old-location: kernel\rtlulonglongmult.htm
tech.root: kernel
ms.assetid: 9865C8D1-DA20-4733-8862-7CA38069A93F
ms.date: 04/30/2018
keywords: ["RtlULongLongMult function"]
ms.keywords: RtlULongLongMult, RtlULongLongMult function [Kernel-Mode Driver Architecture], kernel.rtlulonglongmult, ntintsafe/RtlULongLongMult
f1_keywords:
 - "ntintsafe/RtlULongLongMult"
 - "RtlULongLongMult"
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
- RtlULongLongMult
targetos: Windows
req.typenames: 
---

# RtlULongLongMult function


## -description


Multiplies one value of type <b>ULONGLONG</b> by another.


## -parameters




### -param ullMultiplicand [in]

The value to be multiplied by <i>ullMultiplier</i>.


### -param ullMultiplier [in]

The value by which to multiply <i>ullMultiplicand</i>.


### -param pullResult [out]

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.



