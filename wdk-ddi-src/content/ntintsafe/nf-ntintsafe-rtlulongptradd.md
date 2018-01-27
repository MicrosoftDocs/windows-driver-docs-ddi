---
UID: NF:ntintsafe.RtlULongPtrAdd
title: RtlULongPtrAdd function
author: windows-driver-content
description: Adds two values of type ULONG_PTR.
old-location: kernel\rtlulongptradd.htm
old-project: kernel
ms.assetid: 26A9A0B6-07A3-4D42-A5A1-C4CDD541A3FA
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlULongPtrAdd function [Kernel-Mode Driver Architecture], kernel.rtlulongptradd, ntintsafe/RtlULongPtrAdd, RtlULongPtrAdd
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
-	RtlULongPtrAdd
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlULongPtrAdd function


## -description


Adds two values of type <b>ULONG_PTR</b>.


## -syntax


````
NTSTATUS RtlULongPtrAdd(
  _In_  ULONG_PTR ulAugend,
  _In_  ULONG_PTR ulAddend,
  _Out_ ULONG_PTR *pulResult
);
````


## -parameters




### -param ulAugend [in]

The first value in the equation.


### -param ulAddend [in]

The value to add to <i>ulAugend</i>.


### -param pulResult [out]

A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

