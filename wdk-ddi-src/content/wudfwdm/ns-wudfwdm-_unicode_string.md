---
UID: NS:wudfwdm._UNICODE_STRING
title: "_UNICODE_STRING"
author: windows-driver-content
description: The UNICODE_STRING structure is used to define Unicode strings.
old-location: kernel\unicode_string.htm
tech.root: kernel
ms.assetid: b02f29a9-1049-4e29-aac3-72bf0c70a21e
ms.date: 04/30/2018
ms.keywords: "*PUNICODE_STRING, PUNICODE_STRING, PUNICODE_STRING structure pointer [Kernel-Mode Driver Architecture], UNICODE_STRING, UNICODE_STRING structure [Kernel-Mode Driver Architecture], _UNICODE_STRING, kernel.unicode_string, kstruct_d_9f862aaa-4cd6-4420-8255-ad577d8a8c59.xml, wudfwdm/PUNICODE_STRING, wudfwdm/UNICODE_STRING"
ms.topic: struct
req.header: wudfwdm.h
req.include-header: Wdm.h, Ntddk.h, Ntdef.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wudfwdm.h
api_name:
-	UNICODE_STRING
product:
- Windows
targetos: Windows
req.typenames: UNICODE_STRING
---

# _UNICODE_STRING structure


## -description


The <b>UNICODE_STRING</b> structure is used to define Unicode strings.


## -struct-fields




### -field Length

The length, in bytes, of the string stored in <b>Buffer</b>.


### -field MaximumLength

The length, in bytes, of <b>Buffer</b>.

### -field Buffer

Pointer to a buffer used to contain a string of wide characters.


### -field Buffer.size_is

 


### -field Buffer.size_is.MaximumLength/2

 


### -field Buffer.length_is

 


### -field Buffer.length_is.(Length)/2

## -remarks



The <b>UNICODE_STRING</b> structure is used to pass Unicode strings. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff562954">RtlUnicodeStringInit</a> or   <a href="https://msdn.microsoft.com/library/windows/hardware/ff562958">RtlUnicodeStringInitEx</a> to initialize a <b>UNICODE_STRING</b> structure.

If the string is null-terminated, <b>Length</b> does not include the trailing null character.

The <b>MaximumLength</b> is used to indicate the length of <b>Buffer</b> so that if the string is passed to a conversion routine such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff561729">RtlAnsiStringToUnicodeString</a> the returned string does not exceed the buffer size.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558741">OEM_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561725">RtlAnsiStringToUnicodeSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561729">RtlAnsiStringToUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561903">RtlFreeUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561934">RtlInitUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553248">RtlUnicodeStringToAnsiSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562969">RtlUnicodeStringToAnsiString</a>
 

 



