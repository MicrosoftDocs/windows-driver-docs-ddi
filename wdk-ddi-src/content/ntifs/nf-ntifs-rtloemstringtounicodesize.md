---
UID: NF:ntifs.RtlOemStringToUnicodeSize
title: RtlOemStringToUnicodeSize macro (ntifs.h)
description: The RtlOemStringToUnicodeSize routine determines the size, in bytes, that a given OEM string will be after it is translated into a null-terminated Unicode string.
old-location: ifsk\rtloemstringtounicodesize.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["RtlOemStringToUnicodeSize macro"]
ms.keywords: RtlOemStringToUnicodeSize, RtlOemStringToUnicodeSize routine [Installable File System Drivers], ifsk.rtloemstringtounicodesize, ntifs/RtlOemStringToUnicodeSize, rtlref_5f048569-d84e-43ee-8d51-1281f18c7ddf.xml
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
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
req.irql: < DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlOemStringToUnicodeSize
 - ntifs/RtlOemStringToUnicodeSize
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlOemStringToUnicodeSize
---

# RtlOemStringToUnicodeSize macro


## -description

The <b>RtlOemStringToUnicodeSize</b> routine determines the size, in bytes, that a given OEM string will be after it is translated into a null-terminated Unicode string.

## -parameters

### -param STRING

<p>Pointer to a caller-allocated OEM string. </p>

## -remarks

<b>RtlOemStringToUnicodeSize</b> can be called to determine how much memory to allocate when translating an OEM string to Unicode with <b>RtlOemStringToUnicodeString</b>. The returned value includes space for the NULL terminator. 

For information about other string-handling routines, see <a href="/windows-hardware/drivers/ddi/_kernel/#run-time-library-rtl-routines">Run-Time Library (RTL) Routines</a>.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/ff558741(v=vs.85)">OEM_STRING</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtloemstringtocountedunicodesize">RtlOemStringToCountedUnicodeSize</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtloemstringtounicodestring">RtlOemStringToUnicodeString</a>
