---
UID: NF:ntintsafe.RtlShortToUIntPtr
title: RtlShortToUIntPtr function
author: windows-driver-content
description: Converts a value of type SHORT to a value of type UINT_PTR.
old-location: kernel\rtlshorttouintptr.htm
old-project: kernel
ms.assetid: C9E81C1A-56F2-414F-8FE5-847E291A022A
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlShortToUIntPtr function [Kernel-Mode Driver Architecture], RtlShortToUIntPtr, kernel.rtlshorttouintptr, ntintsafe/RtlShortToUIntPtr
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
-	RtlShortToUIntPtr
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlShortToUIntPtr function


## -description


Converts a value of type <b>SHORT</b> to a value of type <b>UINT_PTR</b>.


## -syntax


````
NTSTATUS RtlShortToUIntPtr(
  _In_  SHORT    sOperand,
  _Out_ UINT_PTR *puResult
);
````


## -parameters




### -param sOperand [in]

The value to be converted.


### -param puResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks


This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:
<ul>
<li>RtlShortToSizeT
</li>
<li>RtlInt16ToUIntPtr
</li>
<li>RtlInt16ToSizeT
</li>
</ul>

