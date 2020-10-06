---
UID: NF:ntintsafe.RtlShortToUInt8
title: RtlShortToUInt8 function (ntintsafe.h)
description: Converts a value of type SHORT to a value of type UINT8.
old-location: kernel\rtlshorttouint8.htm
tech.root: kernel
ms.assetid: B1B5AE37-23BC-444A-9014-529BAD50ED52
ms.date: 04/30/2018
keywords: ["RtlShortToUInt8 function"]
ms.keywords: RtlShortToUInt8, RtlShortToUInt8 function [Kernel-Mode Driver Architecture], kernel.rtlshorttouint8, ntintsafe/RtlShortToUInt8
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
 - RtlShortToUInt8
 - ntintsafe/RtlShortToUInt8
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlShortToUInt8
---

# RtlShortToUInt8 function


## -description

Converts a value of type <b>SHORT</b> to a value of type <b>UINT8</b>.

## -parameters

### -param sOperand 

[in]
The value to be converted.

### -param pui8Result

<p>A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.</p>

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlShortToByte
</li>
<li>RtlInt16ToUInt8
</li>
<li>RtlInt16ToByte
</li>
</ul>

