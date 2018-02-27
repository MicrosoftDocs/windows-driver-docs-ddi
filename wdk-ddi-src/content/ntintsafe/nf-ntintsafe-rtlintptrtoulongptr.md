---
UID: NF:ntintsafe.RtlIntPtrToULongPtr
title: RtlIntPtrToULongPtr function
author: windows-driver-content
description: Converts a value of type INT_PTR to a value of type ULONG_PTR.
old-location: kernel\rtlintptrtoulongptr.htm
old-project: kernel
ms.assetid: DE6CD62F-0792-490A-9DDD-A979CAC0565A
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: RtlIntPtrToULongPtr, RtlIntPtrToULongPtr function [Kernel-Mode Driver Architecture], kernel.rtlintptrtoulongptr, ntintsafe/RtlIntPtrToULongPtr
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
-	RtlIntPtrToULongPtr
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlIntPtrToULongPtr function


## -description


Converts a value of type <b>INT_PTR</b> to a value of type <b>ULONG_PTR</b>.


## -syntax


````
NTSTATUS RtlIntPtrToULongPtr(
  _In_  INT_PTR   iOperand,
  _Out_ ULONG_PTR *pulResult
);
````


## -parameters




### -param iOperand [in]

The value to be converted.


### -param pulResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlIntPtrToDWordPtr
</li>
<li>RtlIntPtrToSIZET
</li>
<li>RtlPtrdiffTToULongPtr
</li>
<li>RtlPtrdiffTToDWordPtr
</li>
<li>RtlPtrdiffTToSIZET
</li>
</ul>


