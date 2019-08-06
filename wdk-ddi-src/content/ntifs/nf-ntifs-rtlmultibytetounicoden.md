---
UID: NF:ntifs.RtlMultiByteToUnicodeN
title: RtlMultiByteToUnicodeN function (ntifs.h)
description: The RtlMultiByteToUnicodeN routine translates the specified source string into a Unicode string, using the current system ANSI code page (ACP). The source string is not necessarily from a multibyte character set.
old-location: ifsk\rtlmultibytetounicoden.htm
tech.root: ifsk
ms.assetid: c0cc4fba-01ba-4745-8dee-fc4c43f570cf
ms.date: 04/16/2018
ms.keywords: RtlMultiByteToUnicodeN, RtlMultiByteToUnicodeN routine [Installable File System Drivers], ifsk.rtlmultibytetounicoden, ntifs/RtlMultiByteToUnicodeN, rtlref_c9245403-e17c-479b-ac16-07deb29a56d1.xml
ms.topic: function
f1_keywords:
 - "ntifs/RtlMultiByteToUnicodeN"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: < DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
- Ntdll.dll
api_name:
- RtlMultiByteToUnicodeN
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlMultiByteToUnicodeN function


## -description


The <b>RtlMultiByteToUnicodeN</b> routine translates the specified source string into a Unicode string, using the current system ANSI code page (ACP). The source string is not necessarily from a multibyte character set. 


## -parameters




### -param UnicodeString [out]

Pointer to a caller-allocated buffer that receives the translated string. <i>UnicodeString</i> buffer must not overlap with <i>MultiByteString </i>buffer.


### -param MaxBytesInUnicodeString [in]

Maximum number of bytes to be written at <i>UnicodeString</i>. If this value causes the translated string to be truncated, <b>RtlMultiByteToUnicodeN</b> does not return an error status. 


### -param BytesInUnicodeString [out, optional]

Pointer to a caller-allocated variable that receives the length, in bytes, of the translated string. This parameter can be <b>NULL</b>. 


### -param MultiByteString [in]

Pointer to the string to be translated. 


### -param BytesInMultiByteString [in]

Size, in bytes, of the string at <i>MultiByteString</i>. 


## -returns



<b>RtlMultiByteToUnicodeN</b> returns STATUS_SUCCESS. 




## -remarks



<b>RtlMultiByteToUnicodeN</b> supports only precomposed Unicode characters that are mapped to the current system ANSI code page installed at system boot. 

Although <i>BytesInUnicodeString</i> is optional and can be <b>NULL</b>, callers should provide storage for it, because the received length can be used to determine whether the conversion was successful.

If the current system code page defines a single-byte character set, all ANSI characters in the range 0x00 to 0x7f are simply zero-extended in the corresponding Unicode string to speed the conversion operation. The ANSI value 0x5c in such a code page is translated into the backslash character, even if the current single-byte code page defines this character as the Yen sign. 

<b>RtlMultiByteToUnicodeN</b> does not modify the source string unless the <i>UnicodeString</i> and <i>MultiByteString</i> pointers are equivalent. The returned Unicode string is not null-terminated. 

Like <b>RtlMultiByteToUnicodeSize</b>, <b>RtlMultiByteToUnicodeN</b> supports only precomposed Unicode characters that are mapped to the current system ANSI code page installed at system boot. 

For information about other string-handling routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Strings</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-rtlmultibytetounicodesize">RtlMultiByteToUnicodeSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-rtlunicodetomultibyten">RtlUnicodeToMultiByteN</a>
 

 

