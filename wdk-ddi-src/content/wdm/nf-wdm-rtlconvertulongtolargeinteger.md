---
UID: NF:wdm.RtlConvertUlongToLargeInteger
title: RtlConvertUlongToLargeInteger function
author: windows-driver-content
description: The RtlConvertUlongToLargeInteger routine converts the input unsigned integer to a signed large integer. For Windows XP and later versions of Windows, do not use this routine; use the native support for __int64.
old-location: kernel\rtlconvertulongtolargeinteger.htm
old-project: kernel
ms.assetid: 9e0b8d36-0191-4f78-91dd-874346a69072
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: RtlConvertUlongToLargeInteger, RtlConvertUlongToLargeInteger routine [Kernel-Mode Driver Architecture], k109_442eaa78-8765-4d40-a77d-8a511d18b754.xml, kernel.rtlconvertulongtolargeinteger, wdm/RtlConvertUlongToLargeInteger
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	RtlConvertUlongToLargeInteger
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlConvertUlongToLargeInteger function


## -description


The <b>RtlConvertUlongToLargeInteger</b> routine converts the input unsigned integer to a signed large integer. For Windows XP and later versions of Windows, do not use this routine; use the native support for <b>__int64</b>. 


## -parameters




### -param UnsignedInteger [in]

Specifies a value of type ULONG.


## -returns



<b>RtlConvertUlongToLargeInteger</b> returns the converted large integer. 



