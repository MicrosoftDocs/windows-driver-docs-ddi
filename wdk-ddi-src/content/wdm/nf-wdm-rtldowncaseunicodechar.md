---
UID: NF:wdm.RtlDowncaseUnicodeChar
title: RtlDowncaseUnicodeChar function (wdm.h)
description: The RtlDowncaseUnicodeChar routine converts the specified Unicode character to lowercase.
old-location: kernel\rtldowncaseunicodechar.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlDowncaseUnicodeChar function"]
ms.keywords: RtlDowncaseUnicodeChar, RtlDowncaseUnicodeChar routine [Kernel-Mode Driver Architecture], k109_e9ba1cee-5de9-4f8f-b964-6668ddef36b7.xml, kernel.rtldowncaseunicodechar, wdm/RtlDowncaseUnicodeChar
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
req.lib: Ntoskrnl.lib; Ntdll.lib
req.dll: Ntoskrnl.exe; Ntdll.dll
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlDowncaseUnicodeChar
 - wdm/RtlDowncaseUnicodeChar
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Ntoskrnl.exe
 - Ntdll.dll
api_name:
 - RtlDowncaseUnicodeChar
---

# RtlDowncaseUnicodeChar function


## -description

The <b>RtlDowncaseUnicodeChar</b> routine converts the specified Unicode character to lowercase.

## -parameters

### -param SourceCharacter 

[in]
Specifies the character to convert.

## -returns

<b>RtlDowncaseUnicodeChar</b> returns the lowercase value of the Unicode character.

## -remarks

Ntoskrnl.lib supports the <b>RtlDowncaseUnicodeChar</b> routine in the WDK for Windows 7 and later versions of Windows. Ntdll.dll exports the <b>RtlDowncaseUnicodeChar</b> entry point in Windows XP and later versions of Windows.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtldowncaseunicodestring">RtlDowncaseUnicodeString</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlupcaseunicodechar">RtlUpcaseUnicodeChar</a>
