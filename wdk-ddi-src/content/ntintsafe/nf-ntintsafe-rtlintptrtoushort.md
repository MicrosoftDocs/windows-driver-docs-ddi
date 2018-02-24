---
UID: NF:ntintsafe.RtlIntPtrToUShort
title: RtlIntPtrToUShort function
author: windows-driver-content
description: Converts a value of type INT_PTR to a value of type USHORT.
old-location: kernel\rtlintptrtoushort.htm
old-project: kernel
ms.assetid: 7B563FDF-2535-40DD-9370-6607F3ED59F2
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlIntPtrToUShort function [Kernel-Mode Driver Architecture], ntintsafe/RtlIntPtrToUShort, kernel.rtlintptrtoushort, RtlIntPtrToUShort
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
-	RtlIntPtrToUShort
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlIntPtrToUShort function


## -description


Converts a value of type <b>INT_PTR</b> to a value of type <b>USHORT</b>.


## -syntax


````
NTSTATUS RtlIntPtrToUShort(
  _In_  INT_PTR iOperand,
  _Out_ USHORT  *pusResult
);
````


## -parameters




### -param iOperand [in]

The value to be converted.


### -param pusResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlIntPtrToUInt16
</li>
<li>RtlIntPtrToWord
</li>
<li>RtlPtrdiffTToUShort
</li>
<li>RtlPtrdiffTToUInt16
</li>
<li>RtlPtrdiffTToWord
</li>
</ul>


