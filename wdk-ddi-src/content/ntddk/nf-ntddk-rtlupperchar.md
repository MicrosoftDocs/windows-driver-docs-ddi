---
UID: NF:ntddk.RtlUpperChar
title: RtlUpperChar function (ntddk.h)
description: The RtlUpperChar routine converts the specified character to uppercase.
old-location: kernel\rtlupperchar.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlUpperChar function"]
ms.keywords: RtlUpperChar, RtlUpperChar routine [Kernel-Mode Driver Architecture], k109_c1a13e9a-f863-4bcd-ae89-daee0c3d3a4b.xml, kernel.rtlupperchar, ntddk/RtlUpperChar
req.header: ntddk.h
req.include-header: Ntddk.h
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
req.irql: <=APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlUpperChar
 - ntddk/RtlUpperChar
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlUpperChar
---

# RtlUpperChar function


## -description

The <b>RtlUpperChar</b> routine converts the specified character to uppercase.

## -parameters

### -param Character 

[in]
Specifies the character to convert.

## -returns

<b>RtlUpperChar</b> returns the uppercase version of the specified character or returns the value specified by the caller for <i>Character</i> if the specified character cannot be converted.

## -remarks

<b>RtlUpperChar</b> returns the input <i>Character</i> unconverted if it is the lead byte of a multibyte character or if the uppercase equivalent of <i>Character</i> is a double-byte character. To convert such characters, use <b>RtlUpcaseUnicodeChar</b>. 

**RtlUpperChar** is not recommended because the function is designed to work for ASCII range A-Z letters. Instead, use [**RtlUpcaseUnicodeChar**](../wdm/nf-wdm-rtlupcaseunicodechar.md).

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlupcaseunicodechar">RtlUpcaseUnicodeChar</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlupperstring">RtlUpperString</a>
