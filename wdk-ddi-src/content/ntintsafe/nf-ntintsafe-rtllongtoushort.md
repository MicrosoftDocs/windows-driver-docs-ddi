---
UID: NF:ntintsafe.RtlLongToUShort
title: RtlLongToUShort function
author: windows-driver-content
description: Converts a value of type LONG to a value of type USHORT.
old-location: kernel\rtllongtoushort.htm
old-project: kernel
ms.assetid: A6D3E5D2-EB53-4F1D-B4E4-9E2D8D845E80
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.rtllongtoushort, RtlLongToUShort function [Kernel-Mode Driver Architecture], ntintsafe/RtlLongToUShort, RtlLongToUShort
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
-	RtlLongToUShort
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlLongToUShort function


## -description


Converts a value of type <b>LONG</b> to a value of type <b>USHORT</b>.


## -syntax


````
NTSTATUS RtlLongToUShort(
  _In_  LONG   lOperand,
  _Out_ USHORT *pusResult
);
````


## -parameters




### -param lOperand [in]

The value to be converted.


### -param pusResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlLongToUInt16
</li>
<li>RtlLongToWord
</li>
</ul>


