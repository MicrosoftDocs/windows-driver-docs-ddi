---
UID: NF:ntintsafe.RtlLongLongToLongPtr
title: RtlLongLongToLongPtr function
author: windows-driver-content
description: Converts a value of type LONGLONG to a value of type LONG_PTR.
old-location: kernel\rtllonglongtolongptr.htm
old-project: kernel
ms.assetid: 1E7B693A-B363-4AE0-B9E3-45CC01FE9724
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: RtlLongLongToLongPtr, RtlLongLongToLongPtr function [Kernel-Mode Driver Architecture], kernel.rtllonglongtolongptr, ntintsafe/RtlLongLongToLongPtr
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
-	RtlLongLongToLongPtr
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlLongLongToLongPtr function


## -description


Converts a value of type <b>LONGLONG</b> to a value of type <b>LONG_PTR</b>.


## -parameters




### -param llOperand [in]

The value to be converted.


### -param plResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>
RtlLongLongToSSIZET
</li>
<li>RtlLong64ToLongPtr
</li>
<li>RtlLong64ToSSIZET
</li>
<li>RtlInt64ToLongPtr
</li>
<li>RtlInt64ToSSIZET
</li>
</ul>


