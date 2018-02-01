---
UID: NF:ntintsafe.RtlLongToUInt
title: RtlLongToUInt function
author: windows-driver-content
description: Converts a value of type LONG to a value of type UINT.
old-location: kernel\rtllongtouint.htm
old-project: kernel
ms.assetid: 8347581C-91CB-4C53-91C5-9560CC88A4B8
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ntintsafe/RtlLongToUInt, RtlLongToUInt, kernel.rtllongtouint, RtlLongToUInt function [Kernel-Mode Driver Architecture]
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
-	RtlLongToUInt
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlLongToUInt function


## -description


Converts a value of type <b>LONG</b> to a value of type <b>UINT</b>.


## -syntax


````
NTSTATUS RtlLongToUInt(
  _In_  LONG lOperand,
  _Out_ UINT *puResult
);
````


## -parameters




### -param lOperand [in]

The value to be converted.


### -param puResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks


This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:
<ul>
<li>RtlLongToUInt32
</li>
<li>RtlLongToUIntPtr
</li>
</ul>

