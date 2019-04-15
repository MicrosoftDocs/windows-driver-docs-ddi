---
UID: NF:ntintsafe.RtlInt8Sub
title: RtlInt8Sub function (ntintsafe.h)
description: Subtracts one value of type INT8 from another.
old-location: kernel\rtlint8sub.htm
tech.root: kernel
ms.assetid: 3648668C-65CD-45F9-80E0-490AE2FE405E
ms.date: 04/30/2018
ms.keywords: RtlInt8Sub, RtlInt8Sub function [Kernel-Mode Driver Architecture], kernel.rtlint8sub, ntintsafe/RtlInt8Sub
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
- RtlInt8Sub
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlInt8Sub function


## -description


Subtracts one value of type <b>INT8</b> from another.


## -parameters




### -param i8Minuend [in]

The value from which <i>i8Subtrahend</i> is subtracted.


### -param i8Subtrahend [in]

The value to subtract from <i>i8Minuend</i>.


### -param pi8Result [out]

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.



