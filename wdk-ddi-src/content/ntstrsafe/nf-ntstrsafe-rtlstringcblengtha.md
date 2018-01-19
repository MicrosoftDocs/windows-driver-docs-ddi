---
UID: NF:ntstrsafe.RtlStringCbLengthA
title: RtlStringCbLengthA function
author: windows-driver-content
description: The RtlStringCbLengthW and RtlStringCbLengthA functions determine the length, in bytes, of a supplied string.
old-location: kernel\rtlstringcblength.htm
old-project: kernel
ms.assetid: 74644211-7cf5-48d4-9025-7831cb449979
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlStringCbLengthA
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
req.alt-api: RtlStringCbLengthW,RtlStringCbLengthA,RtlStringCbLengthW
req.alt-loc: Ntstrsafe.lib,Ntstrsafe.dll
req.ddi-compliance: 
req.unicode-ansi: RtlStringCbLengthW (Unicode) and RtlStringCbLengthA (ANSI)
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

# RtlStringCbLengthA function



## -description
The <b>RtlStringCbLengthW</b> and <b>RtlStringCbLengthA</b> functions determine the length, in bytes, of a supplied string. 



## -syntax

````
NTSTATUS RtlStringCbLengthW(
  _In_      LPCTSTR psz,
  _In_      size_t  cbMax,
  _Out_opt_ size_t  *pcb
);
````


## -parameters

### -param psz [in]

A pointer to a buffer that contains a null-terminated string, the length of which will be checked.


### -param cbMax [in]

The maximum number of bytes allowed in the buffer that is pointed to by <i>psz</i>, including the terminating null character. 

For Unicode strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * sizeof(WCHAR). 

For ANSI strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * sizeof(char). 


### -param pcb [out, optional]

If the caller supplies a non-<b>NULL</b> address pointer, the function loads the address with the length, in bytes, of the string that is contained in the buffer. The length does not include the string's terminating null character.


## -returns
The function returns one of the NTSTATUS values that are listed in the following table. For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>This <i>success</i> status means the string at <i>psz</i> was not <b>NULL</b>, and the length of the string (including the terminating null character) is less than or equal to <i>cbMax</i> characters.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>This <i>error</i> status means the value in <i>psz</i> is <b>NULL</b>, <i>cbMax</i> is larger than NTSTRSAFE_MAX_CCH * sizeof(TCHAR), or <i>psz</i> is longer than <i>cbMax</i>.

 


## -remarks
<b>RtlStringCbLengthW</b> and <b>RtlStringCbLengthA</b> should be used instead of <b>strlen</b>. Use these functions to ensure that a string is not larger than a given length, in bytes. If that condition is met, <b>RtlStringCbLengthW</b> and <b>RtlStringCbLengthA</b> return the current length of the string in bytes, not including those bytes used for the terminating null character.

Use <b>RtlStringCbLengthW</b> to handle Unicode strings and <b>RtlStringCbLengthA</b> to handle ANSI strings. The form you use depends on your data, as shown in the following table.

WCHAR

L"string"

<b>RtlStringCbLengthW</b>

<b>char</b>

"string"

<b>RtlStringCbLengthA</b>

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>. 


## -see-also
<dl>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchlengthw.md">RtlStringCchLength</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlStringCbLengthW function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

