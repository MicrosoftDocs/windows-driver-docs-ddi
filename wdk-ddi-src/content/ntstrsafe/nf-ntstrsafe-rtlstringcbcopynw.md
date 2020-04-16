---
UID: NF:ntstrsafe.RtlStringCbCopyNW
title: RtlStringCbCopyNW function (ntstrsafe.h)
description: The RtlStringCbCopyNW and RtlStringCbCopyNA functions copy a byte-counted string to a buffer while limiting the size of the copied string.
old-location: kernel\rtlstringcbcopyn.htm
tech.root: kernel
ms.assetid: d64fb3e6-fba1-4383-bdb0-a63dc7c16033
ms.date: 04/30/2018
keywords: ["RtlStringCbCopyNW function"]
ms.keywords: RtlStringCbCopyN, RtlStringCbCopyNA, RtlStringCbCopyNW, RtlStringCbCopyNW function [Kernel-Mode Driver Architecture], kernel.rtlstringcbcopyn, ntstrsafe/RtlStringCbCopyNA, ntstrsafe/RtlStringCbCopyNW, safestrings_a3f7f7a8-b4a1-4c7c-b384-2243b3c97a4e.xml
f1_keywords:
 - "ntstrsafe/RtlStringCbCopyNW"
req.header: ntstrsafe.h
req.include-header: Ntstrsafe.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP with Service Pack 1 (SP1) and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: RtlStringCbCopyNW (Unicode) and RtlStringCbCopyNA (ANSI)
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
- RtlStringCbCopyNW
- RtlStringCbCopyNA
- RtlStringCbCopyNW
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlStringCbCopyNW function


## -description


The <b>RtlStringCbCopyNW</b> and <b>RtlStringCbCopyNA</b> functions copy a byte-counted string to a buffer while limiting the size of the copied string.


## -parameters




### -param pszDest [out]

A pointer to a caller-supplied buffer that receives the copied string. The string at <i>pszSrc</i>, up to <i>cbSrc</i> bytes, is copied to the buffer at <i>pszDest</i> and terminated with a null character. 


### -param cbDest [in]

The size, in bytes, of the destination buffer. The buffer must be large enough for both the string and the terminating null character.

For Unicode strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * <b>sizeof</b>(WCHAR). 

For ANSI strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * <b>sizeof</b>(<b>char</b>). 


### -param pszSrc [in]

A pointer to a caller-supplied, null-terminated string. 


### -param cbToCopy

<p>The maximum number of bytes to copy from <i>pszSrc</i> to <i>pszDest</i>.</p>




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
<li>The value in <i>cbDest</i> is larger than the maximum buffer size.</li>
<li>The destination buffer was already full.</li>
<li>A <b>NULL</b> pointer was present.</li>
<li>The destination buffer's length was zero, but a nonzero length source string was present.</li>
</ul>
</td>
</tr>
</table>
 




## -remarks



<b>RtlStringCbCopyNW</b> and <b>RtlStringCbCopyNA</b> should be used instead of <b>strncpy</b>. However, these functions  differ in behavior. If <i>cbSrc</i> is larger than the number of bytes in <i>pszSrc</i>, the <b>RtlStringCbCopyN </b>functions—unlike <b>strncpy</b>—do not fill <i>pszDest</i> with null characters until <i>cbSrc</i> bytes have been copied.

<b>RtlStringCbCopyN</b> copies a given number of bytes from a source string. The size, in bytes, of the destination buffer is provided to the function to ensure that <b>RtlStringCbCopyN</b> does not write past the end of this buffer.

Use <b>RtlStringCbCopyNW</b> to handle Unicode strings and <b>RtlStringCbCopyNA</b> to handle ANSI strings. The form you use depends on your data, as shown in the following table.

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
<b>RtlStringCbCopyNW</b>

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
<b>RtlStringCbCopyNA</b>

</td>
</tr>
</table>
 

If <i>pszSrc</i> and <i>pszDest</i> point to overlapping strings, the behavior of the function is undefined.

Neither <i>pszSrc</i> nor <i>pszDest</i> can be <b>NULL</b>. If you need to handle <b>NULL</b> string pointer values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlstringcbcopynexa">RtlStringCbCopyNEx</a>.

For more information about the safe string functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-safe-string-functions">Using Safe String Functions</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlstringcbcopya">RtlStringCbCopy</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlstringcbcopynexa">RtlStringCbCopyNEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlstringcchcopyna">RtlStringCchCopyN</a>
 

 

