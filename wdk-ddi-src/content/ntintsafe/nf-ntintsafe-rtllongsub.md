---
UID: NF:ntintsafe.RtlLongSub
title: RtlLongSub function (ntintsafe.h)
description: Subtracts one value of type LONG from another.
old-location: kernel\rtllongsub.htm
tech.root: kernel
ms.assetid: 5D98737C-0986-4DCB-9270-A0DF76CFCB5C
ms.date: 04/30/2018
keywords: ["RtlLongSub function"]
ms.keywords: RtlLongSub, RtlLongSub function [Kernel-Mode Driver Architecture], kernel.rtllongsub, ntintsafe/RtlLongSub
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
 - RtlLongSub
 - ntintsafe/RtlLongSub
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlLongSub
---

# RtlLongSub function


## -description

Subtracts one value of type <b>LONG</b> from another.

## -parameters

### -param lMinuend 

[in]
The value from which <i>lSubtrahend</i> is subtracted.

### -param lSubtrahend 

[in]
The value to subtract from <i>lMinuend</i>.

### -param plResult 

[out]
A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

