---
UID: NF:ntintsafe.RtlIntPtrToULongLong
title: RtlIntPtrToULongLong function
author: windows-driver-content
description: Converts a value of type INT_PTR to a value of type ULONGLONG.
old-location: kernel\rtlintptrtoulonglong.htm
old-project: kernel
ms.assetid: FF5D7B10-86AE-4C01-AFA9-C0C94E566428
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: RtlIntPtrToULongLong, RtlIntPtrToULongLong function [Kernel-Mode Driver Architecture], kernel.rtlintptrtoulonglong, ntintsafe/RtlIntPtrToULongLong
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
-	RtlIntPtrToULongLong
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlIntPtrToULongLong function


## -description


Converts a value of type <b>INT_PTR</b> to a value of type <b>ULONGLONG</b>.


## -syntax


````
NTSTATUS RtlIntPtrToULongLong(
  _In_  INT_PTR   iOperand,
  _Out_ ULONGLONG *pullResult
);
````


## -parameters




### -param iOperand [in]

The value to be converted.


### -param pullResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlIntPtrToDWordLong
</li>
<li>RtlIntPtrToULong64
</li>
<li>RtlIntPtrToDWord64
</li>
<li>RtlIntPtrToUInt64
</li>
<li>RtlPtrdiffTToULongLong
</li>
<li>RtlPtrdiffTToDWordLong
</li>
<li>RtlPtrdiffTToULong64
</li>
<li>RtlPtrdiffTToDWord64
</li>
<li>RtlPtrdiffTToUInt64
</li>
</ul>


