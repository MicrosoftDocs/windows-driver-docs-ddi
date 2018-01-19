---
UID: NF:ntstrsafe.RtlStringCbVPrintfW
title: RtlStringCbVPrintfW function
author: windows-driver-content
description: The RtlStringCbVPrintfW and RtlStringCbVPrintfA functions create a byte-counted text string, with formatting that is based on supplied formatting information.
old-location: kernel\rtlstringcbvprintf.htm
old-project: kernel
ms.assetid: 9dfd1894-c9b5-43c2-8377-c28577898754
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlStringCbVPrintfW
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntstrsafe.h
req.include-header: Ntstrsafe.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows XP with Service Pack 1 (SP1).
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlStringCbVPrintfW,RtlStringCbVPrintfA,RtlStringCbVPrintfW
req.alt-loc: Ntstrsafe.lib,Ntstrsafe.dll
req.ddi-compliance: 
req.unicode-ansi: RtlStringCbVPrintfW (Unicode) and RtlStringCbVPrintfA (ANSI)
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

# RtlStringCbVPrintfW function



## -description
The <b>RtlStringCbVPrintfW</b> and <b>RtlStringCbVPrintfA</b> functions create a byte-counted text string, with formatting that is based on supplied formatting information.



## -syntax

````
NTSTATUS RtlStringCbVPrintfW(
  _Out_ LPTSTR  pszDest,
  _In_  size_t  cbDest,
  _In_  LPCTSTR pszFormat,
  _In_  va_list argList
);
````


## -parameters

### -param pszDest [out]

A pointer to a caller-supplied buffer that receives a formatted, null-terminated string. The function creates this string from both the formatting string that is supplied by <i>pszFormat</i> and the arguments supplied by <i>argList</i>.


### -param cbDest [in]

The size of the destination buffer, in bytes. The buffer must be large enough to contain the formatted string plus the terminating null character.

For Unicode strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * sizeof(WCHAR). 

For ANSI strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * sizeof(char). 


### -param pszFormat [in]

A pointer to a null-terminated text string that contains <b>printf</b>-styled <a href="http://msdn.microsoft.com/en-us/library/56e442dc.aspx">formatting directives</a>.


### -param argList [in]

A <b>va_list</b>-typed argument list. Arguments contained in the argument list will be interpreted by using the formatting string that is supplied by <i>pszFormat</i>.


## -returns
The function returns one of the NTSTATUS values that are listed in the following table. For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>This <i>success</i> status means source data was present, the output string was created without truncation, and the resultant destination buffer is null-terminated.
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>This <i>warning</i> status means the operation did not complete due to insufficient space in the destination buffer. The destination buffer contains a truncated version of the created string.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>This <i>error</i> status means the function received an invalid input parameter. For more information, see the following paragraph.

The function returns the STATUS_INVALID_PARAMETER value when:

 


## -remarks
<b>RtlStringCbVPrintfW</b> and <b>RtlStringCbVPrintfA</b> should be used instead of the following functions: 

<b>vsprintf</b>

<b>vswprintf</b>

_<b>vsnprintf</b>

_<b>vsnwprintf</b>

All of these functions accept a format string, along with a set of arguments in a <b>va_list</b>-typed argument list, and return a formatted string. The size, in bytes, of the destination buffer is provided to <b>RtlStringCbVPrintfW</b> and <b>RtlStringCbVPrintfA</b> to ensure that they do not write past the end of the buffer.

For more information about <b>va_list</b>-typed argument lists, see the Microsoft Windows SDK documentation.

Use <b>RtlStringCbVPrintfW</b> to handle Unicode strings and <b>RtlStringCbVPrintfA</b> to handle ANSI strings. The form you use depends on your data, as shown in the following table.

WCHAR

L"string"

<b>RtlStringCbVPrintfW</b>

<b>char</b>

"string"

<b>RtlStringCbVPrintfA</b>

If <i>pszDest</i> and <i>pszFormat </i>point to overlapping strings or if any argument strings overlap, the behavior of the function is undefined..

Neither <i>pszFormat</i> nor <i>pszDest</i> should be <b>NULL</b>. If you need to handle <b>NULL</b> string pointer values, use <a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbvprintfexw.md">RtlStringCbVPrintfEx</a>.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>.


## -see-also
<dl>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbvprintfexw.md">RtlStringCbVPrintfEx</a>
</dt>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbprintfw.md">RtlStringCbPrintf</a>
</dt>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchvprintfw.md">RtlStringCchVPrintf</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlStringCbVPrintfW function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

