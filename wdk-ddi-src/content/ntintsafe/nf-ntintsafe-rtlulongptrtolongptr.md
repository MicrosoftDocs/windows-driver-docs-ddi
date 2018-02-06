---
UID: NF:ntintsafe.RtlULongPtrToLongPtr
title: RtlULongPtrToLongPtr function
author: windows-driver-content
description: Converts a value of type ULONG_PTR to a value of type LONG_PTR.
old-location: kernel\rtlulongptrtolongptr.htm
old-project: kernel
ms.assetid: 5231A8BC-2F7A-4A2C-931C-D3A81563754A
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.rtlulongptrtolongptr, ntintsafe/RtlULongPtrToLongPtr, RtlULongPtrToLongPtr, RtlULongPtrToLongPtr function [Kernel-Mode Driver Architecture]
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
-	RtlULongPtrToLongPtr
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlULongPtrToLongPtr function


## -description


Converts a value of type <b>ULONG_PTR</b> to a value of type <b>LONG_PTR</b>.


## -syntax


````
NTSTATUS RtlULongPtrToLongPtr(
  _In_  ULONG_PTR ulOperand,
  _Out_ LONG_PTR  *plResult
);
````


## -parameters




### -param ulOperand [in]

The value to be converted.


### -param plResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks


This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.


