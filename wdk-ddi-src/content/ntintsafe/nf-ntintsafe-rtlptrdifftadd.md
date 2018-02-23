---
UID: NF:ntintsafe.RtlPtrdiffTAdd
title: RtlPtrdiffTAdd function
author: windows-driver-content
description: Adds two values of type PTRDIFF_T.
old-location: kernel\rtlptrdifftadd.htm
old-project: kernel
ms.assetid: 3B4C0CF0-8153-446E-A834-C1FE28651718
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.rtlptrdifftadd, RtlPtrdiffTAdd, RtlPtrdiffTAdd function [Kernel-Mode Driver Architecture], ntintsafe/RtlPtrdiffTAdd
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
-	RtlPtrdiffTAdd
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlPtrdiffTAdd function


## -description


Adds two values of type <b>PTRDIFF_T</b>.


## -syntax


````
NTSTATUS RtlPtrdiffTAdd(
  _In_  PTRDIFF_T Augend,
  _In_  PTRDIFF_T Addend,
  _Out_ PTRDIFF_T *pResult
);
````


## -parameters




### -param Augend [in]

The first value in the equation.


### -param Addend [in]

The value to add to <i>Augend</i>.


### -param pResult [out]

A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.



