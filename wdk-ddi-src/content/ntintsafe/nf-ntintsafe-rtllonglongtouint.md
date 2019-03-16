---
UID: NF:ntintsafe.RtlLongLongToUInt
title: RtlLongLongToUInt function (ntintsafe.h)
description: Converts a value of type LONGLONG to a value of type UINT.
old-location: kernel\rtllonglongtouint.htm
tech.root: kernel
ms.assetid: 81B87CA6-01D8-4D54-87A6-6311260C06CB
ms.date: 04/30/2018
ms.keywords: RtlLongLongToUInt, RtlLongLongToUInt function [Kernel-Mode Driver Architecture], kernel.rtllonglongtouint, ntintsafe/RtlLongLongToUInt
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntintsafe.h
api_name:
- RtlLongLongToUInt
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlLongLongToUInt function


## -description


Converts a value of type <b>LONGLONG</b> to a value of type <b>UINT</b>.


## -parameters




### -param llOperand [in]

The value to be converted.


### -param puResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlIntPtrToUInt
</li>
<li>RtlLongPtrToUInt
</li>
<li>RtlLongLongToUInt32
</li>
<li>RtlLongLongToUIntPtr
</li>
<li>RtlLong64ToUInt
</li>
<li>RtlLong64ToUInt32
</li>
<li>RtlInt64ToUInt
</li>
<li>RtlInt64ToUInt32
</li>
<li>RtlLongLongToSizeT
</li>
<li>RtlLong64ToUIntPtr
</li>
<li>RtlLong64ToSizeT
</li>
<li>RtlInt64ToUIntPtr
</li>
<li>RtlInt64ToSizeT
</li>
</ul>


