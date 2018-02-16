---
UID: NF:ntintsafe.RtlULongPtrToChar
title: RtlULongPtrToChar function
author: windows-driver-content
description: Converts a value of type ULONG_PTR to a value of type CHAR.
old-location: kernel\rtlulongptrtochar.htm
old-project: kernel
ms.assetid: DB015FC3-D263-4EA6-AAE1-E4ECA3ECF4F9
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlULongPtrToChar, ntintsafe/RtlULongPtrToChar, kernel.rtlulongptrtochar, RtlULongPtrToChar function [Kernel-Mode Driver Architecture]
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
-	RtlULongPtrToChar
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlULongPtrToChar function


## -description


Converts a value of type <b>ULONG_PTR</b> to a value of type <b>CHAR</b>.


## -syntax


````
NTSTATUS RtlULongPtrToChar(
  _In_  ULONG_PTR ulOperand,
  _Out_ CHAR      *pch
);
````


## -parameters




### -param ulOperand [in]

The value to be converted.


### -param pch [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



