---
UID: NF:ntintsafe.RtlLongLongToUChar
title: RtlLongLongToUChar function
author: windows-driver-content
description: Converts a value of type LONGLONG to a value of type UCHAR.
old-location: kernel\rtllonglongtouchar.htm
old-project: kernel
ms.assetid: 58380931-F16E-478D-8C1B-690CF90C4BD0
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.rtllonglongtouchar, ntintsafe/RtlLongLongToUChar, RtlLongLongToUChar, RtlLongLongToUChar function [Kernel-Mode Driver Architecture]
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
-	RtlLongLongToUChar
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlLongLongToUChar function


## -description


Converts a value of type <b>LONGLONG</b> to a value of type <b>UCHAR</b>.


## -syntax


````
NTSTATUS RtlLongLongToUChar(
  _In_  LONGLONG llOperand,
  _Out_ UCHAR    *pch
);
````


## -parameters




### -param llOperand [in]

The value to be converted.


### -param pch [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks


This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:
<ul>
<li>
RtlLong64ToUChar
</li>
<li>RtlInt64ToUChar
</li>
</ul>

