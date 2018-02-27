---
UID: NF:ntintsafe.RtlLongPtrSub
title: RtlLongPtrSub function
author: windows-driver-content
description: Subtracts one value of type LONG_PTR from another.
old-location: kernel\rtllongptrsub.htm
old-project: kernel
ms.assetid: 3F95CA04-3CE1-4298-B3B6-5D111AB4F3D3
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: RtlLongPtrSub, RtlLongPtrSub function [Kernel-Mode Driver Architecture], kernel.rtllongptrsub, ntintsafe/RtlLongPtrSub
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
-	RtlLongPtrSub
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlLongPtrSub function


## -description


Subtracts one value of type <b>LONG_PTR</b> from another.


## -syntax


````
NTSTATUS RtlLongPtrSub(
  _In_  LONG_PTR lMinuend,
  _In_  LONG_PTR lSubtrahend,
  _Out_ LONG_PTR *plResult
);
````


## -parameters




### -param lMinuend [in]

The value from which <i>lSubtrahend</i> is subtracted.


### -param lSubtrahend [in]

The value to subtract from <i>lMinuend</i>.


### -param plResult [out]

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.



