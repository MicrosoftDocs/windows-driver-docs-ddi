---
UID: NF:ntintsafe.RtlLongLongToULongLong
title: RtlLongLongToULongLong function (ntintsafe.h)
description: Converts a value of type LONGLONG to a value of type LONGLONG.
old-location: kernel\rtllonglongtoulonglong.htm
tech.root: kernel
ms.assetid: AE273E51-FEB5-4470-AB19-0F55A2F8EFFD
ms.date: 04/30/2018
keywords: ["RtlLongLongToULongLong function"]
ms.keywords: RtlLongLongToULongLong, RtlLongLongToULongLong function [Kernel-Mode Driver Architecture], kernel.rtllonglongtoulonglong, ntintsafe/RtlLongLongToULongLong
f1_keywords:
 - "ntintsafe/RtlLongLongToULongLong"
 - "RtlLongLongToULongLong"
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
- RtlLongLongToULongLong
targetos: Windows
req.typenames: 
---

# RtlLongLongToULongLong function


## -description


Converts a value of type <b>LONGLONG</b> to a value of type <b>LONGLONG</b>.


## -parameters




### -param llOperand 
[in]
The value to be converted.


### -param pullResult 
[out]
A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlIntPtrToUIntPtr
</li>
<li>RtlIntPtrToULongPtr
</li>
<li>RtlIntPtrToULongLong
</li>
<li>RtlLongLongToUIntPtr
</li>
<li>RtlLongLongToULongPtr
</li>
<li>RtlLongLongToDWordLong
</li>
<li>RtlLongLongToULong64
</li>
<li>RtlLongLongToDWord64
</li>
<li>RtlLongLongToUInt64
</li>
<li>RtlLong64ToULongLong
</li>
<li>RtlInt64ToULongLong
</li>
<li>RtlInt64ToDWordLong
</li>
<li>RtlInt64ToULong64
</li>
<li>RtlInt64ToDWord64
</li>
<li>RtlInt64ToUInt64

</li>
</ul>


