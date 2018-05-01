---
UID: NF:ntstrsafe.RtlStringCbCopyW
title: RtlStringCbCopyW function
author: windows-driver-content
description: The RtlStringCbCopyW and RtlStringCbCopyA functions copy a byte-counted string into a buffer.
old-location: kernel\rtlstringcbcopy.htm
old-project: kernel
ms.assetid: 77a42d5e-92ff-4e64-9bd3-b713286d3db0
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: RtlStringCbCopy, RtlStringCbCopyA, RtlStringCbCopyW, RtlStringCbCopyW function [Kernel-Mode Driver Architecture], kernel.rtlstringcbcopy, ntstrsafe/RtlStringCbCopyA, ntstrsafe/RtlStringCbCopyW, safestrings_a9c53388-15ef-4140-8931-ca93d519a7d4.xml
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
req.unicode-ansi: RtlStringCbCopyW (Unicode) and RtlStringCbCopyA (ANSI)
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
-	RtlStringCbCopyW
-	RtlStringCbCopyA
-	RtlStringCbCopyW
product: Windows
targetos: Windows
req.typenames: 
---

# RtlStringCbCopyW function


## -description


The <b>RtlStringCbCopyW</b> and <b>RtlStringCbCopyA</b> functions copy a byte-counted string into a buffer. 


## -parameters




### -param pszDest [out]

A pointer to a caller-supplied buffer that receives the copied string. The string at <i>pszSrc</i> is copied to the buffer at <i>pszDest</i> and terminated with a null character.


### -param cbDest [in]

The size, in bytes, of the destination buffer. The buffer must be large enough for the string and the terminating null character.

For Unicode strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * sizeof(WCHAR). 

For ANSI strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * sizeof(char). 


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
<li>The value in <i>cbDest</i> is larger than the maximum buffer size.</li>
<li>The destination buffer was already full.</li>
<li>A <b>NULL</b> pointer was present.</li>
<li>The destination buffer's length was zero, but a nonzero length source string was present.</li>
</ul>
</td>
</tr>
</table>
 




## -remarks



<b>RtlStringCbCopyA</b> and <b>RtlStringCbCopyW</b> should be used instead of the following functions: 

<ul>
<li>
<b>strcpy</b>

</li>
<li>
<b>wcscpy</b>

</li>
</ul>
<b>RtlStringCbCopyA</b> and <b>RtlStringCbCopyW</b> are not replacements for <b>strncpy</b>. To replace <b>strncpy</b>, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff562811">RtlStringCbCopyN</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff562813">RtlStringCbCopyNEx</a>.

The size of the destination buffer is provided to the function to ensure that <b>RtlStringCbCopy</b> does not write past the end of the buffer.

Use <b>RtlStringCbCopyW</b> to handle Unicode strings and <b>RtlStringCbCopyA</b> to handle ANSI strings. The form you use depends on your data as shown in the following table.

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
<b>RtlStringCbCopyW</b>

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
<b>RtlStringCbCopyA</b>

</td>
</tr>
</table>
 

If <i>pszSrc</i> and <i>pszDest</i> point to overlapping strings, the behavior of the function is undefined.

Neither <i>pszSrc</i> nor <i>pszDest</i> can be <b>NULL</b>. If you need to handle <b>NULL</b> string pointer values, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff562807">RtlStringCbCopyEx</a>.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562807">RtlStringCbCopyEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562841">RtlStringCchCopy</a>
 

 

