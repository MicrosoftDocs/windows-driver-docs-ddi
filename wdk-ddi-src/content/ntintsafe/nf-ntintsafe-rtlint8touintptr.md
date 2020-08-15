---
UID: NF:ntintsafe.RtlInt8ToUIntPtr
title: RtlInt8ToUIntPtr function (ntintsafe.h)
description: Converts a value of type INT8 to a value of type UINT_PTR.
old-location: kernel\rtlint8touintptr.htm
tech.root: kernel
ms.assetid: B96B17E1-911F-442F-811F-294AB14D7058
ms.date: 04/30/2018
keywords: ["RtlInt8ToUIntPtr function"]
ms.keywords: RtlInt8ToUIntPtr, RtlInt8ToUIntPtr function [Kernel-Mode Driver Architecture], kernel.rtlint8touintptr, ntintsafe/RtlInt8ToUIntPtr
f1_keywords:
 - "ntintsafe/RtlInt8ToUIntPtr"
 - "RtlInt8ToUIntPtr"
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
- RtlInt8ToUIntPtr
targetos: Windows
req.typenames: 
---

# RtlInt8ToUIntPtr function


## -description


Converts a value of type <b>INT8</b> to a value of type <b>UINT_PTR</b>.


## -parameters




### -param i8Operand 
[in]
The value to be converted.


### -param puResult 
[out]
A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlInt8ToSizeT</li>
</ul>


