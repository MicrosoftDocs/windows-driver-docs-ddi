---
UID: NF:wdm.RtlAnsiStringToUnicodeSize
title: RtlAnsiStringToUnicodeSize macro (wdm.h)
description: The RtlAnsiStringToUnicodeSize routine returns the number of bytes required to hold an ANSI string converted into a Unicode string.
old-location: kernel\rtlansistringtounicodesize.htm
tech.root: kernel
ms.assetid: 32687aa7-4e14-40cb-baa3-4a97d834bf86
ms.date: 04/30/2018
ms.keywords: RtlAnsiStringToUnicodeSize, RtlAnsiStringToUnicodeSize routine [Kernel-Mode Driver Architecture], k109_90cc45c4-2e5b-4f11-823d-5dbc52017e15.xml, kernel.rtlansistringtounicodesize, wdm/RtlAnsiStringToUnicodeSize
f1_keywords:
 - "wdm/RtlAnsiStringToUnicodeSize"
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlAnsiStringToUnicodeSize
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlAnsiStringToUnicodeSize macro


## -description


The <b>RtlAnsiStringToUnicodeSize</b> routine returns the number of bytes required to hold an ANSI string converted into a Unicode string. 


## -parameters




### -param STRING [in]

Pointer to a buffer containing the ANSI string.


## -remarks

**RtlAnsiStringToUnicodeSize** returns the necessary size in bytes for a Unicode string buffer.

Casting the return value of the <b>RtlAnsiStringToUnicodeSize</b> routine to USHORT might cause a loss of data. To avoid potential problems, callers of this routine should test the return value for arithmetic overflow. Note that <b>RtlAnsiStringToUnicodeSize</b> accounts for the trailing <b>NULL</b>.</div>

Callers of <b>RtlAnsiStringToUnicodeSize</b> must be running at IRQL = PASSIVE_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlansistringtounicodestring">RtlAnsiStringToUnicodeString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlxansistringtounicodesize">RtlxAnsiStringToUnicodeSize</a>
 

 

