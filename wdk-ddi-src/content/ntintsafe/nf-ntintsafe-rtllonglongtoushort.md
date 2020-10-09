---
UID: NF:ntintsafe.RtlLongLongToUShort
title: RtlLongLongToUShort function (ntintsafe.h)
description: Converts a value of type LONGLONG to a value of type USHORT.
old-location: kernel\rtllonglongtoushort.htm
tech.root: kernel
ms.assetid: 68D3A830-6687-4D45-8C9B-FC7B5E1F318A
ms.date: 04/30/2018
keywords: ["RtlLongLongToUShort function"]
ms.keywords: RtlLongLongToUShort, RtlLongLongToUShort function [Kernel-Mode Driver Architecture], kernel.rtllonglongtoushort, ntintsafe/RtlLongLongToUShort
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlLongLongToUShort
 - ntintsafe/RtlLongLongToUShort
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlLongLongToUShort
---

# RtlLongLongToUShort function


## -description

Converts a value of type <b>LONGLONG</b> to a value of type <b>USHORT</b>.

## -parameters

### -param llOperand 

[in]
The value to be converted.

### -param pusResult 

[out]
A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>
RtlLongLongToUInt16
</li>
<li>RtlLongLongToWord
</li>
<li>RtlLong64ToUShort
</li>
<li>RtlLong64ToUInt16
</li>
<li>RtlLong64ToWord
</li>
<li>RtlInt64ToUShort
</li>
<li>RtlInt64ToUInt16
</li>
<li>RtlInt64ToWord
</li>
</ul>

