---
UID: NF:ntintsafe.RtlInt8ToUInt8
title: RtlInt8ToUInt8 function (ntintsafe.h)
description: Converts a value of type INT8 to a value of type UINT8.
old-location: kernel\rtlint8touint8.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlInt8ToUInt8 function"]
ms.keywords: RtlInt8ToUInt8, RtlInt8ToUInt8 function [Kernel-Mode Driver Architecture], kernel.rtlint8touint8, ntintsafe/RtlInt8ToUInt8
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
 - RtlInt8ToUInt8
 - ntintsafe/RtlInt8ToUInt8
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntintsafe.h
api_name:
 - RtlInt8ToUInt8
---

# RtlInt8ToUInt8 function


## -description

Converts a value of type <b>INT8</b> to a value of type <b>UINT8</b>.

## -parameters

### -param i8Operand [in]


The value to be converted.

### -param pu8Result [out]


A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlInt8ToByte</li>
</ul>

