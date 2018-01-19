---
UID: NF:ntstrsafe.RtlStringCbCatW
title: RtlStringCbCatW function
author: windows-driver-content
description: The RtlStringCbCatW and RtlStringCbCatA functions concatenate two byte-counted strings.
old-location: kernel\rtlstringcbcat.htm
old-project: kernel
ms.assetid: 1034384f-6295-42ca-bf78-47c383417500
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlStringCbCatW
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
req.alt-api: RtlStringCbCatW,RtlStringCbCatA,RtlStringCbCatW
req.alt-loc: Ntstrsafe.lib,Ntstrsafe.dll
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
req.typenames: *PBATTERY_REPORTING_SCALE, BATTERY_REPORTING_SCALE
---

# RtlStringCbCatW function



## -description
The <b>RtlStringCbCatW</b> and <b>RtlStringCbCatA</b> functions concatenate two byte-counted strings.



## -syntax

````
NTSTATUS RtlStringCbCatW(
  _Inout_ LPTSTR  pszDest,
  _In_    size_t  cbDest,
  _In_    LPCTSTR pszSrc
);
````


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
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>This <i>success</i> status means source data was present, the strings were concatenated without truncation, and the resultant destination buffer is null-terminated.
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>This <i>warning</i> status means the concatenation operation did not complete due to insufficient buffer space. The destination buffer contains a truncated, null-terminated version of the intended result.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>This <i>error</i> status means the function received an invalid input parameter. For more information, see the following paragraph.

The STATUS_INVALID_PARAMETER return value means that one of the following occurred:

 


## -remarks
<b>RtlStringCbCatW</b> and <b>RtlStringCbCatA</b> should be used instead of the following functions:

<b>strcat</b>

<b>wcscat</b>

Because <b>RtlStringCbCatW</b> and <b>RtlStringCbCatA </b>receive the size of the destination buffer as input, they will not write past the end of the buffer. 

Use <b>RtlStringCbCatW</b> to handle Unicode strings and <b>RtlStringCbCatA</b> to handle ANSI strings. The form to use is determined by your data as shown in the following table.

WCHAR

L"string"

<b>RtlStringCbCatW</b>

<b>char</b>

"string"

<b>RtlStringCbCatA</b>

If <i>pszSrc</i> and <i>pszDest</i> point to strings that overlap, the behavior of the functions is undefined.

Neither <i>pszSrc</i> nor <i>pszDest</i> can be <b>NULL</b>. If you need to handle <b>NULL</b> string pointer values, use <a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbcatnexw.md">RtlStringCbCatNEx</a>.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>.


## -see-also
<dl>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbcatexw.md">RtlStringCbCatEx</a>
</dt>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchcatexw.md">RtlStringCchCatEx</a>
</dt>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbcatnexw.md">RtlStringCbCatNEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlStringCbCatW function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

