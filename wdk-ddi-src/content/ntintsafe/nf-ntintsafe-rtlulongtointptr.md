---
UID: NF:ntintsafe.RtlULongToIntPtr
title: RtlULongToIntPtr function
description: Converts a value of type ULONG to a value of type INT_PTR.
old-location: kernel\rtlulongtointptr.htm
tech.root: kernel
ms.assetid: EEAA1C05-BB93-4D8A-9AD6-6F109BBE4FE0
ms.date: 04/30/2018
ms.keywords: RtlULongToIntPtr, RtlULongToIntPtr function [Kernel-Mode Driver Architecture], kernel.rtlulongtointptr, ntintsafe/RtlULongToIntPtr
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
-	RtlULongToIntPtr
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlULongToIntPtr function


## -description


Converts a value of type <b>ULONG</b> to a value of type <b>INT_PTR</b>.


## -parameters




### -param ulOperand [in]

The value to be converted.


### -param piResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



