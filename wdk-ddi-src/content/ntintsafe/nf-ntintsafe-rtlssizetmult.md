---
UID: NF:ntintsafe.RtlSSIZETMult
title: RtlSSIZETMult function (ntintsafe.h)
description: Multiplies one value of type SSIZE_T by another.
old-location: kernel\rtlssizetmult.htm
tech.root: kernel
ms.assetid: 43FFE47F-C8A3-49B4-B61A-3EAF3841037D
ms.date: 04/30/2018
ms.keywords: RtlSSIZETMult, RtlSSIZETMult function [Kernel-Mode Driver Architecture], kernel.rtlssizetmult, ntintsafe/RtlSSIZETMult
ms.topic: function
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
- RtlSSIZETMult
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlSSIZETMult function


## -description


Multiplies one value of type <b>SSIZE_T</b> by another.


## -parameters




### -param Multiplicand [in]

The value to be multiplied by <i>Multiplier</i>.


### -param Multiplier [in]

The value by which to multiply <i>Multiplicand</i>.


### -param pResult [out]

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.



