---
UID: NF:ntintsafe.RtlULongMult
title: RtlULongMult function
author: windows-driver-content
description: Multiplies one value of type ULONG by another.
old-location: kernel\rtlulongmult.htm
old-project: kernel
ms.assetid: 2D5DA884-1746-4DBC-8ABC-2D307181CCAE
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: RtlULongMult, RtlULongMult function [Kernel-Mode Driver Architecture], kernel.rtlulongmult, ntintsafe/RtlULongMult
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
-	RtlULongMult
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlULongMult function


## -description


Multiplies one value of type <b>ULONG</b> by another.


## -parameters




### -param ulMultiplicand [in]

The value to be multiplied by <i>ulMultiplier</i>.


### -param ulMultiplier [in]

The value by which to multiply <i>ulMultiplicand</i>.


### -param pulResult [out]

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.



