---
UID: NF:wdm.RtlUnicodeStringToAnsiString
title: RtlUnicodeStringToAnsiString function (wdm.h)
description: The RtlUnicodeStringToAnsiString routine converts a given Unicode string into an ANSI string.
old-location: kernel\rtlunicodestringtoansistring.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlUnicodeStringToAnsiString function"]
ms.keywords: RtlUnicodeStringToAnsiString, RtlUnicodeStringToAnsiString routine [Kernel-Mode Driver Architecture], k109_50e549a0-61fa-4a0f-b43f-de2f4c6dba31.xml, kernel.rtlunicodestringtoansistring, wdm/RtlUnicodeStringToAnsiString
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlUnicodeStringToAnsiString
 - wdm/RtlUnicodeStringToAnsiString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlUnicodeStringToAnsiString
---

# RtlUnicodeStringToAnsiString function


## -description

The <b>RtlUnicodeStringToAnsiString</b> routine converts a given Unicode string into an ANSI string.

## -parameters

### -param DestinationString 

[in, out]
Pointer to an <a href="/windows/win32/api/ntdef/ns-ntdef-string">ANSI_STRING</a> structure to hold the converted ANSI string. If <i>AllocateDestinationString</i> is <b>TRUE</b>, the routine allocates a new buffer to hold the string data, and updates the <b>Buffer</b> member of <i>DestinationString</i> to point to the new buffer. Otherwise, the routine uses the currently specified buffer to hold the string.

### -param SourceString 

[in]
Pointer to the Unicode source string to be converted to ANSI.

### -param AllocateDestinationString 

[in]
<b>TRUE</b> if this routine is to allocate the buffer space for the <i>DestinationString</i>. If it does, the buffer must be deallocated by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfreeansistring">RtlFreeAnsiString</a>.

## -returns

If the conversion succeeds, <b>RtlUnicodeStringToAnsiString</b> returns STATUS_SUCCESS. Otherwise, no storage was allocated, and no conversion was done.

## -remarks

The translation is done in accord with the current system-locale information.

## -see-also

<a href="/windows/win32/api/ntdef/ns-ntdef-string">ANSI_STRING</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlansistringtounicodestring">RtlAnsiStringToUnicodeString</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfreeansistring">RtlFreeAnsiString</a>



<a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
