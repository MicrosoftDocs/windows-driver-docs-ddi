---
UID: NF:ntintsafe.RtlUIntPtrMult
title: RtlUIntPtrMult function
author: windows-driver-content
description: Multiplies one value of type UINT_PTR by another.
old-location: kernel\rtluintptrmult.htm
old-project: kernel
ms.assetid: E484AB83-DEA6-4FC7-9896-26984D998661
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: RtlUIntPtrMult, RtlUIntPtrMult function [Kernel-Mode Driver Architecture], kernel.rtluintptrmult, ntintsafe/RtlUIntPtrMult
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	RtlUIntPtrMult
product: Windows
targetos: Windows
req.typenames: 
---

# RtlUIntPtrMult function


## -description


Multiplies one value of type <b>UINT_PTR</b> by another.


## -parameters




### -param uMultiplicand [in]

The value to be multiplied by <i>uMultiplier</i>.


### -param uMultiplier [in]

The value by which to multiply <i>uMultiplicand</i>.


### -param puResult [out]

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlUIntPtrMult
</li>
<li>RtlULongPtrMult
</li>
<li>RtlDWordPtrMult
</li>
<li>RtlSizeTMult
</li>
<li>RtlSIZETMult
</li>
<li>RtlDWordLongMult
</li>
<li>RtlULong64Mult
</li>
<li>RtlDWord64Mult
</li>
<li>RtlUInt64Mult
</li>
</ul>


