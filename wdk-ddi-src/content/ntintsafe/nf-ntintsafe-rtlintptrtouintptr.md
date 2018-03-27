---
UID: NF:ntintsafe.RtlIntPtrToUIntPtr
title: RtlIntPtrToUIntPtr function
author: windows-driver-content
description: Converts a value of type INT_PTR to a value of type UINT_PTR.
old-location: kernel\rtlintptrtouintptr.htm
old-project: kernel
ms.assetid: A4677F86-C98A-4F8B-98CA-86082A7D77FD
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: RtlIntPtrToUIntPtr, RtlIntPtrToUIntPtr function [Kernel-Mode Driver Architecture], kernel.rtlintptrtouintptr, ntintsafe/RtlIntPtrToUIntPtr
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
-	RtlIntPtrToUIntPtr
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlIntPtrToUIntPtr function


## -description


Converts a value of type <b>INT_PTR</b> to a value of type <b>UINT_PTR</b>.


## -parameters




### -param iOperand [in]

The value to be converted.


### -param puResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlIntPtrToSizeT
</li>
<li>RtlPtrdiffTToUIntPtr
</li>
<li>RtlPtrdiffTToSizeT
</li>
</ul>


