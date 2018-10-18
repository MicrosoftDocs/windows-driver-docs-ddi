---
UID: NF:ntintsafe.RtlUIntPtrToInt16
title: RtlUIntPtrToInt16 function
author: windows-driver-content
description: Converts a value of type UINT_PTR to a value of type INT16.
old-location: kernel\rtluintptrtoint16.htm
tech.root: kernel
ms.assetid: 11FA2777-93AA-4833-8726-4C6E5FADD0B9
ms.date: 04/30/2018
ms.keywords: RtlUIntPtrToInt16, RtlUIntPtrToInt16 function [Kernel-Mode Driver Architecture], kernel.rtluintptrtoint16, ntintsafe/RtlUIntPtrToInt16
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
-	RtlUIntPtrToInt16
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUIntPtrToInt16 function


## -description


Converts a value of type <b>UINT_PTR</b> to a value of type <b>INT16</b>.


## -parameters




### -param uOperand [in]

The value to be converted.


### -param pi16Result [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



