---
UID: NF:wdm.RtlConvertUlongToLargeInteger
title: RtlConvertUlongToLargeInteger function (wdm.h)
description: The RtlConvertUlongToLargeInteger routine converts the input unsigned integer to a signed large integer. For Windows XP and later versions of Windows, do not use this routine; use the native support for __int64.
old-location: kernel\rtlconvertulongtolargeinteger.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlConvertUlongToLargeInteger function"]
ms.keywords: RtlConvertUlongToLargeInteger, RtlConvertUlongToLargeInteger routine [Kernel-Mode Driver Architecture], k109_442eaa78-8765-4d40-a77d-8a511d18b754.xml, kernel.rtlconvertulongtolargeinteger, wdm/RtlConvertUlongToLargeInteger
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlConvertUlongToLargeInteger
 - wdm/RtlConvertUlongToLargeInteger
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlConvertUlongToLargeInteger
---

# RtlConvertUlongToLargeInteger function


## -description

The <b>RtlConvertUlongToLargeInteger</b> routine converts the input unsigned integer to a signed large integer. For Windows XP and later versions of Windows, do not use this routine; use the native support for <b>__int64</b>.

## -parameters

### -param UnsignedInteger [in]


Specifies a value of type ULONG.

## -returns

<b>RtlConvertUlongToLargeInteger</b> returns the converted large integer.

