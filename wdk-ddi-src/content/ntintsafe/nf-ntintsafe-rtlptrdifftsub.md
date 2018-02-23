---
UID: NF:ntintsafe.RtlPtrdiffTSub
title: RtlPtrdiffTSub function
author: windows-driver-content
description: Subtracts one value of type PTRDIFF_T from another.
old-location: kernel\rtlptrdifftsub.htm
old-project: kernel
ms.assetid: C87E3BD5-8CA7-443E-8CC3-F863CD4F321A
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlPtrdiffTSub function [Kernel-Mode Driver Architecture], RtlPtrdiffTSub, kernel.rtlptrdifftsub, ntintsafe/RtlPtrdiffTSub
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
-	RtlPtrdiffTSub
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlPtrdiffTSub function


## -description


Subtracts one value of type <b>PTRDIFF_T</b> from another.


## -syntax


````
NTSTATUS RtlPtrdiffTSub(
  _In_  PTRDIFF_T Minuend,
  _In_  PTRDIFF_T Subtrahend,
  _Out_ PTRDIFF_T *pResult
);
````


## -parameters




### -param Minuend [in]

The value from which <i>Subtrahend</i> is subtracted.


### -param Subtrahend [in]

The value to subtract from <i>Minuend</i>.


### -param pResult [out]

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.



