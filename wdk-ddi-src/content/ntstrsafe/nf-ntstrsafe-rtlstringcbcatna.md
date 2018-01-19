---
UID: NF:ntstrsafe.RtlStringCbCatNA
title: RtlStringCbCatNA function
author: windows-driver-content
description: The RtlStringCbCatNW and RtlStringCbCatNA functions concatenate two byte-counted strings while limiting the size of the appended string.
old-location: kernel\rtlstringcbcatn.htm
old-project: kernel
ms.assetid: 60ecabb1-5607-4962-82c6-8081916b507d
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlStringCbCatNA
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
req.alt-api: RtlStringCbCatNW,RtlStringCbCatNA,RtlStringCbCatNW
req.alt-loc: Ntstrsafe.lib,Ntstrsafe.dll
req.ddi-compliance: 
req.unicode-ansi: RtlStringCbCatNW (Unicode) and RtlStringCbCatNA (ANSI)
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

# RtlStringCbCatNA function



## -description
The <b>RtlStringCbCatNW</b> and <b>RtlStringCbCatNA</b> functions concatenate two byte-counted strings while limiting the size of the appended string. 



## -syntax

````
NTSTATUS RtlStringCbCatNW(
  _Inout_ LPTSTR  pszDest,
  _In_    size_t  cbDest,
  _In_    LPCTSTR pszSrc,
  _In_    size_t  cbMaxAppend
);
````


## -parameters

### -param pszDest [in, out]

Pointer to a buffer which, on input, contains a null-terminated string to which <i>pszSrc</i> will be concatenated. On output, this is the destination buffer that contains the entire resultant string. The string at <i>pszSrc</i>, up to <i>cbMaxAppend</i> bytes, is added to the end of the string at <i>pszDest</i> and terminated with a null character.


### -param cbDest [in]

The size of the destination buffer, in bytes. The buffer must be large enough to include both strings and the terminating null character.

For Unicode strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * sizeof(WCHAR). 

For ANSI strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * sizeof(char). 


### -param pszSrc [in]

Pointer to a null-terminated string. This string will be concatenated to the end of the string that is contained in the buffer at <i>pszDest</i>. 


### -param cbMaxAppend [in]

The maximum number of bytes to append to the string that is contained in the buffer at <i>pszDest</i>.


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

The function returns the STATUS_INVALID_PARAMETER value when:

 


## -remarks
<b>RtlStringCbCatNW</b> and <b>RtlStringCbCatNA</b> should be used instead of the following functions: 

<b>strncat</b>

<b>wcsncat</b>

The size, in bytes, of the destination buffer is provided to <b>RtlStringCbCatNW</b> and <b>RtlStringCbCatNA</b> to ensure that they do not write past the end of the buffer.

Use <b>RtlStringCbCatNW</b> to handle Unicode strings and <b>RtlStringCbCatNA</b> to handle ANSI strings. The form you use depends on your data, as shown in the following table

WCHAR

L"string"

<b>RtlStringCbCatNW</b>

<b>char</b>

"string"

<b>RtlStringCbCatNA</b>

If <i>pszSrc</i> and <i>pszDest</i> point to overlapping strings, the behavior of the function is undefined.

Neither <i>pszSrc</i> nor <i>pszDest</i> can be <b>NULL</b>. If you need to handle <b>NULL</b> string pointer values, use <a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbcatnexw.md">RtlStringCbCatNEx</a>.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>. 


## -see-also
<dl>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbcatw.md">RtlStringCbCat</a>
</dt>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbcatnexw.md">RtlStringCbCatNEx</a>
</dt>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchcatnw.md">RtlStringCchCatN</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlStringCbCatNW function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

