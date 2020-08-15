---
UID: NF:ntstrsafe.RtlStringCbPrintfExW
title: RtlStringCbPrintfExW function (ntstrsafe.h)
description: The RtlStringCbPrintfExW and RtlStringCbPrintfExA functions create a byte-counted text string, with formatting that is based on supplied formatting information.
old-location: kernel\rtlstringcbprintfex.htm
tech.root: kernel
ms.assetid: 514a5b40-c9ba-4ed1-871d-fd6ffde583a6
ms.date: 04/30/2018
keywords: ["RtlStringCbPrintfExW function"]
ms.keywords: RtlStringCbPrintfEx, RtlStringCbPrintfExA, RtlStringCbPrintfExW, RtlStringCbPrintfExW function [Kernel-Mode Driver Architecture], STRSAFE_FILL_BEHIND_NULL, STRSAFE_FILL_ON_FAILURE, STRSAFE_IGNORE_NULLS, STRSAFE_NO_TRUNCATION, STRSAFE_NULL_ON_FAILURE, kernel.rtlstringcbprintfex, ntstrsafe/RtlStringCbPrintfExA, ntstrsafe/RtlStringCbPrintfExW, safestrings_44a6ae33-3b6e-4de4-893c-4a198dfa75da.xml
f1_keywords:
 - "ntstrsafe/RtlStringCbPrintfExW"
 - "RtlStringCbPrintfExW"
req.header: ntstrsafe.h
req.include-header: Ntstrsafe.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows XP with Service Pack 1 (SP1).
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: RtlStringCbPrintfExW (Unicode) and RtlStringCbPrintfExA (ANSI)
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntstrsafe.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ntstrsafe.lib
- Ntstrsafe.dll
api_name:
- RtlStringCbPrintfExW
- RtlStringCbPrintfExA
- RtlStringCbPrintfExW
targetos: Windows
req.typenames: 
---

# RtlStringCbPrintfExW function


## -description


The <b>RtlStringCbPrintfExW</b> and <b>RtlStringCbPrintfExA</b> functions create a byte-counted text string, with formatting that is based on supplied formatting information.


## -parameters




### -param pszDest 
[out, optional]
A pointer to a caller-supplied buffer that receives a formatted, null-terminated string. The function creates this string from both the formatting string that is supplied by <i>pszFormat</i> and the function's argument list. The <i>pszDest</i> pointer can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.


### -param cbDest 
[in]
The size of the destination buffer, in bytes. The buffer must be large enough to contain the formatted string plus the terminating null character. 

For Unicode strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * sizeof(WCHAR). 

For ANSI strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * sizeof(char). 

If <i>pszDest</i> is <b>NULL</b>, <i>cbDest</i> must be zero.


### -param ppszDestEnd 
[out, optional]
If the caller supplies a non-<b>NULL</b> address pointer then, after the operation completes, the function loads that address with a pointer to the destination buffer's resulting null string terminator. 


### -param pcbRemaining 
[out, optional]
If the caller supplies a non-<b>NULL</b> address pointer, the function loads the address with the number of unused bytes that are in the buffer pointed to by <i>pszDest</i>, including bytes used for the terminating null character.


### -param dwFlags 
[in]
One or more flags and, optionally, a fill byte. The flags are defined as follows:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="STRSAFE_FILL_BEHIND_NULL_"></a><a id="strsafe_fill_behind_null_"></a><dl>
<dt><b>STRSAFE_FILL_BEHIND_NULL </b></dt>
</dl>
</td>
<td width="60%">
If set and the function succeeds, the low byte of <i>dwFlags</i> is used to fill the portion of the destination buffer that follows the terminating null character. 

</td>
</tr>
<tr>
<td width="40%"><a id="STRSAFE_IGNORE_NULLS_"></a><a id="strsafe_ignore_nulls_"></a><dl>
<dt><b>STRSAFE_IGNORE_NULLS </b></dt>
</dl>
</td>
<td width="60%">
If set, either <i>pszDest </i>or<i> pszSrc</i>, or both, can be <b>NULL</b>. <b>NULL</b><i>pszSrc</i> pointers are treated like empty strings (TEXT("")), which can be copied. <b>NULL</b><i>pszDest</i> pointers cannot receive nonempty strings. 

</td>
</tr>
<tr>
<td width="40%"><a id="STRSAFE_FILL_ON_FAILURE_"></a><a id="strsafe_fill_on_failure_"></a><dl>
<dt><b>STRSAFE_FILL_ON_FAILURE </b></dt>
</dl>
</td>
<td width="60%">
If set and the function fails, the low byte of <i>dwFlags</i> is used to fill the entire destination buffer, and the buffer is null-terminated. This operation overwrites any preexisting buffer contents. 

