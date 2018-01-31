---
UID: NF:ntifs.RtlUnicodeToUTF8N
title: RtlUnicodeToUTF8N function
author: windows-driver-content
description: The RtlUnicodeToUTF8N routine converts a Unicode string to a UTF-8 string.
old-location: kernel\rtlunicodetoutf8n.htm
old-project: kernel
ms.assetid: fdbb5d74-25d5-4920-849c-8d4adce1d216
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k109_8c33089a-9b47-4c33-9468-56a16caea229.xml, RtlUnicodeToUTF8N routine [Kernel-Mode Driver Architecture], wdm/RtlUnicodeToUTF8N, kernel.rtlunicodetoutf8n, RtlUnicodeToUTF8N
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, Wdm.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlUnicodeToUTF8N
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlUnicodeToUTF8N function


## -description


The <b>RtlUnicodeToUTF8N</b> routine converts a Unicode string to a UTF-8 string. 


## -syntax


````
NTSTATUS RtlUnicodeToUTF8N(
  _Out_ PCHAR  UTF8StringDestination,
  _In_  ULONG  UTF8StringMaxByteCount,
  _Out_ PULONG UTF8StringActualByteCount,
  _In_  PCWCH  UnicodeStringSource,
  _In_  ULONG  UnicodeStringByteCount
);
````


## -parameters




#### - UTF8StringDestination [out]

A pointer to a caller-allocated destination buffer into which the routine writes the UTF-8 output string. If this parameter is <b>NULL</b>, the routine writes the required size of the output buffer to *<i>UTF8StringActualByteCount</i>. 


#### - UTF8StringMaxByteCount [in]

Specifies the maximum number of bytes that the routine can write to the buffer that <i>UTF8StringDestination</i> points to. If <i>UTF8StringDestination</i> = <b>NULL</b>, set <i>UTF8StringMaxByteCount</i> = 0. 


#### - UTF8StringActualByteCount [out]

A pointer to a location into which the routine writes the actual number of bytes that it has written to the buffer that <i>UTF8StringDestination</i> points to. If <i>UTF8StringDestination</i> is non-<b>NULL</b>, this count never exceeds the value of <i>UTF8StringMaxByteCount</i>. If <i>UTF8StringDestination</i> is <b>NULL</b>, this count is the number of bytes that are required to contain the entire output string. 


#### - UnicodeStringSource [in]

A pointer to the Unicode source string.


#### - UnicodeStringByteCount [in]

Specifies the number of bytes in the Unicode source string that the <i>UnicodeStringSource</i> parameter points to. 


## -returns


<b>RtlUnicodeToUTF8N</b> returns STATUS_SUCCESS if the call is successful and all Unicode character codes in the input string were converted to the corresponding UTF-8 character codes in the output string. It returns STATUS_SOME_NOT_MAPPED if the call is successful but one or more input characters were invalid and were replaced by the Unicode replacement character, U+FFFD, before they were converted to UTF-8. Possible error return values include the following error codes:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The <i>UTF8StringMaxByteCount</i> parameter specifies a buffer size that is too small to contain the entire output string. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>UTF8StringDestination</i> and <i>UTF8StringActualByteCount</i> parameters are both <b>NULL</b>. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_4</b></dt>
</dl>
</td>
<td width="60%">
The <i>UnicodeStringSource</i> parameter is <b>NULL</b>. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_5</b></dt>
</dl>
</td>
<td width="60%">
<i>UnicodeStringByteCount</i> is not an integer multiple of <b>sizeof</b>(WCHAR). 

</td>
</tr>
</table> 



## -remarks


The UTF-8 output string is null-terminated only if the Unicode input string is null-terminated.

The routine returns STATUS_BUFFER_TOO_SMALL if the <i>UTF8StringMaxByteCount</i> parameter specifies a buffer size that is too small to contain the entire output string. In this case, the routine writes as many UTF-8 characters as will fit in the buffer, and the *<i>UTF8StringActualByteCount</i> value specifies the number of valid bytes that the routine has written to the buffer. The partial string that is contained in the output buffer might not include a terminating null character.

You can make an initial call to <b>RtlUnicodeToUTF8N</b> to obtain the required output buffer size, and then call <b>RtlUnicodeToUTF8N</b> again to obtain the Unicode output string. In the initial call, set <i>UTF8StringDestination</i> = <b>NULL</b> and <i>UTF8StringMaxByteCount</i> = 0, and the routine will write the required buffer size to *<i>UTF8StringActualByteCount</i>. Next, allocate a buffer of the required size and call <b>RtlUnicodeToUTF8N</b> a second time to obtain the UTF-8 output string.

<b>RtlUnicodeToUTF8N</b> supports Unicode surrogate pairs. However, a surrogate leading word value that is not followed by a trailing word value, or a trailing word value that is not preceded by a leading word value, is not recognized as a valid character code and is replaced by the Unicode replacement character, U+FFFD.

<b>RtlUnicodeToUTF8N</b> continues to convert the input string to an output string until it reaches the end of the source buffer or the end of the destination buffer, whichever occurs first. The routine converts any null characters in the input string to null characters in the output string. If the input string contains a terminating null character, but the null character is not located at the end of the source buffer, the routine continues past the terminating null character until it reaches the end of the available buffer space.

The <a href="..\wdm\nf-wdm-rtlutf8tounicoden.md">RtlUTF8ToUnicodeN</a> routine converts a UTF-8 string to a Unicode string.

You can use <b>RtlUnicodeToUTF8N</b> and <b>RtlUTF8ToUnicode</b> routines to perform a lossless conversion of valid text strings between the Unicode and UTF-8 formats. However, strings that have arbitrary data values are likely to violate the Unicode rules for encoding surrogate pairs, and any information that is contained in the invalid values in an input string is lost and cannot be recovered from the resulting output string. 



## -see-also

<a href="..\wdm\nf-wdm-rtlutf8tounicoden.md">RtlUTF8ToUnicodeN</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlUnicodeToUTF8N routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

