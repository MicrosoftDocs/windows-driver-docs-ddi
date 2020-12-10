---
UID: NF:ntifs.RtlUnicodeToMultiByteSize
title: RtlUnicodeToMultiByteSize function (ntifs.h)
description: The RtlUnicodeToMultiByteSize routine determines the number of bytes that are required to store the multibyte translation for the specified Unicode string. The translation is assumed to use the current system ANSI code page (ACP).
old-location: ifsk\rtlunicodetomultibytesize.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["RtlUnicodeToMultiByteSize function"]
ms.keywords: RtlUnicodeToMultiByteSize, RtlUnicodeToMultiByteSize routine [Installable File System Drivers], ifsk.rtlunicodetomultibytesize, ntifs/RtlUnicodeToMultiByteSize, rtlref_f0366c3a-b185-45f3-a7e2-541168b842d3.xml
req.header: ntifs.h
req.include-header: Ntifs.h
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
 - RtlUnicodeToMultiByteSize
 - ntifs/RtlUnicodeToMultiByteSize
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlUnicodeToMultiByteSize
---

# RtlUnicodeToMultiByteSize function


## -description

The <b>RtlUnicodeToMultiByteSize</b> routine determines the number of bytes that are required to store the multibyte translation for the specified Unicode string. The translation is assumed to use the current system ANSI code page (ACP).

## -parameters

### -param BytesInMultiByteString 

[out]
Pointer to a caller-allocated variable that receives the number of bytes required to store the translated string.

### -param UnicodeString 

[in]
Pointer to the Unicode string for which the multibyte length is to be calculated.

### -param BytesInUnicodeString 

[in]
Length, in bytes, of the source string.

## -returns

<b>RtlUnicodeToMultiByteSize</b> returns STATUS_SUCCESS.

## -remarks

<b>RtlUnicodeToMultiByteSize</b> can be called to determine how much memory to allocate, or possibly the value to specify for <i>MaxBytesInMultiByteString</i>, before translating a Unicode string to ANSI with <b>RtlUnicodeToMultiByteN</b> or <b>RtlUpcaseUnicodeToMultiByteN</b>. The returned value does not include space for a NULL terminator for the ANSI string. 

Like <b>RtlUnicodeToMultiByteN</b>, <b>RtlUnicodeToMultiByteSize</b> supports only precomposed Unicode characters that are mapped to the current system ANSI code page installed at system boot. 

For information about other string-handling routines, see <a href="/windows-hardware/drivers/ddi/_kernel/#run-time-library-rtl-routines">Run-Time Library (RTL) Routines</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlmultibytetounicodesize">RtlMultiByteToUnicodeSize</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlunicodetomultibyten">RtlUnicodeToMultiByteN</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlupcaseunicodetomultibyten">RtlUpcaseUnicodeToMultiByteN</a>