</td>
</tr>
<tr>
<td width="40%"><a id="STRSAFE_NULL_ON_FAILURE_"></a><a id="strsafe_null_on_failure_"></a><dl>
<dt><b>STRSAFE_NULL_ON_FAILURE </b></dt>
</dl>
</td>
<td width="60%">
If set and the function fails, the destination buffer is set to an empty string (TEXT("")). This operation overwrites any preexisting buffer contents. 

</td>
</tr>
<tr>
<td width="40%"><a id="STRSAFE_NO_TRUNCATION_"></a><a id="strsafe_no_truncation_"></a><dl>
<dt><b>STRSAFE_NO_TRUNCATION </b></dt>
</dl>
</td>
<td width="60%">
If set and the function returns STATUS_BUFFER_OVERFLOW, the contents of the destination buffer are not modified.

</td>
</tr>
</table>
 


### -param pszFormat 
[in, optional]
A pointer to a null-terminated text string that contains <b>printf</b>-styled <a href="https://docs.microsoft.com/cpp/c-runtime-library/format-specification-syntax-printf-and-wprintf-functions">formatting directives</a>. The <i>pszFormat</i> pointer can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.


### -param param

<p>A list of arguments that are interpreted by the function, based on formatting directives contained in the <i>pszFormat</i> string.</p>




####### - ...

A list of arguments that are interpreted by the function, based on formatting directives contained in the <i>pszFormat</i> string.


## -returns



The function returns one of the NTSTATUS values that are listed in the following table. For information about how to test NTSTATUS values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">Using NTSTATUS Values</a>.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
This <i>success</i> status means source data was present, the output string was created without truncation, and the resultant destination buffer is null-terminated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
This <i>warning</i> status means the operation did not complete due to insufficient space in the destination buffer. If STRSAFE_NO_TRUNCATION is set in <i>dwFlags</i>, the destination buffer is not modified. If the flag is not set, the destination buffer contains a truncated version of the created string.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
This <i>error</i> status means the function received an invalid input parameter. For more information, see the following paragraph.

The function returns the STATUS_INVALID_PARAMETER value when:

<ul>
<li>An invalid flag was specified.</li>
<li>The value in <i>cbDest</i> is larger than the maximum buffer size.</li>
<li>The destination buffer was already full.</li>
<li>A <b>NULL</b> pointer was present without the STRSAFE_IGNORE_NULLS flag.</li>
<li>The destination buffer pointer was <b>NULL</b>, but the buffer size was not zero.</li>
<li>The destination buffer pointer was <b>NULL</b>, or its length was zero, but a nonzero length source string was present.</li>
</ul>
</td>
</tr>
</table>
 




## -remarks



<b>RtlStringCbPrintfExW</b> and <b>RtlStringCbPrintfExA</b> should be used instead of the following functions: 

<ul>
<li>
<b>sprintf</b>

</li>
<li>
<b>swprintf</b>

</li>
<li>
_<b>snprintf</b>

</li>
<li>
_<b>snwprintf</b>

</li>
</ul>
All of these functions accept a format string and a list of arguments, interpret them, and create a formatted string. The size, in bytes, of the destination buffer is provided to <b>RtlStringCbPrintfExW</b> and <b>RtlStringCbPrintfExA</b> to ensure that they do not write past the end of the buffer.

<b>RtlStringCbPrintfExW</b> and <b>RtlStringCbPrintfExA</b> add to the functionality of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlstringcbprintfa">RtlStringCbPrintf</a> by returning a pointer to the end of the destination string, as well as the number of bytes left unused in that string. Flags can be passed to the function for additional control.

Use <b>RtlStringCbPrintfExW</b> to handle Unicode strings and <b>RtlStringCbPrintfExA</b> to handle ANSI strings. The form you use depends on your data, as shown in the following table.

<table>
<tr>
<th>String data type</th>
<th>String literal</th>
<th>Function</th>
</tr>
<tr>
<td>
WCHAR

</td>
<td>
L"string"

</td>
<td>
<b>RtlStringCbPrintfExW</b>

</td>
</tr>
<tr>
<td>
<b>char</b>

</td>
<td>
"string"

</td>
<td>
<b>RtlStringCbPrintfExA</b>

</td>
</tr>
</table>
 

If <i>pszDest</i> and <i>pszFormat </i>point to overlapping strings or if any argument strings overlap, the behavior of the function is undefined.

Neither <i>pszFormat</i> nor <i>pszDest</i> can be <b>NULL</b> unless the STRSAFE_IGNORE_NULLS flag is set, in which case either or both can be <b>NULL</b>. If <i>pszDest</i> is <b>NULL</b>, <i>pszFormat</i> must either be <b>NULL</b> or point to an empty string.

For more information about the safe string functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-safe-string-functions">Using Safe String Functions</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlstringcbvprintfexa">RtlStringCbVPrintfEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlstringcchprintfa">RtlStringCchPrintf</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlstringcchprintfexa">RtlStringCchPrintfEx</a>
 

 

