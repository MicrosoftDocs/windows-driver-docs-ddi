---
UID: NF:ntintsafe.RtlInt8Add
title: RtlInt8Add function
author: windows-driver-content
description: Adds two values of type INT8.
old-location: kernel\rtlint8add.htm
old-project: kernel
ms.assetid: E97C3EA9-2244-458E-BE5E-6312023118A3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , 8, A, I, R, RtlInt8Add, RtlInt8Add function [Kernel-Mode Driver Architecture], d, kernel.rtlint8add, l, n, ntintsafe/RtlInt8Add, t"
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
-	RtlInt8Add
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlInt8Add function


## -description


Adds two values of type <b>INT8</b>.


## -syntax


````
NTSTATUS RtlInt8Add(
  _In_  INT8 i8Augend,
  _In_  INT8 i8Addend,
  _Out_ INT8 *pi8Result
);
````


## -parameters




### -param i8Augend [in]

The first value in the equation.


### -param i8Addend [in]

The value to add to <i>i8Augend</i>.


### -param pi8Result [out]

A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.



