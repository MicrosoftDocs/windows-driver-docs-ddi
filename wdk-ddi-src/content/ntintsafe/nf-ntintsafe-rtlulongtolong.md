---
UID: NF:ntintsafe.RtlULongToLong
title: RtlULongToLong function (ntintsafe.h)
description: Converts a value of type ULONG to a value of type LONG.
old-location: kernel\rtlulongtolong.htm
tech.root: kernel
ms.assetid: EA30B409-8953-488B-A8AB-84A3FBED1A20
ms.date: 04/30/2018
keywords: ["RtlULongToLong function"]
ms.keywords: RtlULongToLong, RtlULongToLong function [Kernel-Mode Driver Architecture], kernel.rtlulongtolong, ntintsafe/RtlULongToLong
f1_keywords:
 - "ntintsafe/RtlULongToLong"
 - "RtlULongToLong"
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
- RtlULongToLong
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlULongToLong function


## -description


Converts a value of type <b>ULONG</b> to a value of type <b>LONG</b>.


## -parameters




### -param ulOperand [in]

The value to be converted.


### -param plResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



