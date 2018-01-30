---
UID: NF:ntintsafe.RtlLongToULong
title: RtlLongToULong function
author: windows-driver-content
description: Converts a value of type LONG to a value of type ULONG.
old-location: kernel\rtllongtoulong.htm
old-project: kernel
ms.assetid: FD0BD380-6DC2-4C4F-BE7B-42731082EB5C
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlLongToULong, RtlLongToULong function [Kernel-Mode Driver Architecture], ntintsafe/RtlLongToULong, kernel.rtllongtoulong
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
-	RtlLongToULong
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlLongToULong function


## -description


Converts a value of type <b>LONG</b> to a value of type <b>ULONG</b>.


## -syntax


````
NTSTATUS RtlLongToULong(
  _In_  LONG  lOperand,
  _Out_ ULONG *pulResult
);
````


## -parameters




### -param lOperand [in]

The value to be converted.


### -param pulResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks


This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:
<ul>
<li>RtlLongToULongPtr
</li>
<li>RtlLongToDWord
</li>
</ul>

