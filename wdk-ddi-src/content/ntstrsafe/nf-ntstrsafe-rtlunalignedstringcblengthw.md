---
UID: NF:ntstrsafe.RtlUnalignedStringCbLengthW
title: RtlUnalignedStringCbLengthW function
author: windows-driver-content
description: The RtlUnalignedStringCbLengthW function is a version of the RtlStringCbLength function that accepts an unaligned pointer to a string of Unicode characters.
old-location: kernel\rtlunalignedstringcblength.htm
old-project: kernel
ms.assetid: 03f49658-ec51-4869-bba8-832c6856c4b0
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ntstrsafe/RtlUnalignedStringCbLengthW, RtlUnalignedStringCbLength, safestrings_6724eedb-4d8d-490a-aac8-81c5c95ca3df.xml, RtlUnalignedStringCbLengthW function [Kernel-Mode Driver Architecture], kernel.rtlunalignedstringcblength, RtlUnalignedStringCbLengthW
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
req.unicode-ansi: 
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
-	RtlUnalignedStringCbLengthW
product: Windows
targetos: Windows
req.typenames: BATTERY_REPORTING_SCALE, *PBATTERY_REPORTING_SCALE
---

# RtlUnalignedStringCbLengthW function


## -description


The <b>RtlUnalignedStringCbLengthW</b> function is a version of the <a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcblengthw.md">RtlStringCbLength</a> function that accepts an unaligned pointer to a string of Unicode characters.


## -syntax


````
NTSTATUS RtlUnalignedStringCbLengthW(
  _In_      STRSAFE_PCUNZWCH psz,
  _In_      size_t           cbMax,
  _Out_opt_ size_t           *pcbLength
);
````


## -parameters




#### - psz [in]

Supplies a pointer to a buffer that contains a null-terminated string whose length <b>RtlUnalignedStringCbLengthW</b>  will check. 


#### - cbMax [in]

Supplies the maximum number of bytes that are allowed in the buffer that <i>psz</i> points to, including the terminating NULL character. This value cannot exceed NTSTRSAFE_MAX_CCH * sizeof(WCHAR). 


#### - pcbLength [out, optional]

Optional. If the caller supplies a non-<b>NULL</b> address pointer, the function loads the address with the length, in bytes, of the string that is contained in the buffer that <i>psz</i> points to. The length does not include the string's terminating NULL character.


## -returns


<b>RtlUnalignedStringCbLengthW</b> returns one of the following NTSTATUS values. 
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
This <i>success</i> status means the string that the <i>psz</i> parameter specified was not <b>NULL</b>, and the length of the string (including the terminating NULL character) was less than or equal to <i>cbMax</i> bytes.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
This <i>error</i> status means the value in <i>psz</i> is <b>NULL</b>, <i>cbMax</i> is larger than NTSTRSAFE_MAX_CCH * sizeof(WCHAR, or <i>psz</i> is longer than <i>cbMax</i>.

</td>
</tr>
</table> 

For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.



## -remarks


The <b>RtlUnalignedStringCbLengthW</b> function is available for processor architectures, such as Itanium-based and x64-based, that cause alignment exceptions when software attempts to access unaligned data. On those processors, you can use <b>RtlUnalignedStringCbLengthW</b> instead of the <a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcblengthw.md">RtlStringCbLength</a> function to avoid alignment exceptions. (For processors that do not cause alignment exceptions, <b>RtlUnalignedStringCbLengthW</b> is equivalent to <b>RtlStringCbLength</b>.)

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>.



## -see-also

<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcblengthw.md">RtlStringCbLength</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlUnalignedStringCbLengthW function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

