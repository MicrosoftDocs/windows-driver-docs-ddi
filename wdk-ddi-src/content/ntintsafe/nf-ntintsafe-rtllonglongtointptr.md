---
UID: NF:ntintsafe.RtlLongLongToIntPtr
title: RtlLongLongToIntPtr function
author: windows-driver-content
description: Converts a value of type LONGLONG to a value of type INT_PTR.
old-location: kernel\rtllonglongtointptr.htm
old-project: kernel
ms.assetid: 7BFAB50B-7C0A-40D8-AB6D-ECBBDA0387AA
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlLongLongToIntPtr function [Kernel-Mode Driver Architecture], kernel.rtllonglongtointptr, RtlLongLongToIntPtr, ntintsafe/RtlLongLongToIntPtr
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
-	RtlLongLongToIntPtr
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlLongLongToIntPtr function


## -description


Converts a value of type <b>LONGLONG</b> to a value of type <b>INT_PTR</b>.


## -syntax


````
NTSTATUS RtlLongLongToIntPtr(
  _In_  LONGLONG llOperand,
  _Out_ INT_PTR  *piResult
);
````


## -parameters




### -param llOperand [in]

The value to be converted.


### -param piResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks


This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:
<ul>
<li>
RtlLongLongToPtrdiffT
</li>
<li>RtlLong64ToIntPtr
</li>
<li>RtlLong64ToPtrdiffT
</li>
<li>RtlInt64ToIntPtr
</li>
<li>RtlInt64ToPtrdiffT
</li>
</ul>

