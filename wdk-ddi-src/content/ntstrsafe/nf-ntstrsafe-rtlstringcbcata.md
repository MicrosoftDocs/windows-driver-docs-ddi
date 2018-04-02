---
UID: NF:ntstrsafe.RtlStringCbCatA
title: RtlStringCbCatA function
author: windows-driver-content
description: The RtlStringCbCatW and RtlStringCbCatA functions concatenate two byte-counted strings.
old-location: kernel\rtlstringcbcat.htm
old-project: kernel
ms.assetid: 1034384f-6295-42ca-bf78-47c383417500
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlStringCbCat, RtlStringCbCatA, RtlStringCbCatW, RtlStringCbCatW function [Kernel-Mode Driver Architecture], kernel.rtlstringcbcat, ntstrsafe/RtlStringCbCatA, ntstrsafe/RtlStringCbCatW, safestrings_31bee145-512e-4daa-87c3-98abc5e88b2b.xml
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
req.unicode-ansi: RtlStringCbCatW (Unicode) and RtlStringCbCatA (ANSI)
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
-	RtlStringCbCatW
-	RtlStringCbCatA
-	RtlStringCbCatW
product:
- Windows
targetos: Windows
req.typenames: SYSTEM_POWER_STATE_CONTEXT, *PSYSTEM_POWER_STATE_CONTEXT
---

# RtlStringCbCatA function


## -description


The <b>RtlStringCbCatW</b> and <b>RtlStringCbCatA</b> functions concatenate two byte-counted strings.


## -parameters




### -param pszDest [in, out]

A pointer to a buffer which, on input, contains a null-terminated string to which <i>pszSrc</i> will be concatenated. On output, this is the destination buffer that contains the entire resultant string. The string at <i>pszSrc</i> is added to the end of the string at <i>pszDest</i> and terminated with a null character. 


### -param cbDest [in]

The size of the destination buffer, in bytes. The destination buffer must be large enough to include the concatenated strings and the terminating null character. 

For Unicode strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * sizeof(WCHAR).

For ANSI strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * sizeof(char).


### -param pszSrc [in]

A pointer to a null-terminated string. This string will be concatenated to the end of the string that is contained in the buffer at <i>pszDest</i>.


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
This <i>success</i> status means source data was present, the strings were concatenated without truncation, and the resultant destination buffer is null-terminated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
This <i>warning</i> status means the concatenation operation did not complete due to insufficient buffer space. The destination buffer contains a truncated, null-terminated version of the intended result.

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

The STATUS_INVALID_PARAMETER return value means that one of the following occurred:

<ul>
<li>The value in <i>cbDest</i> is larger than the maximum buffer size.</li>
<li>The destination buffer was already full.</li>
<li>A <b>NULL</b> pointer was present.</li>
<li>The destination buffer length was zero, but a nonzero length source string was present.</li>
</ul>
</td>
</tr>
</table>
 




## -remarks



<b>RtlStringCbCatW</b> and <b>RtlStringCbCatA</b> should be used instead of the following functions:

<ul>
<li>
<b>strcat</b>

</li>
<li>
<b>wcscat</b>

</li>
</ul>
Because <b>RtlStringCbCatW</b> and <b>RtlStringCbCatA </b>receive the size of the destination buffer as input, they will not write past the end of the buffer. 

Use <b>RtlStringCbCatW</b> to handle Unicode strings and <b>RtlStringCbCatA</b> to handle ANSI strings. The form to use is determined by your data as shown in the following table.

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
<b>RtlStringCbCatW</b>

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
<b>RtlStringCbCatA</b>

</td>
</tr>
</table>
 

If <i>pszSrc</i> and <i>pszDest</i> point to strings that overlap, the behavior of the functions is undefined.

Neither <i>pszSrc</i> nor <i>pszDest</i> can be <b>NULL</b>. If you need to handle <b>NULL</b> string pointer values, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff562802">RtlStringCbCatNEx</a>.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562799">RtlStringCbCatEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562802">RtlStringCbCatNEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562835">RtlStringCchCatEx</a>
 

 

