---
UID: NF:ntifs.RtlUnicodeStringToCountedOemString
title: RtlUnicodeStringToCountedOemString function (ntifs.h)
description: The RtlUnicodeStringToCountedOemString routine translates the specified Unicode source string into a counted OEM string using the current system OEM code page.
old-location: ifsk\rtlunicodestringtocountedoemstring.htm
tech.root: ifsk
ms.assetid: 7479d5d0-69d0-42b8-9aa1-5eab8b71b118
ms.date: 04/16/2018
keywords: ["RtlUnicodeStringToCountedOemString function"]
ms.keywords: RtlUnicodeStringToCountedOemString, RtlUnicodeStringToCountedOemString routine [Installable File System Drivers], ifsk.rtlunicodestringtocountedoemstring, ntifs/RtlUnicodeStringToCountedOemString, rtlref_dbc62228-043f-43f1-bd19-464adf37b693.xml
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
 - RtlUnicodeStringToCountedOemString
 - ntifs/RtlUnicodeStringToCountedOemString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlUnicodeStringToCountedOemString
---

# RtlUnicodeStringToCountedOemString function


## -description

The <b>RtlUnicodeStringToCountedOemString</b> routine translates the specified Unicode source string into a counted OEM string using the current system OEM code page.

## -parameters

### -param DestinationString

Pointer to a caller-allocated buffer to receive the counted OEM string. If <i>AllocateDestinationString</i> is <b>FALSE</b>, the caller must also allocate a buffer for the <b>Buffer</b> member of <i>DestinationString</i> to hold the OEM data. If <i>AllocateDestinationString</i> is <b>TRUE</b>, <b>RtlUnicodeStringToCountedOemString</b> allocates a buffer large enough to hold the string, passes a pointer to it in <b>Buffer</b>, and updates the length and maximum length members of <i>DestinationString</i> accordingly.

### -param SourceString 

[in]
Pointer to the source Unicode string to be translated.

### -param AllocateDestinationString 

[in]
Set to <b>TRUE</b> if <b>RtlUnicodeStringToCountedOemString</b> should allocate the buffer space for the <i>DestinationString</i>, <b>FALSE</b> otherwise. If this parameter is <b>TRUE</b>, the caller is responsible for freeing the buffer when it is no longer needed by calling <b>RtlFreeOemString</b>.

## -returns

<b>RtlUnicodeStringToCountedOemString</b> returns STATUS_SUCCESS if the string at <i>DestinationString</i> is translated. Otherwise, no storage was allocated, and no conversion was performed. This routine returns STATUS_UNMAPPABLE_CHARACTER if it cannot translate a character in the given <i>SourceString</i>.

## -remarks

<b>RtlUnicodeStringToCountedOemString</b> returns a translated string that does not include a NULL terminator. It translates the given source string using the OEM code page that was installed as the current system code page at system boot time. 

<b>RtlUnicodeStringToCountedOemString</b> does not modify the source string.

For information about other string-handling routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Strings</a>.

## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff558741(v=vs.85)">OEM_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlfreeoemstring">RtlFreeOemString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtloemstringtocountedunicodestring">RtlOemStringToCountedUnicodeString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlunicodestringtooemstring">RtlUnicodeStringToOemString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlunicodetooemn">RtlUnicodeToOemN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlupcaseunicodestringtocountedoemstring">RtlUpcaseUnicodeStringToCountedOemString</a>



<a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>

