---
UID: NF:ntintsafe.RtlLongToUChar
title: RtlLongToUChar function (ntintsafe.h)
description: Converts a value of type LONG to a value of type UCHAR.
old-location: kernel\rtllongtouchar.htm
tech.root: kernel
ms.assetid: 22440E1D-8DF5-4391-90F4-6080AAAC65D1
ms.date: 04/30/2018
ms.keywords: RtlLongToUChar, RtlLongToUChar function [Kernel-Mode Driver Architecture], kernel.rtllongtouchar, ntintsafe/RtlLongToUChar
ms.topic: function
f1_keywords:
 - "ntintsafe/RtlLongToUChar"
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
- RtlLongToUChar
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlLongToUChar function


## -description


Converts a value of type <b>LONG</b> to a value of type <b>UCHAR</b>.


## -parameters




### -param lOperand [in]

The value to be converted.


### -param pch [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



