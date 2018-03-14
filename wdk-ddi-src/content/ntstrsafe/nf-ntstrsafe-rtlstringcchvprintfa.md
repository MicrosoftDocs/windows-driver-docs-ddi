---
UID: NF:ntstrsafe.RtlStringCchVPrintfA
title: RtlStringCchVPrintfA function
author: windows-driver-content
description: The RtlStringCchVPrintfW and RtlStringCchVPrintfA functions create a character-counted text string, with formatting that is based on supplied formatting information.
old-location: kernel\rtlstringcchvprintf.htm
old-project: kernel
ms.assetid: a3552042-15e6-4778-8026-a4b615228dc7
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: RtlStringCchVPrintf, RtlStringCchVPrintfA, RtlStringCchVPrintfW, RtlStringCchVPrintfW function [Kernel-Mode Driver Architecture], kernel.rtlstringcchvprintf, ntstrsafe/RtlStringCchVPrintfA, ntstrsafe/RtlStringCchVPrintfW, safestrings_7e5dc683-a092-4540-a6e5-81b72bae11ec.xml
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
req.unicode-ansi: RtlStringCchVPrintfW (Unicode) and RtlStringCchVPrintfA (ANSI)
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
-	RtlStringCchVPrintfW
-	RtlStringCchVPrintfA
-	RtlStringCchVPrintfW
product: Windows
targetos: Windows
req.typenames: SYSTEM_POWER_STATE_CONTEXT, *PSYSTEM_POWER_STATE_CONTEXT
---

# RtlStringCchVPrintfA function


## -description


The <b>RtlStringCchVPrintfW</b> and <b>RtlStringCchVPrintfA</b> functions create a character-counted text string, with formatting that is based on supplied formatting information.


## -syntax


````
NTSTATUS RtlStringCchVPrintfW(
  _Out_ LPTSTR  pszDest,
  _In_  size_t  cchDest,
  _In_  LPCTSTR pszFormat,
  _In_  va_list argList
);
````


## -parameters




### -param pszDest [out]

A pointer to a caller-supplied buffer that receives a formatted, null-terminated string. The function creates this string from both the formatting string that is supplied by <i>pszFormat</i> and the arguments supplied by <i>argList</i>.


### -param cchDest [in]

The size of the destination buffer, in characters. The buffer must be large enough to contain the formatted string plus the terminating null character. The maximum number of characters allowed is NTSTRSAFE_MAX_CCH.


### -param pszFormat [in]

A pointer to a null-terminated text string that contains <b>printf</b>-styled formatting directives.


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
This <i>warning</i> status means the operation did not complete due to insufficient space in the destination buffer. The destination buffer contains a truncated version of the created string.

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
<li>The value in <i>cchDest  </i> is larger than the maximum buffer size.</li>
<li>The destination buffer was already full.</li>
<li>A <b>NULL</b> pointer was present.</li>
<li>The destination buffer length was zero, but a nonzero length source string was present.</li>
</ul>
</td>
</tr>
</table>
 




## -remarks



<b>RtlStringCchVPrintfW</b> and <b>RtlStringCchVPrintfA</b> should be used instead of the following functions: 

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
All of these functions accept a format string and its arguments, which are provided as a <b>va_list</b>-typed argument list, and return a formatted string. <b>RtlStringCchVPrintfW</b> and <b>RtlStringCchVPrintfA</b> receive the size, in characters, of the destination buffer to ensure that the functions do not write past the end of the buffer.

For more information about <b>va_list</b>-typed argument lists, see the Microsoft Windows SDK documentation.

Use <b>RtlStringCchVPrintfW</b> to handle Unicode strings and <b>RtlStringCchVPrintfA</b> to handle ANSI strings. The form you  use depends on your data, as shown in the following table.

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
<b>RtlStringCchVPrintfW</b>

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
<b>RtlStringCchVPrintfA</b>

</td>
</tr>
</table>
 

If <i>pszDest</i> and <i>pszFormat</i> point to overlapping strings, or if any argument strings overlap, the behavior of the function is undefined.

Neither <i>pszFormat</i> nor <i>pszDest</i> can be <b>NULL</b>. If you need to handle <b>NULL</b> string pointer values, use <a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchvprintfexw.md">RtlStringCchVPrintfEx</a>.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>.




## -see-also

<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbvprintfw.md">RtlStringCbVPrintf</a>



<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchprintfw.md">RtlStringCchPrintf</a>



<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchvprintfexw.md">RtlStringCchVPrintfEx</a>



 

 


