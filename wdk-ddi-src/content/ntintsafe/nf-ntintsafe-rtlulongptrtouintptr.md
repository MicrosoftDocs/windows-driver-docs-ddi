---
UID: NF:ntintsafe.RtlULongPtrToUIntPtr
title: RtlULongPtrToUIntPtr function
author: windows-driver-content
description: Converts a value of type ULONG_PTR to a value of type UINT_PTR.
old-location: kernel\rtlulongptrtouintptr.htm
tech.root: kernel
ms.assetid: 2FB3E4E4-77D6-477C-B206-62E460D853D3
ms.date: 04/30/2018
ms.keywords: RtlULongPtrToUIntPtr, RtlULongPtrToUIntPtr function [Kernel-Mode Driver Architecture], kernel.rtlulongptrtouintptr, ntintsafe/RtlULongPtrToUIntPtr
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
-	RtlULongPtrToUIntPtr
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlULongPtrToUIntPtr function


## -description


Converts a value of type <b>ULONG_PTR</b> to a value of type <b>UINT_PTR</b>.


## -parameters




### -param ulOperand [in]

The value to be converted.


### -param puResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



