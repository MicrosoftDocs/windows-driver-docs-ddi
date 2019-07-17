---
UID: NF:ntintsafe.RtlUInt8Add
title: RtlUInt8Add function (ntintsafe.h)
description: Adds two values of type UINT8.
old-location: kernel\rtluint8add.htm
tech.root: kernel
ms.assetid: E93C8C7A-13E5-4089-931C-C56055FA3C90
ms.date: 04/30/2018
ms.keywords: RtlUInt8Add, RtlUInt8Add function [Kernel-Mode Driver Architecture], kernel.rtluint8add, ntintsafe/RtlUInt8Add
ms.topic: function
f1_keywords:
 - "ntintsafe/RtlUInt8Add"
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
- RtlUInt8Add
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUInt8Add function


## -description


Adds two values of type <b>UINT8</b>.


## -parameters




### -param u8Augend [in]

The first value in the equation.


### -param u8Addend [in]

The value to add to <i>u8Augend</i>.


### -param pu8Result [out]

A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.



