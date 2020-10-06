---
UID: NF:ntifs.RtlUpcaseUnicodeStringToOemString
title: RtlUpcaseUnicodeStringToOemString function (ntifs.h)
description: The RtlUpcaseUnicodeStringToOemString routine translates a given Unicode source string into an uppercase OEM string using the current system OEM code page.
old-location: ifsk\rtlupcaseunicodestringtooemstring.htm
tech.root: ifsk
ms.assetid: 3d81c5e4-780b-4b1f-ad3a-6d59cab5650f
ms.date: 04/16/2018
keywords: ["RtlUpcaseUnicodeStringToOemString function"]
ms.keywords: RtlUpcaseUnicodeStringToOemString, RtlUpcaseUnicodeStringToOemString routine [Installable File System Drivers], ifsk.rtlupcaseunicodestringtooemstring, ntifs/RtlUpcaseUnicodeStringToOemString, rtlref_a98f9782-c665-40fa-af3d-47eb2bef27d9.xml
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
 - RtlUpcaseUnicodeStringToOemString
 - ntifs/RtlUpcaseUnicodeStringToOemString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlUpcaseUnicodeStringToOemString
---

# RtlUpcaseUnicodeStringToOemString function


## -description

The <b>RtlUpcaseUnicodeStringToOemString</b> routine translates a given Unicode source string into an uppercase OEM string using the current system OEM code page.

## -parameters

### -param DestinationString

Pointer to a caller-allocated buffer to receive the counted OEM string. If <i>AllocateDestinationString</i> is <b>FALSE</b>, the caller must also allocate a buffer for the <b>Buffer</b> member of <i>DestinationString</i> to hold the OEM data. If <i>AllocateDestinationString</i> is <b>TRUE</b>, <b>RtlUpcaseUnicodeStringToOemString</b> allocates a buffer large enough to hold the string, passes a pointer to it in <b>Buffer</b>, and updates the length and maximum length members of <i>DestinationString</i> accordingly.

### -param SourceString 

[in]
Pointer to the Unicode string to be translated.

### -param AllocateDestinationString 

[in]
Set to <b>TRUE</b> if <b>RtlUpcaseUnicodeStringToOemString</b> should allocate the buffer space for the <i>DestinationString</i>, <b>FALSE</b> otherwise. If this parameter is <b>TRUE</b>, the caller is responsible for freeing the buffer when it is no longer needed by calling <b>RtlFreeOemString</b>.

## -returns

<b>RtlUpcaseUnicodeStringToOemString</b> returns STATUS_SUCCESS if the string at <i>DestinationString</i> is translated. Otherwise, no storage was allocated, nor was any conversion performed.

## -remarks

<b>RtlUpcaseUnicodeStringToOemString</b> translates the given source string using the OEM code page that was installed as the current system code page at system boot time, and converts the OEM string to uppercase. 

This routine can substitute a default character in the destination string for all source string characters that it cannot map to the current code page and, then, return STATUS_SUCCESS. 

This routine does not modify the source string. It returns a null-terminated OEM string. 

For information about other string-handling routines, see <a href="/windows-hardware/drivers/ddi/index">Strings</a>.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/ff558741(v=vs.85)">OEM_STRING</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlfreeoemstring">RtlFreeOemString</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlunicodestringtocountedoemstring">RtlUnicodeStringToCountedOemString</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlunicodestringtooemsize">RtlUnicodeStringToOemSize</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlunicodestringtooemstring">RtlUnicodeStringToOemString</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlupcaseunicodetooemn">RtlUpcaseUnicodeToOemN</a>



<a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>