---
UID: NF:ntstrsafe.RtlStringCchCopyUnicodeString
title: RtlStringCchCopyUnicodeString function
author: windows-driver-content
description: The RtlStringCchCopyUnicodeString function copies the contents of a UNICODE_STRING structure to a specified destination.
old-location: kernel\rtlstringcchcopyunicodestring.htm
old-project: kernel
ms.assetid: acc4051f-dcd4-443d-ad6b-02e6b0c1cad4
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlStringCchCopyUnicodeString
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
req.alt-api: RtlStringCchCopyUnicodeString
req.alt-loc: Ntstrsafe.lib,Ntstrsafe.dll
req.ddi-compliance: 
req.unicode-ansi: 
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

# RtlStringCchCopyUnicodeString function



## -description
The <b>RtlStringCchCopyUnicodeString</b> function copies the contents of a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure to a specified destination.



## -syntax

````
NTSTATUS RtlStringCchCopyUnicodeString(
  _Out_ NTSTRSAFE_PWSTR  pszDest,
  _In_  size_t           cchDest,
  _In_  PCUNICODE_STRING SourceString
);
````


## -parameters

### -param pszDest [out]

A pointer to a buffer that receives the copied string. The string that the <i>SourceString</i> parameter's <b>UNICODE_STRING</b> structure points to is copied to the buffer at <i>pszDest</i> and terminated with a null character. 


### -param cchDest [in]

The size, in characters, of the destination buffer. The buffer must be large enough for the string and the terminating null character. The maximum number of characters is NTSTRSAFE_MAX_CCH.


### -param SourceString [in]

A pointer to a <b>UNICODE_STRING</b> structure that contains the string to be copied. The maximum number of characters in the string is NTSTRSAFE_UNICODE_STRING_MAX_CCH.


## -returns
<b>RtlStringCchCopyUnicodeString</b> returns one of the following NTSTATUS values.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>This <i>success</i> status means that source data was present, the string was copied without truncation, and the resultant destination buffer is null-terminated.
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>This <i>warning</i> status means that the copy operation did not complete because of insufficient buffer space. The destination buffer contains a truncated, null-terminated version of the intended result.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>This <i>error</i> status means that the function received an invalid input parameter. For more information, see the following list.

 

<b>RtlStringCchCopyUnicodeString</b> returns the STATUS_INVALID_PARAMETER value when one of the following occurs:

For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.


## -remarks
The <b>RtlStringCchCopyUnicodeString</b> function uses the destination buffer's size (which <i>cchDest</i> specifies) to ensure that the copy operation does not write past the end of the buffer.

If the source and destination strings overlap, the behavior of the function is undefined.

The <i>SourceString </i>and <i>pszDest</i> pointers cannot be <b>NULL</b>. If you need to handle <b>NULL</b> pointer values, use the <a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchcopyunicodestringex.md">RtlStringCchCopyUnicodeStringEx</a> function.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>. 


## -see-also
<dl>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbcopyunicodestring.md">RtlStringCbCopyUnicodeString</a>
</dt>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchcopyunicodestringex.md">RtlStringCchCopyUnicodeStringEx</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlStringCchCopyUnicodeString function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

