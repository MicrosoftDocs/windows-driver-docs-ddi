---
UID: NF:ntintsafe.RtlSizeTAdd
title: RtlSizeTAdd function (ntintsafe.h)
description: Adds two values of type SIZE_T.
old-location: kernel\rtlsizetadd.htm
tech.root: kernel
ms.assetid: A3A2BD4D-F95D-4427-BE63-80A6E9AC9293
ms.date: 04/30/2018
keywords: ["RtlSizeTAdd function"]
ms.keywords: RtlSizeTAdd, RtlSizeTAdd function [Kernel-Mode Driver Architecture], kernel.rtlsizetadd, ntintsafe/RtlSizeTAdd
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
 - RtlSizeTAdd
 - ntintsafe/RtlSizeTAdd
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlSizeTAdd
---

# RtlSizeTAdd function


## -description

Adds two values of type <b>SIZE_T</b>.

## -parameters

### -param Augend 

[in]
The first value in the equation.

### -param Addend 

[in]
The value to add to <i>Augend</i>.

### -param pResult 

[out]
A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

