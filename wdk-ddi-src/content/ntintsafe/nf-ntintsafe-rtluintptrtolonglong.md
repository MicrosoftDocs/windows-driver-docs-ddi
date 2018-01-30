---
UID: NF:ntintsafe.RtlUIntPtrToLongLong
title: RtlUIntPtrToLongLong function
author: windows-driver-content
description: Converts a value of type UINT_PTR to a value of type LONGLONG.
old-location: kernel\rtluintptrtolonglong.htm
old-project: kernel
ms.assetid: EFEE4662-9FB1-4E44-BE54-2C7932104F28
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.rtluintptrtolonglong, RtlUIntPtrToLongLong function [Kernel-Mode Driver Architecture], ntintsafe/RtlUIntPtrToLongLong, RtlUIntPtrToLongLong
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
-	RtlUIntPtrToLongLong
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlUIntPtrToLongLong function


## -description


Converts a value of type <b>UINT_PTR</b> to a value of type <b>LONGLONG</b>.


## -syntax


````
NTSTATUS RtlUIntPtrToLongLong(
  _In_  UINT_PTR uOperand,
  _Out_ LONGLONG *pllResult
);
````


## -parameters




### -param uOperand [in]

The value to be converted.


### -param pllResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks


This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:
<ul>
<li>RtlUIntPtrToLong64
</li>
<li>RtlUIntPtrToInt64
</li>
<li>RtlSizeTToLongLong
</li>
<li>RtlSizeTToLong64
</li>
<li>RtlSizeTToInt64
</li>
</ul>

