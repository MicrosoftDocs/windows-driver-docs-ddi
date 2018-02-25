---
UID: NF:ntintsafe.RtlIntPtrSub
title: RtlIntPtrSub function
author: windows-driver-content
description: Subtracts one value of type INT_PTR from another.
old-location: kernel\rtlintptrsub.htm
old-project: kernel
ms.assetid: 72352FD3-4855-4630-AF42-368FF3A6B2BB
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , I, P, R, RtlIntPtrSub, RtlIntPtrSub function [Kernel-Mode Driver Architecture], S, b, kernel.rtlintptrsub, l, n, ntintsafe/RtlIntPtrSub, r, t, u"
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
-	RtlIntPtrSub
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlIntPtrSub function


## -description


Subtracts one value of type <b>INT_PTR</b> from another.


## -syntax


````
NTSTATUS RtlIntPtrSub(
  _In_  INT_PTR iMinuend,
  _In_  INT_PTR iSubtrahend,
  _Out_ INT_PTR *piResult
);
````


## -parameters




### -param iMinuend [in]

The value from which <i>iSubtrahend</i> is subtracted.


### -param iSubtrahend [in]

The value to subtract from <i>iMinuend</i>.


### -param piResult [out]

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.



