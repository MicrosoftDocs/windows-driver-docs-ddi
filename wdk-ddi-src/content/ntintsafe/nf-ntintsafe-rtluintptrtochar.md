---
UID: NF:ntintsafe.RtlUIntPtrToChar
title: RtlUIntPtrToChar function
author: windows-driver-content
description: Converts a value of type UINT_PTR to a value of type CHAR.
old-location: kernel\rtluintptrtochar.htm
old-project: kernel
ms.assetid: 531A8110-FF91-4DE7-8FC5-305A2525DD40
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlUIntPtrToChar, RtlUIntPtrToChar function [Kernel-Mode Driver Architecture], kernel.rtluintptrtochar, ntintsafe/RtlUIntPtrToChar
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
-	RtlUIntPtrToChar
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlUIntPtrToChar function


## -description


Converts a value of type <b>UINT_PTR</b> to a value of type <b>CHAR</b>.


## -syntax


````
NTSTATUS RtlUIntPtrToChar(
  _In_  SHORT     sOperand,
  _Out_ ULONG_PTR *pulResult
);
````


## -parameters




### -param uOperand

TBD


### -param pch

TBD




#### - sOperand [in]

The value to be converted.


#### - pulResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlSizeTToChar
</li>
</ul>


