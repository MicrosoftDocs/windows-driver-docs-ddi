---
UID: NF:ntintsafe.RtlLongPtrToInt8
title: RtlLongPtrToInt8 function
author: windows-driver-content
description: Converts a value of type LONG_PTR to a value of type INT8.
old-location: kernel\rtllongptrtoint8.htm
old-project: kernel
ms.assetid: 1C8FA483-3713-464E-91B7-0A8D754F5D16
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlLongPtrToInt8, RtlLongPtrToInt8 function [Kernel-Mode Driver Architecture], ntintsafe/RtlLongPtrToInt8, kernel.rtllongptrtoint8
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
-	RtlLongPtrToInt8
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlLongPtrToInt8 function


## -description


Converts a value of type <b>LONG_PTR</b> to a value of type <b>INT8</b>.


## -syntax


````
NTSTATUS RtlLongPtrToInt8(
  _In_  LONG_PTR lOperand,
  _Out_ INT8     *pi8Result
);
````


## -parameters




### -param lOperand [in]

The value to be converted.


### -param pi8Result [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks


This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:
<ul>
<li>
RtlSSIZETToInt8</li>
</ul>

