---
UID: NF:ntstrsafe.RtlStringCbCopyA
title: RtlStringCbCopyA function
author: windows-driver-content
description: The RtlStringCbCopyW and RtlStringCbCopyA functions copy a byte-counted string into a buffer.
old-location: kernel\rtlstringcbcopy.htm
old-project: kernel
ms.assetid: 77a42d5e-92ff-4e64-9bd3-b713286d3db0
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlStringCbCopyA
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
req.alt-api: RtlStringCbCopyW,RtlStringCbCopyA,RtlStringCbCopyW
req.alt-loc: Ntstrsafe.lib,Ntstrsafe.dll
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
req.typenames: *PBATTERY_REPORTING_SCALE, BATTERY_REPORTING_SCALE
---

# RtlStringCbCopyA function



## -description
The <b>RtlStringCbCopyW</b> and <b>RtlStringCbCopyA</b> functions copy a byte-counted string into a buffer. 



## -syntax

````
NTSTATUS RtlStringCbCopyW(
  _Out_ LPTSTR  pszDest,
  _In_  size_t  cbDest,
  _In_  LPCTSTR pszSrc
);
````


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
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>This <i>success</i> status means source data was present, the string was copied without truncation, and the resultant destination buffer is null-terminated.
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>This <i>warning</i> status means the copy operation did not complete due to insufficient buffer space. The destination buffer contains a truncated, null-terminated version of the intended result.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>This <i>error</i> status means the function received an invalid input parameter. For more information, see the following paragraph.

The function returns the STATUS_INVALID_PARAMETER value when:

 


## -remarks
<b>RtlStringCbCopyA</b> and <b>RtlStringCbCopyW</b> should be used instead of the following functions: 

<b>strcpy</b>

<b>wcscpy</b>

<b>RtlStringCbCopyA</b> and <b>RtlStringCbCopyW</b> are not replacements for <b>strncpy</b>. To replace <b>strncpy</b>, use <a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbcopynw.md">RtlStringCbCopyN</a> or <a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbcopynexw.md">RtlStringCbCopyNEx</a>.

The size of the destination buffer is provided to the function to ensure that <b>RtlStringCbCopy</b> does not write past the end of the buffer.

Use <b>RtlStringCbCopyW</b> to handle Unicode strings and <b>RtlStringCbCopyA</b> to handle ANSI strings. The form you use depends on your data as shown in the following table.

WCHAR

L"string"

<b>RtlStringCbCopyW</b>

<b>char</b>

"string"

<b>RtlStringCbCopyA</b>

If <i>pszSrc</i> and <i>pszDest</i> point to overlapping strings, the behavior of the function is undefined.

Neither <i>pszSrc</i> nor <i>pszDest</i> can be <b>NULL</b>. If you need to handle <b>NULL</b> string pointer values, use <a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbcopyexw.md">RtlStringCbCopyEx</a>.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>. 


## -see-also
<dl>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbcopyexw.md">RtlStringCbCopyEx</a>
</dt>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchcopyw.md">RtlStringCchCopy</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlStringCbCopyW function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

