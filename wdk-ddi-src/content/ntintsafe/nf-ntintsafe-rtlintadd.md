---
UID: NF:ntintsafe.RtlIntAdd
title: RtlIntAdd function (ntintsafe.h)
description: Adds two values of type INT.
old-location: kernel\rtlintadd.htm
tech.root: kernel
ms.assetid: DF556961-D5BA-4A50-9E6A-DACE96D13B50
ms.date: 04/30/2018
keywords: ["RtlIntAdd function"]
ms.keywords: RtlIntAdd, RtlIntAdd function [Kernel-Mode Driver Architecture], kernel.rtlintadd, ntintsafe/RtlIntAdd
f1_keywords:
 - "ntintsafe/RtlIntAdd"
 - "RtlIntAdd"
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
- RtlIntAdd
targetos: Windows
req.typenames: 
---

# RtlIntAdd function


## -description


Adds two values of type <b>INT</b>.


## -parameters




### -param iAugend 
[in]
The first value in the equation.


### -param iAddend 
[in]
The value to add to <i>iAugend</i>.


### -param piResult 
[out]
A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlInt32Add
</li>
<li>RtlLong32Add
</li>
</ul>


