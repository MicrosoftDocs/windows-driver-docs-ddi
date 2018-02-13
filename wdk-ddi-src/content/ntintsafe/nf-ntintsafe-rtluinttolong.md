---
UID: NF:ntintsafe.RtlUIntToLong
title: RtlUIntToLong function
author: windows-driver-content
description: Converts a value of type UINT to a value of type LONG.
old-location: kernel\rtluinttolong.htm
old-project: kernel
ms.assetid: 9C388D02-003B-4B0E-B2ED-E311AE750601
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.rtluinttolong, ntintsafe/RtlUIntToLong, RtlUIntToLong, RtlUIntToLong function [Kernel-Mode Driver Architecture]
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
-	RtlUIntToLong
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlUIntToLong function


## -description


Converts a value of type <b>UINT</b> to a value of type <b>LONG</b>.


## -syntax


````
NTSTATUS RtlUIntToLong(
  _In_  UINT uOperand,
  _Out_ LONG *plResult
);
````


## -parameters




### -param uOperand [in]

The value to be converted.


### -param plResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlUIntToLongPtr
</li>
<li>RtlUInt32ToLong
</li>
</ul>


