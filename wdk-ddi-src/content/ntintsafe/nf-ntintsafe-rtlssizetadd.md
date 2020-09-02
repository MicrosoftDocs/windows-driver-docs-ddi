---
UID: NF:ntintsafe.RtlSSIZETAdd
title: RtlSSIZETAdd function (ntintsafe.h)
description: Adds two values of type SSIZE_T.
old-location: kernel\rtlssizetadd.htm
tech.root: kernel
ms.assetid: 1CBB3CDF-E7DD-4686-8EF6-FBCADE978A16
ms.date: 04/30/2018
keywords: ["RtlSSIZETAdd function"]
ms.keywords: RtlSSIZETAdd, RtlSSIZETAdd function [Kernel-Mode Driver Architecture], kernel.rtlssizetadd, ntintsafe/RtlSSIZETAdd
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
 - RtlSSIZETAdd
 - ntintsafe/RtlSSIZETAdd
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlSSIZETAdd
---

# RtlSSIZETAdd function


## -description

Adds two values of type <b>SSIZE_T</b>.

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

