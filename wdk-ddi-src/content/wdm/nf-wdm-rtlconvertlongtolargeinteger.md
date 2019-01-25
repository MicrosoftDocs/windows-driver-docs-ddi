---
UID: NF:wdm.RtlConvertLongToLargeInteger
title: RtlConvertLongToLargeInteger function (wdm.h)
description: The RtlConvertLongToLargeInteger routine converts the input signed integer to a signed large integer.
old-location: kernel\rtlconvertlongtolargeinteger.htm
tech.root: kernel
ms.assetid: 8c1f6cd3-f54b-4104-bd14-63d2c284946c
ms.date: 04/30/2018
ms.keywords: RtlConvertLongToLargeInteger, RtlConvertLongToLargeInteger routine [Kernel-Mode Driver Architecture], k109_f56a300b-e5d3-4f08-8d38-f124f73ada9f.xml, kernel.rtlconvertlongtolargeinteger, wdm/RtlConvertLongToLargeInteger
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlConvertLongToLargeInteger
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlConvertLongToLargeInteger function


## -description


The <b>RtlConvertLongToLargeInteger</b> routine converts the input signed integer to a signed large integer.


## -parameters




### -param SignedInteger [in]

Specifies an integer of type LONG.


## -returns



<b>RtlConvertLongToLargeInteger</b> returns the large integer result.




## -remarks



This routine is not supported in Windows XP. Use native support for <b>__int64</b> instead. 



