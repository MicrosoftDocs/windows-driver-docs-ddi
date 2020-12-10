---
UID: NF:wdm.RtlAnsiStringToUnicodeString
title: RtlAnsiStringToUnicodeString function (wdm.h)
description: RtlAnsiStringToUnicodeString converts the given ANSI source string into a Unicode string.
old-location: kernel\rtlansistringtounicodestring.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlAnsiStringToUnicodeString function"]
ms.keywords: RtlAnsiStringToUnicodeString, RtlAnsiStringToUnicodeString function [Kernel-Mode Driver Architecture], k109_d27ee285-6d32-4ecb-994b-ba8a47f1e588.xml, kernel.rtlansistringtounicodestring, wdm/RtlAnsiStringToUnicodeString
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
 - RtlAnsiStringToUnicodeString
 - wdm/RtlAnsiStringToUnicodeString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlAnsiStringToUnicodeString
---

# RtlAnsiStringToUnicodeString function


## -description

<b>RtlAnsiStringToUnicodeString</b> converts the given ANSI source string into a Unicode string.

## -parameters

### -param DestinationString 

[in, out]
Pointer to a <a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure to hold the converted Unicode string. If <i>AllocateDestinationString</i> is <b>TRUE</b>, the routine allocates a new buffer to hold the string data, and updates the <b>Buffer</b> member of <i>DestinationString</i> to point to the new buffer. Otherwise, the routine uses the currently-specified buffer to hold the string.

### -param SourceString 

[in]
Pointer to the ANSI string to be converted to Unicode.

### -param AllocateDestinationString 

[in]
Specifies if this routine should allocate the buffer space for the destination string. If it does, the caller must deallocate the buffer by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfreeunicodestring">RtlFreeUnicodeString</a>.

## -returns

If the conversion succeeds, <b>RtlAnsiStringToUnicodeString</b> returns STATUS_SUCCESS. On failure, the routine does not allocate any memory.

## -remarks

The translation conforms to the current system locale information.

If caller sets <i>AllocateDestinationString</i> to <b>TRUE</b>, the routine replaces the <b>Buffer</b> member of <i>DestinationString</i> with a pointer to the buffer it allocates. The old value can be overwritten even when the routine returns an error status code.

This routine is not declared in a header file. However, you can copy the following declaration to your source code:


```
NTSYSAPI
WCHAR
NTAPI
RtlAnsiCharToUnicodeChar(
    __inout PUCHAR *SourceCharacter
    );
```

You can use the following routines to convert single-byte and double-byte characters to Unicode characters:


<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlansistringtounicodesize">RtlAnsiStringToUnicodeSize</a>


<b>RtlAnsiStringToUnicodeString</b>


<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlmultibytetounicodesize">RtlMultiByteToUnicodeSize</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlmultibytetounicoden">RtlMultiByteToUnicodeN</a>


For more information about these and other string-handling routines, see <a href="/windows-hardware/drivers/ddi/_kernel/#run-time-library-rtl-routines">Run-Time Library (RTL) Routines</a>.

<b>RtlAnsiCharToUnicodeChar</b> has security deficiencies. Consider using the <b>RtlAnsiStringToUnicodeString</b> routine instead.

If, on entry, *<i>SourceCharacter</i> points to a one-byte buffer that contains the first byte of a two-byte character code, <b>RtlAnsiCharToUnicodeChar</b> overruns the buffer when it tries to read the second byte.

At system startup, the operating system determines the user language from the locale settings and installs the appropriate system ANSI code page. <b>RtlAnsiCharToUnicodeChar</b> uses this code page to convert a single-byte or double-byte character to the corresponding Unicode character.

If the system ANSI code page defines a single-byte character set (that is, the ANSI character set), <b>RtlAnsiCharToUnicodeChar</b> speeds up the conversion operation by simply <a href="/windows-hardware/drivers/">zero-extending</a> an ANSI character in the range 0x00 to 0x7f to produce the corresponding Unicode character. The routine converts the ANSI value 0x5c to the backslash character ("\\"), even if the single-byte code page defines this character as the yen sign.

If, on entry, *<i>SourceCharacter</i> points to an invalid character code, <b>RtlAnsiCharToUnicodeChar</b> returns the Unicode space character code, 0x0020. The following list shows examples of invalid character codes:

<ul>
<li>
The first byte of the character code is a value that is valid only as the second byte of a two-byte character code. 

</li>
<li>
The second byte of a two-byte character code is a value that is valid only as the first byte. 

</li>
</ul>

## -see-also

<a href="/windows/win32/api/ntdef/ns-ntdef-string">ANSI_STRING</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlansistringtounicodesize">RtlAnsiStringToUnicodeSize</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfreeunicodestring">RtlFreeUnicodeString</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitansistring">RtlInitAnsiString</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlunicodestringtoansistring">RtlUnicodeStringToAnsiString</a>



<a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
