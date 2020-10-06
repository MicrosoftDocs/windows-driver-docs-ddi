---
UID: NF:ntstrsafe.RtlStringCchCatW
title: RtlStringCchCatW function (ntstrsafe.h)
description: The RtlStringCchCatW and RtlStringCchCatA functions concatenate two character-counted strings.
old-location: kernel\rtlstringcchcat.htm
tech.root: kernel
ms.assetid: 4d2d0c14-a311-4235-9ceb-4b703ef602fe
ms.date: 04/30/2018
keywords: ["RtlStringCchCatW function"]
ms.keywords: RtlStringCchCat, RtlStringCchCatA, RtlStringCchCatW, RtlStringCchCatW function [Kernel-Mode Driver Architecture], kernel.rtlstringcchcat, ntstrsafe/RtlStringCchCatA, ntstrsafe/RtlStringCchCatW, safestrings_03a0e306-3b4e-4808-b257-a8327b688a08.xml
req.header: ntstrsafe.h
req.include-header: Ntstrsafe.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP with Service Pack 1 (SP1) and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: RtlStringCchCatW (Unicode) and RtlStringCchCatA (ANSI)
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntstrsafe.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlStringCchCatW
 - ntstrsafe/RtlStringCchCatW
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ntstrsafe.lib
 - Ntstrsafe.dll
api_name:
 - RtlStringCchCatW
 - RtlStringCchCatA
 - RtlStringCchCatW
---

# RtlStringCchCatW function


## -description

The <b>RtlStringCchCatW</b> and <b>RtlStringCchCatA</b> functions concatenate two character-counted strings.

## -parameters

### -param pszDest 

[in, out]
A pointer to a buffer which, on input, contains a null-terminated string to which <i>pszSrc</i> will be concatenated. On output, this is the destination buffer that contains the entire resultant string. The string at <i>pszSrc</i> is added to the end of the string at <i>pszDest</i> and terminated with a null character.

### -param cchDest 

[in]
The size, in characters, of the destination buffer. The maximum number of characters allowed is NTSTRSAFE_MAX_CCH.

### -param pszSrc 

[in]
A pointer to a null-terminated string. This string will be concatenated to the end of the string that is contained in the buffer at <i>pszDest</i>.

## -returns

The function returns one of the NTSTATUS values that are listed in the following table. For information about how to test NTSTATUS values, see <a href="/windows-hardware/drivers/kernel/using-ntstatus-values">Using NTSTATUS Values</a>.

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
This <i>warning</i> status means the operation did not complete due to insufficient space in the destination buffer. The destination buffer contains a truncated, null-terminated version of the intended result.

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
<li>The destination buffer pointer was <b>NULL</b>, but the buffer size was not zero.</li>
<li>The destination buffer length was zero, but a nonzero length source string was present.</li>
</ul>
</td>
</tr>
</table>

## -remarks

<b>RtlStringCchCatW</b> and <b>RtlStringCchCatA</b> should be used instead of the following functions: 

<ul>
<li>
<b>strcat</b>

</li>
<li>
<b>wcscat</b>

</li>
</ul>
The size, in characters, of the destination buffer is provided to ensure that <b>RtlStringCchCatW</b> and <b>RtlStringCchCatA</b> do not write past the end of the buffer.

Use <b>RtlStringCchCatW</b> to handle Unicode strings and <b>RtlStringCchCatA</b> to handle ANSI strings. The form you use depends on your data, as shown in the following table.

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
<b>RtlStringCchCatW</b>

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
<b>RtlStringCchCatA</b>

</td>
</tr>
</table>
 

If  <i>pszSrc</i> and <i>pszDest</i> point to overlapping strings, the behavior of the function is undefined.

Neither <i>pszSrc</i> nor <i>pszDest</i> can be <b>NULL</b>. If you need to handle <b>NULL</b> string pointer values, use <a href="/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlstringcchcatexa">RtlStringCchCatEx</a>.

For more information about the safe string functions, see <a href="/windows-hardware/drivers/kernel/using-safe-string-functions">Using Safe String Functions</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlstringcbcata">RtlStringCbCat</a>



<a href="/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlstringcchcatexa">RtlStringCchCatEx</a>



<a href="/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlstringcchcatna">RtlStringCchCatN</a>