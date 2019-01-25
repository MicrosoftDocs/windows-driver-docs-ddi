---
UID: NF:ntintsafe.RtlULongPtrSub
title: RtlULongPtrSub function (ntintsafe.h)
description: Subtracts one value of type ULONG_PTR from another.
old-location: kernel\rtlulongptrsub.htm
tech.root: kernel
ms.assetid: E8F9A1B0-5E87-4CB0-8C9E-5C2494F07C39
ms.date: 04/30/2018
ms.keywords: RtlULongPtrSub, RtlULongPtrSub function [Kernel-Mode Driver Architecture], kernel.rtlulongptrsub, ntintsafe/RtlULongPtrSub
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
-	RtlULongPtrSub
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlULongPtrSub function


## -description


Subtracts one value of type <b>ULONG_PTR</b> from another.


## -parameters




### -param ulMinuend [in]

The value from which <i>ulSubtrahend</i> is subtracted.


### -param ulSubtrahend [in]

The value to subtract from <i>ulMinuend</i>.


### -param pulResult [out]

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.



