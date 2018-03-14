---
UID: NF:ntstrsafe.RtlStringCchLengthA
title: RtlStringCchLengthA function
author: windows-driver-content
description: The RtlStringCchLengthW and RtlStringCchLengthA functions determine the length, in characters, of a supplied string.
old-location: kernel\rtlstringcchlength.htm
old-project: kernel
ms.assetid: 37d9309d-b105-4e56-b236-530ed49ca116
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: RtlStringCchLength, RtlStringCchLengthA, RtlStringCchLengthW, RtlStringCchLengthW function [Kernel-Mode Driver Architecture], kernel.rtlstringcchlength, ntstrsafe/RtlStringCchLengthA, ntstrsafe/RtlStringCchLengthW, safestrings_530fb488-be05-467f-a8c5-22016fb49325.xml
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
req.unicode-ansi: RtlStringCchLengthW (Unicode) and RtlStringCchLengthA (ANSI)
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntstrsafe.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ntstrsafe.lib
-	Ntstrsafe.dll
api_name:
-	RtlStringCchLengthW
-	RtlStringCchLengthA
-	RtlStringCchLengthW
product: Windows
targetos: Windows
req.typenames: SYSTEM_POWER_STATE_CONTEXT, *PSYSTEM_POWER_STATE_CONTEXT
---

# RtlStringCchLengthA function


## -description


The <b>RtlStringCchLengthW</b> and <b>RtlStringCchLengthA</b> functions determine the length, in characters, of a supplied string. 


## -syntax


````
NTSTATUS RtlStringCchLengthW(
  _In_      LPCTSTR psz,
  _In_      size_t  cchMax,
  _Out_opt_ size_t  *pcch
);
````


## -parameters




### -param psz [in]

A pointer to a buffer that contains a null-terminated string, the length of which will be checked. 


### -param cchMax [in]

The maximum number of characters allowed in the buffer pointed to by <i>psz</i>, including the terminating null character. This value cannot exceed NTSTRSAFE_MAX_CCH. 


### -param pcchLength

TBD




#### - pcch [out, optional]

If the caller supplies a non-<b>NULL</b> address pointer, the function loads the address with the length, in characters, of the string that is contained in the buffer. The length does not include the string's terminating null character.


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
This success status means the string at <i>psz</i> was not <b>NULL</b>, and the length of the string (including the terminating null character) is less than or equal to <i>cchMax</i> characters.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
This error status means the value in <i>psz</i> is <b>NULL</b>, <i>cchMax</i> is larger than NTSTRSAFE_MAX_CCH, or <i>psz</i> is longer than <i>cchMax</i>.

</td>
</tr>
</table>
 




## -remarks



<b>RtlStringCchLengthW</b> and <b>RtlStringCchLengthA</b> should be used instead of <b>strlen</b>. They are used to ensure that a string is not larger than a given length, in characters. If that condition is met, <b>RtlStringCchLengthW</b> and <b>RtlStringCchLengthA</b> return the current length of the string in characters, not including the terminating null character.

Use <b>RtlStringCchLengthW</b> to handle Unicode strings and <b>RtlStringCchLengthA</b> to handle ANSI strings. The form you use depends on your data, as shown in the following table.

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
<b>RtlStringCchLengthW</b>

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
<b>RtlStringCchLengthA</b>

</td>
</tr>
</table>
 

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>. 




## -see-also

<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcblengthw.md">RtlStringCbLength</a>



 

 


