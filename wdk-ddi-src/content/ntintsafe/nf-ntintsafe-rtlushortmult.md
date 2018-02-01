---
UID: NF:ntintsafe.RtlUShortMult
title: RtlUShortMult function
author: windows-driver-content
description: Multiplies one value of type USHORT by another.
old-location: kernel\rtlushortmult.htm
old-project: kernel
ms.assetid: 1727AD96-FC0B-4B52-92C5-5E7502433021
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlUShortMult, kernel.rtlushortmult, ntintsafe/RtlUShortMult, RtlUShortMult function [Kernel-Mode Driver Architecture]
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntintsafe.h
apiname:
-	RtlUShortMult
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlUShortMult function


## -description


Multiplies one value of type <b>USHORT</b> by another.


## -syntax


````
NTSTATUS RtlUShortMult(
  _In_  USHORT usMultiplicand,
  _In_  USHORT usMultiplier,
  _Out_ USHORT *pusResult
);
````


## -parameters




### -param usMultiplicand [in]

The value to be multiplied by <i>usMultiplier</i>.


### -param usMultiplier [in]

The value by which to multiply <i>usMultiplicand</i>.


### -param pusResult [out]

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks


This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.


