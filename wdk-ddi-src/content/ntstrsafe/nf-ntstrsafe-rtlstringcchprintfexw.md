---
UID: NF:ntstrsafe.RtlStringCchPrintfExW
title: RtlStringCchPrintfExW function
author: windows-driver-content
description: The RtlStringCchPrintfExW and RtlStringCchPrintfExA functions create a character-counted text string, with formatting that is based on supplied formatting information.
old-location: kernel\rtlstringcchprintfex.htm
old-project: kernel
ms.assetid: 8b43acd5-9204-41ff-8c63-76769bfa5469
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlStringCchPrintfExW
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntstrsafe.h
req.include-header: Ntstrsafe.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP with Service Pack 1 (SP1) and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlStringCchPrintfExW,RtlStringCchPrintfExA,RtlStringCchPrintfExW
req.alt-loc: Ntstrsafe.lib,Ntstrsafe.dll
req.ddi-compliance: 
req.unicode-ansi: RtlStringCchPrintfExW (Unicode) and RtlStringCchPrintfExA (ANSI)
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntstrsafe.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PBATTERY_REPORTING_SCALE, BATTERY_REPORTING_SCALE
---

# RtlStringCchPrintfExW function



## -description
The <b>RtlStringCchPrintfExW</b> and <b>RtlStringCchPrintfExA</b> functions create a character-counted text string, with formatting that is based on supplied formatting information.



## -syntax

````
NTSTATUS RtlStringCchPrintfExW(
  _Out_opt_ LPTSTR  pszDest,
  _In_      size_t  cchDest,
  _Out_opt_ LPTSTR  *ppszDestEnd,
  _Out_opt_ size_t  *pcchRemaining,
  _In_      DWORD   dwFlags,
  _In_      LPCTSTR pszFormat,
                    ...
);
````


## -parameters

### -param pszDest [out, optional]

A pointer to a caller-supplied buffer that receives a formatted, null-terminated string. The function creates this string from both the formatting string that is supplied by <i>pszFormat</i> and the function's argument list. The <i>pszDest</i> pointer can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.


### -param cchDest [in]

The size of the destination buffer, in characters. The buffer must be large enough to contain the formatted string plus the terminating null character. The maximum number of characters allowed is NTSTRSAFE_MAX_CCH. If <i>pszDest</i> is <b>NULL</b>, <i>cchDest</i> must be zero.


### -param ppszDestEnd [out, optional]

If the caller supplies a non-<b>NULL</b> address pointer then, after the operation completes, the function loads that address with a pointer to the destination buffer's resulting <b>NULL</b> string terminator. 


### -param pcchRemaining [out, optional]

If the caller supplies a non-<b>NULL</b> address pointer, the function loads the address with the number of unused characters in the buffer pointed to by <i>pszDest</i>, including the terminating null character.


### -param dwFlags [in]

One or more flags and, optionally, a fill byte. The flags are defined as follows: 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -param STRSAFE_FILL_BEHIND_NULL 

</td>
<td width="60%">
If set and the function succeeds, the low byte of <i>dwFlags</i> is used to fill the portion of the destination buffer that follows the terminating null character. 

</td>
</tr>
<tr>

### -param STRSAFE_IGNORE_NULLS 

</td>
<td width="60%">
If set, either <i>pszDest </i>or<i> pszSrc</i>, or both, can be <b>NULL</b>. <b>NULL</b> <i>pszSrc</i> pointers are treated like empty strings (TEXT("")), which can be copied. <b>NULL</b> <i>pszDest</i> pointers cannot receive nonempty strings. 

</td>
</tr>
<tr>

### -param STRSAFE_FILL_ON_FAILURE 

</td>
<td width="60%">
If set and the function fails, the low byte of <i>dwFlags</i> is used to fill the entire destination buffer, and the buffer is null-terminated. This operation overwrites any preexisting buffer contents. 

</td>
</tr>
<tr>

### -param STRSAFE_NULL_ON_FAILURE 

</td>
<td width="60%">
If set and the function fails, the destination buffer is set to an empty string (TEXT("")). This operation overwrites any preexisting buffer contents. 

</td>
</tr>
<tr>

### -param STRSAFE_NO_TRUNCATION 

</td>
<td width="60%">
If set and the function returns STATUS_BUFFER_OVERFLOW, the contents of the destination buffer are not modified.

</td>
</tr>
</table>
 


### -param pszFormat [in]

A pointer to a null-terminated text string that contains <b>printf</b>-styled formatting directives. The <i>pszFormat</i> pointer can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.


### -param ... 

An optional list of arguments that are interpreted by the function, based on formatting directives contained in the <i>pszFormat</i> string.


## -returns
The function returns one of the <b>NTSTATUS</b> values that are listed in the following table. For information about how to test <b>NTSTATUS</b> values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>This <i>success</i> status means source data was present, the output string was created without truncation, and the resultant destination buffer is null-terminated.
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>This <i>warning</i> status means the operation did not complete due to insufficient space in the destination buffer. If STRSAFE_NO_TRUNCATION is set in <i>dwFlags</i>, the destination buffer is not modified. If the flag is not set, the destination buffer contains a truncated version of the created string.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>This <i>error</i> status means the function received an invalid input parameter. For more information, see the following paragraph.

The function returns the STATUS_INVALID_PARAMETER value when:

 


## -remarks
<b>RtlStringCchPrintfExW</b> and <b>RtlStringCchPrintfExA</b> should be used instead of the following functions: 

<b>sprintf</b>

<b>swprintf</b>

_<b>snprintf</b>

_<b>snwprintf</b>

All of these functions accept a format string and a list of arguments and return a formatted string. <b>RtlStringCchPrintfExW</b> and <b>RtlStringCchPrintfExA</b> accept the size, in characters, of the destination buffer to ensure that they do not write past the end of this buffer.

<b>RtlStringCchPrintfExW</b> and <b>RtlStringCchPrintfExA</b> add to the functionality of <a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchprintfw.md">RtlStringCchPrintf</a> by returning a pointer to the end of the destination string, as well as the number of characters left unused in that string. Flags can be passed to the function for additional control.

Use <b>RtlStringCchPrintfExW</b> to handle Unicode strings and <b>RtlStringCchPrintfExA</b> to handle ANSI strings. The form you use depends on your data, as shown in the following table.

WCHAR

L"string"

<b>RtlStringCchPrintfExW</b>

<b>char</b>

"string"

<b>RtlStringCchPrintfExA</b>

If <i>pszDest</i> and <i>pszFormat</i> point to overlapping strings, or any argument strings overlap, the behavior of the function is undefined.

Neither <i>pszSrc</i> nor <i>pszDest</i> can be <b>NULL</b> unless the STRSAFE_IGNORE_NULLS flag is set, in which case either or both can be <b>NULL</b>. If <i>pszDest</i> is <b>NULL</b>, <i>pszSrc</i> must either be <b>NULL</b> or point to an empty string.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>. 


## -see-also
<dl>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbprintfexw.md">RtlStringCbPrintfEx</a>
</dt>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchprintfw.md">RtlStringCchPrintf</a>
</dt>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchvprintfexw.md">RtlStringCchVPrintfEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlStringCchPrintfExW function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

