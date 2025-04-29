---
UID: NF:wdm.RtlUnicodeStringToAnsiSize
title: RtlUnicodeStringToAnsiSize macro (wdm.h)
description: The RtlUnicodeStringToAnsiSize routine returns the number of bytes required for a null-terminated ANSI string that is equivalent to a specified Unicode string.
tech.root: kernel
ms.date: 04/28/2025
keywords: ["RtlUnicodeStringToAnsiSize macro"]
ms.keywords: RtlUnicodeStringToAnsiSize, RtlUnicodeStringToAnsiSize routine [Kernel-Mode Driver Architecture], k109_3a436ab4-80f1-4fb2-b4b6-98b4dc1ba1f1.xml, kernel.rtlunicodestringtoansisize, wdm/RtlUnicodeStringToAnsiSize
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlUnicodeStringToAnsiSize
 - wdm/RtlUnicodeStringToAnsiSize
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlUnicodeStringToAnsiSize
---

## -description

The **RtlUnicodeStringToAnsiSize**> routine returns the number of bytes required for a null-terminated ANSI string that is equivalent to a specified Unicode string.

## -parameters

### -param STRING [in]

Pointer to the Unicode string for which to compute the number of bytes required for an equivalent null-terminated ANSI string.

## -remarks

If the Unicode string can be translated into an ANSI string using the current system locale information, **RtlUnicodeStringToAnsiSize** returns the number of bytes required for an equivalent null-terminated ANSI string. Otherwise, **RtlUnicodeStringToAnsiSize** returns zero.

The Unicode string is interpreted for the current system locale.

**RtlUnicodeStringToAnsiSize** performs the same operation as [**RtlxUnicodeStringToAnsiSize**](nf-wdm-rtlxunicodestringtoansisize.md), but executes faster if the system does not use multibyte code pages.

## -see-also

[**RtlxUnicodeStringToAnsiSize**](nf-wdm-rtlxunicodestringtoansisize.md)
