---
UID: NF:ntstrsafe.RtlStringCchCopyW
title: RtlStringCchCopyW function
author: windows-driver-content
description: The RtlStringCchCopyW and RtlStringCchCopyA functions copy a null-terminated source string into a destination buffer of specified length.
old-location: kernel\rtlstringcchcopy.htm
old-project: kernel
ms.assetid: d5c6d7d2-fe14-49d5-9e81-3a425a4cf1b3
ms.author: windowsdriverdev
ms.date: 2/24/2018
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ntstrsafe.lib
-	Ntstrsafe.dll
apiname:
-	RtlStringCchCopyW
-	RtlStringCchCopyA
-	RtlStringCchCopyW
product: Windows
targetos: Windows
req.typenames: SYSTEM_POWER_STATE_CONTEXT, *PSYSTEM_POWER_STATE_CONTEXT
---

# RtlStringCchCopyW function


## -description


The <b>RtlStringCchCopyW</b> and <b>RtlStringCchCopyA</b> functions copy a null-terminated source string into a destination buffer of specified length. 


## -syntax


````
NTSTATUS RtlStringCchCopyW(
  _Out_ LPTSTR  pszDest,
  _In_  size_t  cchDest,
  _In_  LPCTSTR pszSrc
);
````


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
These functions are not replacements for <b>strncpy</b>. Use <a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchcopynw.md">RtlStringCchCopyN</a> or <a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchcopynexw.md">RtlStringCchCopyNEx</a> to replace <b>strncpy</b>.

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

Neither <i>pszSrc</i> nor <i>pszDest</i> can be <b>NULL</b>. If you need to handle <b>NULL</b> string pointer values, use <a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchcopyexw.md">RtlStringCchCopyEx</a>.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>.




## -see-also

<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbcopyw.md">RtlStringCbCopy</a>



<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchcopyexw.md">RtlStringCchCopyEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlStringCchCopyW function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

