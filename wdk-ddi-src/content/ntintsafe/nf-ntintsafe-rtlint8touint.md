---
UID: NF:ntintsafe.RtlInt8ToUInt
title: RtlInt8ToUInt function
author: windows-driver-content
description: Converts a value of type INT8 to a value of type UINT.
old-location: kernel\rtlint8touint.htm
old-project: kernel
ms.assetid: 00C37CB5-4CBC-48C3-8D90-F01BF82E2EF6
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.rtlint8touint, ntintsafe/RtlInt8ToUInt, RtlInt8ToUInt, RtlInt8ToUInt function [Kernel-Mode Driver Architecture]
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
-	RtlInt8ToUInt
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlInt8ToUInt function


## -description


Converts a value of type <b>INT8</b> to a value of type <b>UINT</b>.


## -syntax


````
NTSTATUS RtlInt8ToUInt(
  _In_  INT8 i8Operand,
  _Out_ UINT *puResult
);
````


## -parameters




### -param i8Operand [in]

The value to be converted.


### -param puResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlInt8ToUInt32
</li>
</ul>


