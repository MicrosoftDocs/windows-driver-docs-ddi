---
UID: NF:ntintsafe.RtlULongPtrToInt8
title: RtlULongPtrToInt8 function
author: windows-driver-content
description: Converts a value of type ULONG_PTR to a value of type INT8.
old-location: kernel\rtlulongptrtoint8.htm
old-project: kernel
ms.assetid: D2A77B0A-9307-4090-AE3D-049E5C414D31
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlULongPtrToInt8, RtlULongPtrToInt8 function [Kernel-Mode Driver Architecture], ntintsafe/RtlULongPtrToInt8, kernel.rtlulongptrtoint8
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
-	RtlULongPtrToInt8
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlULongPtrToInt8 function


## -description


Converts a value of type <b>ULONG_PTR</b> to a value of type <b>INT8</b>.


## -syntax


````
NTSTATUS RtlULongPtrToInt8(
  _In_  ULONG_PTR ulOperand,
  _Out_ INT8      *pi8Result
);
````


## -parameters




### -param ulOperand [in]

The value to be converted.


### -param pi8Result [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks


This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.


