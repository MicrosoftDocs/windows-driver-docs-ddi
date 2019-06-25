---
UID: NF:ntstrsafe.RtlStringCchPrintfW
title: RtlStringCchPrintfW function (ntstrsafe.h)
description: The RtlStringCchPrintfW and RtlStringCchPrintfA functions create a character-counted text string, with formatting that is based on supplied formatting information.
old-location: kernel\rtlstringcchprintf.htm
tech.root: kernel
ms.assetid: e1c04e73-3055-4de8-bd8d-8d0a13541612
ms.date: 04/30/2018
ms.keywords: RtlStringCchPrintf, RtlStringCchPrintfA, RtlStringCchPrintfW, RtlStringCchPrintfW function [Kernel-Mode Driver Architecture], kernel.rtlstringcchprintf, ntstrsafe/RtlStringCchPrintfA, ntstrsafe/RtlStringCchPrintfW, safestrings_d1041cf8-bec9-4eef-8de8-7b662d474263.xml
ms.topic: function
req.header: ntstrsafe.h
req.include-header: Ntstrsafe.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows XP with Service Pack 1 (SP1).
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: RtlStringCchPrintfW (Unicode) and RtlStringCchPrintfA (ANSI)
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
- RtlStringCchPrintfW
- RtlStringCchPrintfA
- RtlStringCchPrintfW
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlStringCchPrintfW function


## -description


The <b>RtlStringCchPrintfW</b> and <b>RtlStringCchPrintfA</b> functions create a character-counted text string, with formatting that is based on supplied formatting information.


## -parameters




### -param pszDest [out]

A pointer to a caller-supplied buffer that receives a formatted, null-terminated string. The function creates this string from both the formatting string that is supplied by <i>pszFormat</i> and the function's argument list.


### -param cchDest [in]

The size of the destination buffer, in characters. The buffer must be large enough to contain the formatted string plus the terminating null character. The maximum number of characters allowed is <b>NTSTRSAFE_MAX_CCH</b>. 


### -param pszFormat [in]

A pointer to a null-terminated text string that contains <b>printf</b>-styled <a href="https://docs.microsoft.com/cpp/c-runtime-library/format-specification-syntax-printf-and-wprintf-functions">formatting directives</a>.


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
<li>The value in <i>cchDest </i> is larger than the maximum buffer size.</li>
<li>The destination buffer was already full.</li>
<li>A <b>NULL</b> pointer was present.</li>
<li>The destination buffer's length was zero, but a nonzero length source string was present.</li>
</ul>
</td>
</tr>
</table>
 




## -remarks



<b>RtlStringCchPrintfW</b> and <b>RtlStringCchPrintfA</b> should be used instead of the following functions:

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
All of these functions accept a format string and a list of arguments and return a formatted string. <b>RtlStringCchPrintfW</b> and <b>RtlStringCchPrintfA</b> accept the size, in characters, of the destination buffer to ensure that the functions do not write past the end of the buffer.

Use <b>RtlStringCchPrintfW</b> to handle Unicode strings and <b>RtlStringCchPrintfA</b> to handle ANSI strings. The form you use depends on your data.

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
<b>RtlStringCchPrintfW</b>

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
<b>RtlStringCchPrintfA</b>

</td>
</tr>
</table>
 

If  <i>pszDest </i>and <i>pszFormat</i> point to overlapping strings, or if any argument strings overlap, behavior of the function is undefined.

Neither <i>pszFormat</i> nor <i>pszDest</i> can be <b>NULL</b>. If you need to handle <b>NULL</b> string pointer values, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntstrsafe/nf-ntstrsafe-rtlstringcchprintfexa">RtlStringCchPrintfEx</a>.


#### Examples

The following example shows a simple use of <b>RtlStringCchPrintfW</b> using four arguments.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WCHAR pszDest[30]; 
size_t cchDest = 30;

LPCWSTR pszFormat = L"%s %d + %d = %d.";
WCHAR* pszTxt = L"The answer is";

NTSTATUS status = 
    RtlStringCchPrintfW(pszDest, cchDest, pszFormat, pszTxt, 1, 2, 3);</pre>
</td>
</tr>
</table></span></div>
The resultant string is "The answer is 1 + 2 = 3." It is contained in the buffer at <i>pszDest</i>.

For more information about the safe string functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-safe-string-functions">Using Safe String Functions</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntstrsafe/nf-ntstrsafe-rtlstringcbprintfa">RtlStringCbPrintf</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntstrsafe/nf-ntstrsafe-rtlstringcchprintfexa">RtlStringCchPrintfEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntstrsafe/nf-ntstrsafe-rtlstringcchvprintfa">RtlStringCchVPrintf</a>
 

 

