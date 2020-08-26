---
UID: NF:ntintsafe.RtlShortMult
title: RtlShortMult function (ntintsafe.h)
description: Multiplies one value of type SHORT by another.
old-location: kernel\rtlshortmult.htm
tech.root: kernel
ms.assetid: 15DCCCF1-72B1-4944-9BF0-ACAF1DEB9243
ms.date: 04/30/2018
keywords: ["RtlShortMult function"]
ms.keywords: RtlShortMult, RtlShortMult function [Kernel-Mode Driver Architecture], kernel.rtlshortmult, ntintsafe/RtlShortMult
f1_keywords:
 - "ntintsafe/RtlShortMult"
 - "RtlShortMult"
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
- RtlShortMult
targetos: Windows
req.typenames: 
---

# RtlShortMult function


## -description


Multiplies one value of type <b>SHORT</b> by another.


## -parameters




### -param sMultiplicand 
[in]
The value to be multiplied by <i>sMultiplier</i>.


### -param sMultiplier 
[in]
The value by which to multiply <i>sMultiplicand</i>.


### -param psResult 
[out]
A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlInt16Mult
</li>
</ul>


