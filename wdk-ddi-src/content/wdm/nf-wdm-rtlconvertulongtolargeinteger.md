---
UID: NF:wdm.RtlConvertUlongToLargeInteger
title: RtlConvertUlongToLargeInteger function
author: windows-driver-content
description: The RtlConvertUlongToLargeInteger routine converts the input unsigned integer to a signed large integer. For Windows XP and later versions of Windows, do not use this routine; use the native support for __int64.
old-location: kernel\rtlconvertulongtolargeinteger.htm
old-project: kernel
ms.assetid: 9e0b8d36-0191-4f78-91dd-874346a69072
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlConvertUlongToLargeInteger
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
req.alt-api: RtlConvertUlongToLargeInteger
req.alt-loc: NtosKrnl.exe
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlConvertUlongToLargeInteger function



## -description
The <b>RtlConvertUlongToLargeInteger</b> routine converts the input unsigned integer to a signed large integer. For Windows XP and later versions of Windows, do not use this routine; use the native support for <b>__int64</b>. 



## -syntax

````
LARGE_INTEGER RtlConvertUlongToLargeInteger(
  _In_ ULONG UnsignedInteger
);
````


## -parameters

### -param UnsignedInteger [in]

Specifies a value of type ULONG.


## -returns
<b>RtlConvertUlongToLargeInteger</b> returns the converted large integer. 


## -remarks
