---
UID: NF:ntstrsafe.RtlStringCchCatNA
title: RtlStringCchCatNA function
author: windows-driver-content
description: The RtlStringCchCatNW and RtlStringCchCatNA functions concatenate two character-counted strings while limiting the size of the appended string.
old-location: kernel\rtlstringcchcatn.htm
old-project: kernel
ms.assetid: 2cd45c9e-b9dd-47fb-a480-63258b2fccd4
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , A, C, N, R, RtlStringCchCatN, RtlStringCchCatNA, RtlStringCchCatNW, RtlStringCchCatNW function [Kernel-Mode Driver Architecture], S, a, c, g, h, i, kernel.rtlstringcchcatn, l, n, ntstrsafe/RtlStringCchCatNA, ntstrsafe/RtlStringCchCatNW, r, safestrings_499b4858-de9a-4be2-a82d-de2da48d37f5.xml, t"
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
req.unicode-ansi: RtlStringCchCatNW (Unicode) and RtlStringCchCatNA (ANSI)
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntstrsafe.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ntstrsafe.lib
-	Ntstrsafe.dll
apiname:
-	RtlStringCchCatNW
-	RtlStringCchCatNA
-	RtlStringCchCatNW
product: Windows
targetos: Windows
req.typenames: SYSTEM_POWER_STATE_CONTEXT, *PSYSTEM_POWER_STATE_CONTEXT
---

# RtlStringCchCatNA function


## -description


The <b>RtlStringCchCatNW</b> and <b>RtlStringCchCatNA</b> functions concatenate two character-counted strings while limiting the size of the appended string. 


## -syntax


````
NTSTATUS RtlStringCchCatNW(
  _Inout_ LPTSTR  pszDest,
  _In_    size_t  cchDest,
  _In_    LPCTSTR pszSrc,
  _In_    size_t  cchMaxAppend
);
````


## -parameters




### -param pszDest [in, out]

A pointer to a buffer which, on input, contains a null-terminated string to which <i>pszSrc</i> will be concatenated. On output, this is the destination buffer that contains the entire resultant string. The string at <i>pszSrc</i>, up to <i>cchMaxAppend</i> characters, is added to the end of the string at <i>pszDest</i> and terminated with a null character.


### -param cchDest [in]

The size of the destination buffer, in characters. The maximum number of characters allowed is NTSTRSAFE_MAX_CCH. 


### -param pszSrc [in]

A pointer to a null-terminated string. This string will be concatenated to the end of the string that is contained in the buffer at <i>pszDest</i>. 


### -param cchToAppend

TBD




#### - cchMaxAppend [in]

The maximum number of characters to append to the string that is contained in the buffer at <i>pszDest</i>.


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



<b>RtlStringCchCatNW</b> and <b>RtlStringCchCatNA</b> should be used instead of the following functions: 

<ul>
<li>
<b>strncat</b>

</li>
<li>
<b>wcsncat</b>

</li>
</ul>
The size, in characters, of the destination buffer is provided to the function to ensure that <b>RtlStringCchCatNW</b> and <b>RtlStringCchCatNA</b> do not write past the end of the buffer.

Use <b>RtlStringCchCatNW</b> to handle Unicode strings and <b>RtlStringCchCatNA</b> to handle ANSI strings. The form you use depends on your data, as shown in the following table.

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
<b>RtlStringCchCatNW</b>

</td>
</tr>
<tr>
<td>
<b>char
       </b>

</td>
<td>
"string"

</td>
<td>
<b>RtlStringCchCatNA</b>

</td>
</tr>
</table>
 

If  <i>pszSrc</i> and <i>pszDest</i> point to overlapping strings, the behavior of the function is undefined.

Neither <i>pszSrc</i> nor <i>pszDest</i> can be <b>NULL</b>. If you need to handle <b>NULL</b> string pointer values, use <a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchcatnexw.md">RtlStringCchCatNEx</a>.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>.




## -see-also

<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchcatw.md">RtlStringCchCat</a>



<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbcatnw.md">RtlStringCbCatN</a>



<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchcatnexw.md">RtlStringCchCatNEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlStringCchCatNW function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

