---
UID: NF:ntintsafe.RtlUInt8Sub
title: RtlUInt8Sub function (ntintsafe.h)
description: The RtlUInt8Sub routine subtracts one value of type UINT8 from another.
old-location: kernel\rtluint8sub.htm
tech.root: kernel
ms.assetid: D8BD24AA-64CF-42CB-8AD2-2B6C77D4B195
ms.date: 04/30/2018
keywords: ["RtlUInt8Sub function"]
ms.keywords: RtlUInt8Sub, RtlUInt8Sub function [Kernel-Mode Driver Architecture], kernel.rtluint8sub, ntintsafe/RtlUInt8Sub
f1_keywords:
 - "ntintsafe/RtlUInt8Sub"
 - "RtlUInt8Sub"
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
- RtlUInt8Sub
targetos: Windows
req.typenames: 
---

# RtlUInt8Sub function


## -description


The <b>RtlUInt8Sub</b> routine subtracts one value of type <b>UINT8</b> from another.


## -parameters




### -param u8Minuend 
[in]
The value from which <i>u8Subtrahend</i> is subtracted.


### -param u8Subtrahend 
[in]
The value to subtract from <i>u8Minuend</i>.


### -param pu8Result 
[out]
A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -returns



<b>RtlUInt8Sub</b> returns STATUS_SUCCESS if the routine is successful. Possible error return values include the following status code.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INTEGER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
An arithmetic overflow occurred.

</td>
</tr>
</table>
 




## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.



