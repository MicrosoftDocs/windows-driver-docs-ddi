---
UID: NF:ntintsafe.RtlLongAdd
title: RtlLongAdd function
author: windows-driver-content
description: Adds two values of type LONG.
old-location: kernel\rtllongadd.htm
old-project: kernel
ms.assetid: E8CF5E74-2EDA-4B27-A9C0-053930FF741D
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlLongAdd, RtlLongAdd function [Kernel-Mode Driver Architecture], kernel.rtllongadd, ntintsafe/RtlLongAdd
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
-	RtlLongAdd
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlLongAdd function


## -description


Adds two values of type <b>LONG</b>.


## -parameters




### -param lAugend [in]

The first value in the equation.


### -param lAddend [in]

The value to add to <i>lAugend</i>.


### -param plResult [out]

A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.



