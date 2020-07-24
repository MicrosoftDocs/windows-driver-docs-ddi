---
UID: NF:ntstrsafe.RtlStringCbPrintfA
title: RtlStringCbPrintfA function (ntstrsafe.h)
description: The RtlStringCbPrintfW and RtlStringCbPrintfA functions create a byte-counted text string, with formatting that is based on supplied formatting information.
old-location: kernel\rtlstringcbprintf.htm
tech.root: kernel
ms.assetid: ff35590f-1834-462a-9a9e-f7a3268776e8
ms.date: 04/30/2018
keywords: ["RtlStringCbPrintfA function"]
ms.keywords: RtlStringCbPrintf, RtlStringCbPrintfA, RtlStringCbPrintfW, RtlStringCbPrintfW function [Kernel-Mode Driver Architecture], kernel.rtlstringcbprintf, ntstrsafe/RtlStringCbPrintfA, ntstrsafe/RtlStringCbPrintfW, safestrings_066962fd-30e4-4535-b667-bf6f8fa2f2b2.xml
f1_keywords:
 - "ntstrsafe/RtlStringCbPrintfW"
 - "RtlStringCbPrintfW"
req.header: ntstrsafe.h
req.include-header: Ntstrsafe.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows XP with Service Pack 1 (SP1).
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: RtlStringCbPrintfW (Unicode) and RtlStringCbPrintfA (ANSI)
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
- RtlStringCbPrintfW
- RtlStringCbPrintfA
- RtlStringCbPrintfW
targetos: Windows
req.typenames: 
---

# RtlStringCbPrintfA function


## -description


The <b>RtlStringCbPrintfW</b> and <b>RtlStringCbPrintfA</b> functions create a byte-counted text string, with formatting that is based on supplied formatting information. 


## -parameters




### -param pszDest [out]

A pointer to a caller-supplied buffer that receives a formatted, null-terminated string. The function creates this string from both the formatting string that is supplied by <i>pszFormat</i> and the function's argument list. 


### -param cbDest [in]

The size of the destination buffer, in bytes. The buffer must be large enough to contain the formatted string plus the terminating null character. 

For Unicode strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * sizeof(WCHAR). 

For ANSI strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * sizeof(char). 


### -param pszFormat [in]

A pointer to a null-terminated text string that contains <b>printf</b>-styled <a href="https://docs.microsoft.com/cpp/c-runtime-library/format-specification-syntax-printf-and-wprintf-functions">formatting directives</a>.


### -param param

<p>A list of arguments that are interpreted by the function based on formatting directives contained in the <i>pszFormat</i> string.</p>




####### - ...

A list of arguments that are interpreted by the function based on formatting directives contained in the <i>pszFormat</i> string.


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
This <i>success</i> status means source data was present, the string was created without truncation, and the resultant destination buffer is null-terminated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
This <i>warning</i> status means the operation did not complete due to insufficient space in the destination buffer. The destination buffer contains a truncated version of the output string.

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
<li>The value in <i>cbDest</i> is larger than the maximum buffer size.</li>
<li>The destination buffer was already full.</li>
<li>A <b>NULL</b> pointer was present.</li>
<li>The destination buffer's length was zero, but a nonzero length source string was present.</li>
</ul>
</td>
</tr>
</table>
 




## -remarks



<b>RtlStringCbPrintfW</b> and <b>RtlStringCbPrintfA</b> should be used instead of the following functions: 

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
All of these functions accept a format string and a list of arguments, interpret them, and create a formatted string. The size, in bytes, of the destination buffer is provided to <b>RtlStringCbPrintfW</b> and <b>RtlStringCbPrintfA</b> to ensure that they do not write past the end of the buffer.

Use <b>RtlStringCbPrintfW</b> to handle Unicode strings and <b>RtlStringCbPrintfA</b> to handle ANSI strings. The form you use depends on your data, as shown in the following table.

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
<b>RtlStringCbPrintfW</b>

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
<b>RtlStringCbPrintfA</b>

</td>
</tr>
</table>
 

If <i>pszDest</i> and <i>pszFormat</i> point to overlapping string or if any argument strings overlap, the behavior of the function is undefined.

Neither <i>pszFormat</i> nor <i>pszDest</i> can be <b>NULL</b>. If you need to handle <b>NULL</b> string pointer values, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlstringcbprintfexa">RtlStringCbPrintfEx</a>.

For more information about the safe string functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-safe-string-functions">Using Safe String Functions</a>.


#### Examples

The following example shows a basic use of <b>RtlStringCbPrintfW</b> using four arguments.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>int const arraysize = 30;
WCHAR pszDest[arraysize]; 
size_t cbDest = arraysize * sizeof(WCHAR);

LPCWSTR pszFormat = L"%s %d + %d = %d.";
WCHAR* pszTxt = L"The answer is";

NTSTATUS status = RtlStringCbPrintfW(pszDest, cbDest, pszFormat, pszTxt, 1, 2, 3);</pre>
</td>
</tr>
</table></span></div>
The resultant string is "The answer is 1 + 2 = 3." It is contained in the buffer at <i>pszDest</i>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlstringcbprintfexa">RtlStringCbPrintfEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlstringcbvprintfa">RtlStringCbVPrintf</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlstringcchprintfa">RtlStringCchPrintf</a>
 

 

