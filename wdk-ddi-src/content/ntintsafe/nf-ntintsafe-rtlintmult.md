---
UID: NF:ntintsafe.RtlIntMult
title: RtlIntMult function (ntintsafe.h)
description: Multiplies one value of type INT by another.
old-location: kernel\rtlintmult.htm
tech.root: kernel
ms.assetid: 5417D6B1-0523-4C01-9C07-571D096E10F3
ms.date: 04/30/2018
ms.keywords: RtlIntMult, RtlIntMult function [Kernel-Mode Driver Architecture], kernel.rtlintmult, ntintsafe/RtlIntMult
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntintsafe.h
api_name:
-	RtlIntMult
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlIntMult function


## -description


Multiplies one value of type <b>INT</b> by another.


## -parameters




### -param iMultiplicand [in]

The value to be multiplied by <i>iMultiplier</i>.


### -param iMultiplier [in]

The value by which to multiply <i>iMultiplicand</i>.


### -param piResult [out]

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlInt32Mult</li>
<li>RtlLong32Mult
</li>
</ul>


