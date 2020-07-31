---
UID: NF:wdm.RtlxUnicodeStringToAnsiSize
title: RtlxUnicodeStringToAnsiSize function (wdm.h)
description: The RtlxUnicodeStringToAnsiSize routine returns the number of bytes required for a null-terminated ANSI string that is equivalent to a specified Unicode string.
old-location: kernel\rtlxunicodestringtoansisize.htm
tech.root: kernel
ms.assetid: dff228e5-14ea-4ec0-a7f1-247137f9e70d
ms.date: 04/30/2018
keywords: ["RtlxUnicodeStringToAnsiSize function"]
ms.keywords: RtlxUnicodeStringToAnsiSize, RtlxUnicodeStringToAnsiSize routine [Kernel-Mode Driver Architecture], k109_f7d1f632-4350-4fb9-ac05-3c36c0d0446e.xml, kernel.rtlxunicodestringtoansisize, wdm/RtlxUnicodeStringToAnsiSize
f1_keywords:
 - "wdm/RtlxUnicodeStringToAnsiSize"
 - "RtlxUnicodeStringToAnsiSize"
req.header: wdm.h
req.include-header: Wdm.h
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlxUnicodeStringToAnsiSize
targetos: Windows
req.typenames: 
---

# RtlxUnicodeStringToAnsiSize function


## -description


The <b>RtlxUnicodeStringToAnsiSize</b> routine returns the number of bytes required for a null-terminated ANSI string that is equivalent to a specified Unicode string.


## -parameters




### -param UnicodeString [in]

Pointer to the Unicode string for which to compute the number of bytes required for an equivalent null-terminated ANSI string. 


## -returns



If the Unicode string can be translated into an ANSI string using the current system locale information, <b>RtlxUnicodeStringToAnsiSize</b> returns the number of bytes required for an equivalent null-terminated ANSI string. Otherwise, it returns zero.




## -remarks



The Unicode string is interpreted for the current system locale. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlunicodestringtoansisize">RtlUnicodeStringToAnsiSize</a>
 

 

