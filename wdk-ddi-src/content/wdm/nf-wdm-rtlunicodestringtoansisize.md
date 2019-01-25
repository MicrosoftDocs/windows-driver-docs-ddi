---
UID: NF:wdm.RtlUnicodeStringToAnsiSize
title: RtlUnicodeStringToAnsiSize macro (wdm.h)
description: The RtlUnicodeStringToAnsiSize routine returns the number of bytes required for a null-terminated ANSI string that is equivalent to a specified Unicode string.
old-location: kernel\rtlunicodestringtoansisize.htm
tech.root: kernel
ms.assetid: 4deaa42e-8c8b-461a-845e-424b543b52b1
ms.date: 04/30/2018
ms.keywords: RtlUnicodeStringToAnsiSize, RtlUnicodeStringToAnsiSize routine [Kernel-Mode Driver Architecture], k109_3a436ab4-80f1-4fb2-b4b6-98b4dc1ba1f1.xml, kernel.rtlunicodestringtoansisize, wdm/RtlUnicodeStringToAnsiSize
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlUnicodeStringToAnsiSize
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUnicodeStringToAnsiSize macro


## -description


The <b>RtlUnicodeStringToAnsiSize</b> routine returns the number of bytes required for a null-terminated ANSI string that is equivalent to a specified Unicode string.


## -parameters




### -param STRING [in]

Pointer to the Unicode string for which to compute the number of bytes required for an equivalent null-terminated ANSI string.

## -returns
If the Unicode string can be translated into an ANSI string using the current system locale information, [**RtlUnicodeStringToAnsiSize**](nf-wdm-rtlunicodestringtoansisize.md) returns the number of bytes required for an equivalent null-terminated ANSI string. Otherwise, [**RtlUnicodeStringToAnsiSize**](nf-wdm-rtlunicodestringtoansisize.md) returns zero.

## -remarks



The Unicode string is interpreted for the current system locale.

<b>RtlUnicodeStringToAnsiSize</b> performs the same operation as <a href="https://msdn.microsoft.com/library/windows/hardware/ff563605">RtlxUnicodeStringToAnsiSize</a>, but executes faster if the system does not use multibyte code pages.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563605">RtlxUnicodeStringToAnsiSize</a>
 

 

