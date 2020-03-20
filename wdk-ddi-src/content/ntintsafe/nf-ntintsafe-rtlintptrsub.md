---
UID: NF:ntintsafe.RtlIntPtrSub
title: RtlIntPtrSub function (ntintsafe.h)
description: Subtracts one value of type INT_PTR from another.
old-location: kernel\rtlintptrsub.htm
tech.root: kernel
ms.assetid: 72352FD3-4855-4630-AF42-368FF3A6B2BB
ms.date: 04/30/2018
keywords: ["RtlIntPtrSub function"]
ms.keywords: RtlIntPtrSub, RtlIntPtrSub function [Kernel-Mode Driver Architecture], kernel.rtlintptrsub, ntintsafe/RtlIntPtrSub
f1_keywords:
 - "ntintsafe/RtlIntPtrSub"
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
- RtlIntPtrSub
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlIntPtrSub function


## -description


Subtracts one value of type <b>INT_PTR</b> from another.


## -parameters




### -param iMinuend [in]

The value from which <i>iSubtrahend</i> is subtracted.


### -param iSubtrahend [in]

The value to subtract from <i>iMinuend</i>.


### -param piResult [out]

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.



