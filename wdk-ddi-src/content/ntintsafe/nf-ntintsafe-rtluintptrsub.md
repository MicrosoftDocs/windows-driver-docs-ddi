---
UID: NF:ntintsafe.RtlUIntPtrSub
title: RtlUIntPtrSub function (ntintsafe.h)
description: Subtracts one value of type UINT_PTR from another.
old-location: kernel\rtluintptrsub.htm
tech.root: kernel
ms.assetid: D0E23A94-515B-4225-A8AC-390CDD3BEA60
ms.date: 04/30/2018
ms.keywords: RtlUIntPtrSub, RtlUIntPtrSub function [Kernel-Mode Driver Architecture], kernel.rtluintptrsub, ntintsafe/RtlUIntPtrSub
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
- RtlUIntPtrSub
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUIntPtrSub function


## -description


Subtracts one value of type <b>UINT_PTR</b> from another.


## -parameters




### -param uMinuend [in]

The value from which <i>uSubtrahend</i> is subtracted.


### -param uSubtrahend [in]

The value to subtract from <i>uMinuend</i>.


### -param puResult [out]

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlUIntPtrSub
</li>
<li>RtlULongPtrSub
</li>
<li>RtlDWordPtrSub
</li>
<li>RtlSIZETSub
</li>
<li>RtlDWordLongSub
</li>
<li>RtlULong64Sub
</li>
<li>RtlDWord64Sub
</li>
<li>RtlUInt64Sub
</li>
</ul>


