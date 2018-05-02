---
UID: NF:ntstrsafe.RtlStringCbVPrintfExA
title: RtlStringCbVPrintfExA function
author: windows-driver-content
description: The RtlStringCbVPrintfExW and RtlStringCbVPrintfExA functions create a byte-counted text string, with formatting that is based on supplied formatting information.
old-location: kernel\rtlstringcbvprintfex.htm
old-project: kernel
ms.assetid: 29359aa3-2429-45fc-bc19-b58df60c4e89
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: RtlStringCbVPrintfEx, RtlStringCbVPrintfExA, RtlStringCbVPrintfExW, RtlStringCbVPrintfExW function [Kernel-Mode Driver Architecture], STRSAFE_FILL_BEHIND_NULL, STRSAFE_FILL_ON_FAILURE, STRSAFE_IGNORE_NULLS, STRSAFE_NO_TRUNCATION, STRSAFE_NULL_ON_FAILURE, kernel.rtlstringcbvprintfex, ntstrsafe/RtlStringCbVPrintfExA, ntstrsafe/RtlStringCbVPrintfExW, safestrings_95156244-d97b-452b-bd09-3e68d3c25392.xml
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
req.ddi-compliance: 
req.unicode-ansi: RtlStringCbVPrintfExW (Unicode) and RtlStringCbVPrintfExA (ANSI)
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntstrsafe.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ntstrsafe.lib
-	Ntstrsafe.dll
api_name:
-	RtlStringCbVPrintfExW
-	RtlStringCbVPrintfExA
-	RtlStringCbVPrintfExW
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlStringCbVPrintfExA function


## -description


The <b>RtlStringCbVPrintfExW</b> and <b>RtlStringCbVPrintfExA</b> functions create a byte-counted text string, with formatting that is based on supplied formatting information.


## -parameters




### -param pszDest [out, optional]

A pointer to a caller-supplied buffer that receives a formatted, null-terminated string. The function creates this string from both the formatting string that is supplied by <i>pszFormat</i> and the arguments supplied by <i>argList</i>. The <i>pszDest</i> pointer can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.


### -param cbDest [in]

The size of the destination buffer, in bytes. The buffer must be large enough to contain the formatted string plus the terminating null character. 

For Unicode strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * sizeof(WCHAR). 

For ANSI strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * sizeof(char). 

If <i>pszDest</i> is <b>NULL</b>, <i>cbDest</i> must be zero.


### -param ppszDestEnd [out, optional]

If the caller supplies a non-<b>NULL</b> address pointer then, after the operation completes, the function loads that address with a pointer to the destination buffer's resulting null string terminator. 


### -param pcbRemaining [out, optional]

If the caller supplies a non-<b>NULL</b> address pointer, the function loads the address with the number of unused bytes that are in the buffer pointed to by <i>pszDest</i>, including bytes used for the terminating null character.


### -param dwFlags [in]

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
If set, either <i>pszDest </i>or<i> pszSrc</i>, or both, can be <b>NULL</b>. <b>NULL</b> <i>pszSrc</i> pointers are treated like empty strings (TEXT("")), which can be copied. <b>NULL</b> <i>pszDest</i> pointers cannot receive nonempty strings. 

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
 


### -param pszFormat [in, optional]

A pointer to a null-terminated text string that contains <b>printf</b>-styled formatting directives. The <i>pszFormat</i> pointer can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.


### -param argList [in]

A <b>va_list</b>-typed argument list. Arguments contained in the argument list will be interpreted by using the formatting string that is supplied by <i>pszFormat</i>.


## -returns



The function returns one of the NTSTATUS values that are listed in the following table. For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.

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



<b>RtlStringCbVPrintfExW</b> and <b>RtlStringCbVPrintfExA</b> should be used instead of the following functions: 

<ul>
<li>
<b>vsprintf</b>

</li>
<li>
<b>vswprintf</b>

</li>
<li>
_<b>vsnprintf</b>

</li>
<li>
_<b>vsnwprintf</b>

</li>
</ul>
All of these functions accept a format string, along with a set of arguments in a <b>va_list</b>-typed argument list, and return a formatted string. The size, in bytes, of the destination buffer is provided to <b>RtlStringCbVPrintfExW</b> and <b>RtlStringCbVPrintfExA</b> to ensure that they do not write past the end of the buffer.

<b>RtlStringCbVPrintfExW</b> and <b>RtlStringCbVPrintfExA</b> add to the functionality of <a href="https://msdn.microsoft.com/library/windows/hardware/ff562831">RtlStringCbVPrintf</a> by returning a pointer to the end of the destination string, as well as the number of bytes left unused in that string. Flags can be passed to the function for additional control.

For more information about <b>va_list</b>-typed argument lists, see the Microsoft Windows SDK documentation.

Use <b>RtlStringCbVPrintfExW</b> to handle Unicode strings and <b>RtlStringCbVPrintfExA</b> to handle ANSI strings. The form you use depends on your data, as shown in the following table.

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
<b>RtlStringCbVPrintfExW</b>

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
<b>RtlStringCbVPrintfExA</b>

</td>
</tr>
</table>
 

If <i>pszDest</i> and <i>pszFormat</i> point to overlapping strings, or if any argument strings overlap, behavior of the function is undefined.

Neither <i>pszFormat</i> nor <i>pszDest</i> can be <b>NULL</b> unless the STRSAFE_IGNORE_NULLS flag is set, in which case either or both can be <b>NULL</b>. If <i>pszDest</i> is <b>NULL</b>, <i>pszFormat</i> must either be <b>NULL</b> or point to an empty string.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562828">RtlStringCbPrintfEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562831">RtlStringCbVPrintf</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562868">RtlStringCchVPrintfEx</a>
 

 

