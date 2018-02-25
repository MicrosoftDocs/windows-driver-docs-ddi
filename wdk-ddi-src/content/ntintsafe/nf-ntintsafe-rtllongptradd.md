---
UID: NF:ntintsafe.RtlLongPtrAdd
title: RtlLongPtrAdd function
author: windows-driver-content
description: Adds two values of type LONG_PTR.
old-location: kernel\rtllongptradd.htm
old-project: kernel
ms.assetid: D0036070-A23D-4525-AE80-E10B20330F97
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , A, L, P, R, RtlLongPtrAdd, RtlLongPtrAdd function [Kernel-Mode Driver Architecture], d, g, kernel.rtllongptradd, l, n, ntintsafe/RtlLongPtrAdd, o, r, t"
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
-	RtlLongPtrAdd
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlLongPtrAdd function


## -description


Adds two values of type <b>LONG_PTR</b>.


## -syntax


````
NTSTATUS RtlLongPtrAdd(
  _In_  UINT8 u8Augend,
  _In_  UINT8 u8Addend,
  _Out_ UINT8 *pu8Result
);
````


## -parameters




### -param lAugend

TBD


### -param lAddend

TBD


### -param plResult

TBD




#### - u8Augend [in]

The first value in the equation.


#### - u8Addend [in]

The value to add to <i>u8Augend</i>.


#### - pu8Result [out]

A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.



