---
UID: NF:ntintsafe.RtlShortAdd
title: RtlShortAdd function (ntintsafe.h)
description: Adds two values of type SHORT.
old-location: kernel\rtlshortadd.htm
tech.root: kernel
ms.assetid: 6CCBDECB-D52A-409D-91CA-6635E6D02545
ms.date: 04/30/2018
keywords: ["RtlShortAdd function"]
ms.keywords: RtlShortAdd, RtlShortAdd function [Kernel-Mode Driver Architecture], kernel.rtlshortadd, ntintsafe/RtlShortAdd
f1_keywords:
 - "ntintsafe/RtlShortAdd"
 - "RtlShortAdd"
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
- RtlShortAdd
targetos: Windows
req.typenames: 
---

# RtlShortAdd function


## -description


Adds two values of type <b>SHORT</b>.


## -parameters




### -param sAugend [in]

The first value in the equation.


### -param sAddend [in]

The value to add to <i>sAugend</i>.


### -param psResult [out]

A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlInt16Add
</li>
</ul>


