---
UID: NF:ntintsafe.RtlULongPtrToUInt
title: RtlULongPtrToUInt function
author: windows-driver-content
description: Converts a value of type ULONG_PTR to a value of type UINT.
old-location: kernel\rtlulongptrtouint.htm
old-project: kernel
ms.assetid: 0AD17F2A-8681-4C30-979A-D7DBBA21AD08
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlULongPtrToUInt function [Kernel-Mode Driver Architecture], ntintsafe/RtlULongPtrToUInt, kernel.rtlulongptrtouint, RtlULongPtrToUInt
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
-	RtlULongPtrToUInt
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlULongPtrToUInt function


## -description


Converts a value of type <b>ULONG_PTR</b> to a value of type <b>UINT</b>.


## -syntax


````
NTSTATUS RtlULongPtrToUInt(
  _In_  ULONG_PTR ulOperand,
  _Out_ UINT      *puResult
);
````


## -parameters




#### - ulOperand [in]

The value to be converted.


#### - puResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks


This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.


