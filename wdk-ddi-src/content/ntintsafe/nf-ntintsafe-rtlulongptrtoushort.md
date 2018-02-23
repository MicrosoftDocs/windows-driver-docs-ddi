---
UID: NF:ntintsafe.RtlULongPtrToUShort
title: RtlULongPtrToUShort function
author: windows-driver-content
description: Converts a value of type ULONG_PTR to a value of type USHORT.
old-location: kernel\rtlulongptrtoushort.htm
old-project: kernel
ms.assetid: 444A0D3B-AEC3-4474-949F-6C62F54DA43A
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlULongPtrToUShort function [Kernel-Mode Driver Architecture], RtlULongPtrToUShort, ntintsafe/RtlULongPtrToUShort, kernel.rtlulongptrtoushort
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
-	RtlULongPtrToUShort
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlULongPtrToUShort function


## -description


Converts a value of type <b>ULONG_PTR</b> to a value of type <b>USHORT</b>.


## -syntax


````
NTSTATUS RtlULongPtrToUShort(
  _In_  ULONG_PTR ulOperand,
  _Out_ USHORT    *pusResult
);
````


## -parameters




### -param ulOperand [in]

The value to be converted.


### -param pusResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



