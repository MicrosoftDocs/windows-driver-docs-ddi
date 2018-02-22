---
UID: NF:ntintsafe.RtlUIntPtrToInt
title: RtlUIntPtrToInt function
author: windows-driver-content
description: Converts a value of type UINT_PTR to a value of type INT.
old-location: kernel\rtluintptrtoint.htm
old-project: kernel
ms.assetid: C33B717D-0874-47AB-8503-D6F82F713CBF
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.rtluintptrtoint, RtlUIntPtrToInt function [Kernel-Mode Driver Architecture], ntintsafe/RtlUIntPtrToInt, RtlUIntPtrToInt
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntintsafe.h
apiname:
-	RtlUIntPtrToInt
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlUIntPtrToInt function


## -description


Converts a value of type <b>UINT_PTR</b> to a value of type <b>INT</b>.


## -syntax


````
NTSTATUS RtlUIntPtrToInt(
  _In_  UINT_PTR uOperand,
  _Out_ INT      *piResult
);
````


## -parameters




### -param uOperand [in]

The value to be converted.


### -param piResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlUIntPtrToInt32
</li>
<li>RtlSizeTToInt
</li>
<li>RtlSizeTToInt32
</li>
</ul>


