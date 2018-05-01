---
UID: NF:ntstrsafe.RtlStringCchCopyA
title: RtlStringCchCopyA function
author: windows-driver-content
description: The RtlStringCchCopyW and RtlStringCchCopyA functions copy a null-terminated source string into a destination buffer of specified length.
old-location: kernel\rtlstringcchcopy.htm
old-project: kernel
ms.assetid: d5c6d7d2-fe14-49d5-9e81-3a425a4cf1b3
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: RtlStringCchCopy, RtlStringCchCopyA, RtlStringCchCopyW, RtlStringCchCopyW function [Kernel-Mode Driver Architecture], kernel.rtlstringcchcopy, ntstrsafe/RtlStringCchCopyA, ntstrsafe/RtlStringCchCopyW, safestrings_75c329c3-0463-4c8f-a363-ac26ec15c923.xml
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
req.unicode-ansi: RtlStringCchCopyW (Unicode) and RtlStringCchCopyA (ANSI)
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
-	RtlStringCchCopyW
-	RtlStringCchCopyA
-	RtlStringCchCopyW
product: Windows
targetos: Windows
req.typenames: 
---

# RtlStringCchCopyA function


## -description


The <b>RtlStringCchCopyW</b> and <b>RtlStringCchCopyA</b> functions copy a null-terminated source string into a destination buffer of specified length. 


## -parameters




### -param pszDest [out]

A pointer to a caller-supplied buffer that receives the copied string. The string at <i>pszSrc</i> is copied to the buffer at <i>pszDest</i> and terminated with a null character.


### -param cchDest [in]

The size, in characters, of the destination buffer. The maximum number of characters allowed is NTSTRSAFE_MAX_CCH. 


### -param pszSrc [in]

A pointer to a caller-supplied, null-terminated string.


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
This <i>success</i> status means source data was present, the string was copied without truncation, and the resultant destination buffer is null-terminated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
This <i>warning</i> status means the copy operation did not complete due to insufficient buffer space. The destination buffer contains a truncated, null-terminated version of the intended result.

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
<li>The value in <i>cchDest</i> is larger than the maximum buffer size.</li>
<li>A <b>NULL</b> pointer was present.</li>
<li>The destination buffer length was zero at entry.</li>
</ul>
</td>
</tr>
</table>
 




## -remarks



<b>RtlStringCchCopyW</b> and <b>RtlStringCchCopyA</b> should be used instead of the following functions: 

<ul>
<li>
<b>strcpy</b>

</li>
<li>
<b>wcscpy</b>

</li>
</ul>
These functions are not replacements for <b>strncpy</b>. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff562846">RtlStringCchCopyN</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff562849">RtlStringCchCopyNEx</a> to replace <b>strncpy</b>.

The size, in characters, of the destination buffer is provided to <b>RtlStringCchCopyW</b> and <b>RtlStringCchCopyA</b> to ensure that they do not write past the end of the buffer.

Use <b>RtlStringCchCopyW</b> to handle Unicode strings and <b>RtlStringCchCopyA</b> to handle ANSI strings. The form you use depends your data, as shown in the following table.

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
<b>RtlStringCchCopyW</b>

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
<b>RtlStringCchCopyA</b>

</td>
</tr>
</table>
 

If <i>pszSrc</i> and <i>pszDest</i> point to overlapping strings, the behavior of the function is undefined.

Neither <i>pszSrc</i> nor <i>pszDest</i> can be <b>NULL</b>. If you need to handle <b>NULL</b> string pointer values, use <a href="https://msdn.microsoft.com/c8abf741-ea8c-46d3-85f5-0cc38f1a5ea7">RtlStringCchCopyEx</a>.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562805">RtlStringCbCopy</a>



<a href="https://msdn.microsoft.com/c8abf741-ea8c-46d3-85f5-0cc38f1a5ea7">RtlStringCchCopyEx</a>
 

 

