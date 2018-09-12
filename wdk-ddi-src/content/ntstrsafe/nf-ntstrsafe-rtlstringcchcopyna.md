---
UID: NF:ntstrsafe.RtlStringCchCopyNA
title: RtlStringCchCopyNA function
author: windows-driver-content
description: The RtlStringCchCopyNW and RtlStringCchCopyNA functions copy a character-counted string to a buffer while limiting the size of the copied string.
old-location: kernel\rtlstringcchcopyn.htm
tech.root: kernel
ms.assetid: 86ec1a98-d70f-437c-9c8b-005bf78375ba
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: RtlStringCchCopyN, RtlStringCchCopyNA, RtlStringCchCopyNW, RtlStringCchCopyNW function [Kernel-Mode Driver Architecture], kernel.rtlstringcchcopyn, ntstrsafe/RtlStringCchCopyNW, safestrings_6ecbc673-80c3-4568-a6e3-96865035bfed.xml
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
req.unicode-ansi: RtlStringCchCopyNW (Unicode) and RtlStringCchCopyNW (ANSI)
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
-	RtlStringCchCopyNW
-	RtlStringCchCopyNW
-	RtlStringCchCopyNW
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlStringCchCopyNA function


## -description


The <b>RtlStringCchCopyNW</b> and <b>RtlStringCchCopyNA</b> functions copy a character-counted string to a buffer while limiting the size of the copied string.


## -parameters




### -param pszDest [out]

A pointer to a caller-supplied buffer that receives the copied string. The string at <i>pszSrc</i>, up to <i>cchSrc</i> characters, is copied to the buffer at <i>pszDest</i> and terminated with a null character.


### -param cchDest [in]

The size of the destination buffer, in characters. The maximum number of characters allowed is NTSTRSAFE_MAX_CCH.


### -param pszSrc [in]

A pointer to a caller-supplied, null-terminated string. 


### -param cchToCopy

<p>The maximum number of characters to copy from <i>pszSrc</i> to the buffer that is supplied by <i>pszDest</i>.</p>




#### - cchSrc [in]

The maximum number of characters to copy from <i>pszSrc</i> to the buffer that is supplied by <i>pszDest</i>.


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
This <i>warning</i> status means the copy operation did not complete due to insufficient space in the destination buffer. The destination buffer contains a truncated version of the copied string.

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
<li>The value in <i>cchDest</i>  is larger than the maximum buffer size.</li>
<li>The destination buffer was already full.</li>
<li>A <b>NULL</b> pointer was present.</li>
<li>The destination buffer's length was zero, but a nonzero length source string was present.</li>
</ul>
</td>
</tr>
</table>
 




## -remarks



<b>RtlStringCchCopyNW</b> and <b>RtlStringCchCopyNA</b> should be used instead of <b>strncpy</b>. 

The functions copy a given number of characters from a source string. <b>RtlStringCchCopyNW</b> and <b>RtlStringCchCopyNA</b> receive the size, in characters, of the destination buffer to ensure that the functions do not write past the end of the buffer.

Note that these functions behave differently from <b>strncpy</b> in one respect. If <i>cchSrc</i> is larger than the number of characters in <i>pszSrc</i>, <b>RtlStringCchCopyNW</b> and <b>RtlStringCchCopyNA</b>—unlike <b>strncpy</b>—do not continue to pad <i>pszDest</i> with null characters until <i>cchSrc</i> characters have been copied.

Use <b>RtlStringCchCopyNW</b> to handle Unicode strings and <b>RtlStringCchCopyNA</b> to handle ANSI strings. The form you use depends on your data, as shown in the following table.

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
<b>RtlStringCchCopyNW</b>

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
<b>RtlStringCchCopyNA</b>

</td>
</tr>
</table>
 

If <i>pszSrc</i> and <i>pszDest</i> point to overlapping strings, the behavior of the function is undefined.

Neither <i>pszSrc</i> nor <i>pszDest</i> can be <b>NULL</b>. If you need to handle <b>NULL</b> string pointer values, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff562849">RtlStringCchCopyNEx</a>.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562811">RtlStringCbCopyN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562841">RtlStringCchCopy</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562849">RtlStringCchCopyNEx</a>
 

 

