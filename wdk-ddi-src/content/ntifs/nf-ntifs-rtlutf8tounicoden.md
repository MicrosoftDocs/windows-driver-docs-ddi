---
UID: NF:ntifs.RtlUTF8ToUnicodeN
title: RtlUTF8ToUnicodeN function (ntifs.h)
description: The RtlUTF8ToUnicodeN routine converts a UTF-8 string to a Unicode string.
old-location: kernel\rtlutf8tounicoden.htm
tech.root: kernel
ms.assetid: 0b5f791a-9814-4058-8ee0-8f113ca3ade2
ms.date: 04/30/2018
ms.keywords: RtlUTF8ToUnicodeN, RtlUTF8ToUnicodeN routine [Kernel-Mode Driver Architecture], k109_67399c4f-a942-4493-b141-6824b6de570c.xml, kernel.rtlutf8tounicoden, wdm/RtlUTF8ToUnicodeN
ms.topic: function
f1_keywords:
 - "ntifs/RtlUTF8ToUnicodeN"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlUTF8ToUnicodeN
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUTF8ToUnicodeN function


## -description


The <b>RtlUTF8ToUnicodeN</b> routine converts a UTF-8 string to a Unicode string. 


## -parameters




### -param UnicodeStringDestination [out, optional]

A pointer to a caller-allocated destination buffer into which the routine writes the Unicode output string. If this parameter is <b>NULL</b>, the routine writes the required size of the output buffer to *<i>UnicodeStringActualByteCount</i>. 


### -param UnicodeStringMaxByteCount [in]

Specifies the maximum number of bytes that the routine can write to the buffer that <i>UnicodeStringDestination</i> points to. If <i>UnicodeStringDestination</i> = <b>NULL</b>, set <i>UnicodeStringMaxByteCount</i> = 0. 


### -param UnicodeStringActualByteCount [out]

A pointer to a location into which the routine writes the actual number of bytes that the routine has written to the buffer that <i>UnicodeStringDestination</i> points to. If <i>UnicodeStringDestination</i> is non-<b>NULL</b>, this count never exceeds the value of <i>UnicodeStringMaxByteCount</i>. If <i>UnicodeStringDestination</i> is <b>NULL</b>, this count is the number of bytes that are required to contain the entire output string. 


### -param UTF8StringSource [in]

A pointer to the UTF-8 source string.


### -param UTF8StringByteCount [in]

Specifies the number of bytes in the UTF-8 source string that the <i>UTF8StringSource</i> parameter points to. 


## -returns



<b>RtlUTF8ToUnicodeN</b> returns STATUS_SUCCESS if the call is successful and all UTF-8 character codes in the input string were converted to the corresponding Unicode character codes in the output string. It returns STATUS_SOME_NOT_MAPPED if the call is successful but one or more input characters were invalid and were converted to the Unicode replacement character, U+FFFD. Possible error return values include the following error codes:

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
The <i>UnicodeStringMaxByteCount</i> parameter specifies a buffer size that is too small to contain the entire output string. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>UnicodeStringDestination</i> and <i>UnicodeStringActualByteCount</i> parameters are both <b>NULL</b>. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_4</b></dt>
</dl>
</td>
<td width="60%">
The <i>UTF8StringSource</i> parameter is <b>NULL</b>. 

</td>
</tr>
</table>
 




## -remarks



The Unicode output string is null-terminated only if the UTF-8 input string is null-terminated.

The routine returns STATUS_BUFFER_TOO_SMALL if the <i>UnicodeStringMaxByteCount</i> parameter specifies a buffer size that is too small to contain the entire output string. In this case, the routine writes as many Unicode characters as will fit in the buffer, and the *<i>UnicodeStringActualByteCount</i> value specifies the number of valid bytes that the routine has written to the buffer. The partial string that is contained in the output buffer might not include a terminating null character.

You can make an initial call to <b>RtlUTF8ToUnicodeN</b> to obtain the required output buffer size, and then call <b>RtlUTF8ToUnicodeN</b> again to obtain the Unicode output string. In the initial call, set <i>UnicodeStringDestination</i> = <b>NULL</b> and <i>UnicodeStringMaxByteCount</i> = 0, and the routine will write the required buffer size to *<i>UnicodeStringActualByteCount</i>. Next, allocate a buffer of the required size and call <b>RtlUTF8ToUnicodeN</b> a second time to obtain the Unicode output string.

<b>RtlUTF8ToUnicodeN</b> supports Unicode surrogate pairs. However, a surrogate leading word value that is not followed by a trailing word value, or a trailing word value that is not preceded by a leading word value, is not recognized as a valid character and is replaced by the Unicode replacement character, U+FFFD.

<b>RtlUTF8ToUnicodeN</b> continues to convert the input string to an output string until it reaches the end of the source buffer or the end of the destination buffer, whichever occurs first. The routine converts any null characters in the input string to null characters in the output string. If the input string contains a terminating null character, but the null character is not located at the end of the source buffer, the routine continues past the terminating null character until it reaches the end of the available buffer space.

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-rtlunicodetoutf8n">RtlUnicodeToUTF8N</a> routine converts a Unicode string to a UTF-8 string.

You can use the <b>RtlUTF8ToUnicode</b> and <b>RtlUnicodeToUTF8N</b> routines to perform a lossless conversion of valid text strings between the UTF-8 and Unicode formats. However, strings that have arbitrary data values are likely to violate the Unicode rules for encoding surrogate pairs, and any information that is contained in the invalid values in an input string is lost and cannot be recovered from the resulting output string. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-rtlunicodetoutf8n">RtlUnicodeToUTF8N</a>
 

 

