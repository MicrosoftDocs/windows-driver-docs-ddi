---
UID: NF:ntintsafe.RtlShortToULongPtr
title: RtlShortToULongPtr function
author: windows-driver-content
description: Converts a value of type SHORT to a value of type ULONG_PTR.
old-location: kernel\rtlshorttoulongptr.htm
old-project: kernel
ms.assetid: 0C279063-D5B1-4C82-8C0A-2B39E831BFB3
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: RtlShortToULongPtr, RtlShortToULongPtr function [Kernel-Mode Driver Architecture], kernel.rtlshorttoulongptr, ntintsafe/RtlShortToULongPtr
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntintsafe.h
api_name:
-	RtlShortToULongPtr
product: Windows
targetos: Windows
req.typenames: 
---

# RtlShortToULongPtr function


## -description


Converts a value of type <b>SHORT</b> to a value of type <b>ULONG_PTR</b>.


## -parameters




### -param sOperand [in]

The value to be converted.


### -param pulResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>
RtlLongLongToDWordPtr
</li>
<li>RtlLongLongToSIZET
</li>
<li>RtlLong64ToULongPtr
</li>
<li>RtlLong64ToDWordPtr
</li>
<li>RtlLong64ToSIZET
</li>
<li>RtlInt64ToULongPtr
</li>
<li>RtlInt64ToDWordPtr
</li>
<li>RtlInt64ToSIZET
</li>
<li>RtlShortToSIZET
</li>
<li>RtlInt16ToULongPtr
</li>
<li>RtlInt16ToDWordPtr
</li>
<li>RtlInt16ToSIZET
</li>
</ul>


