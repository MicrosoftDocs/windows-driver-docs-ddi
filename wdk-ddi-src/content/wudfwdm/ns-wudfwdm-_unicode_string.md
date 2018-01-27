---
UID: NS:wudfwdm._UNICODE_STRING
title: _UNICODE_STRING
author: windows-driver-content
description: The UNICODE_STRING structure is used to define Unicode strings.
old-location: kernel\unicode_string.htm
old-project: kernel
ms.assetid: b02f29a9-1049-4e29-aac3-72bf0c70a21e
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wudfwdm/PUNICODE_STRING, wudfwdm/UNICODE_STRING, UNICODE_STRING structure [Kernel-Mode Driver Architecture], PUNICODE_STRING structure pointer [Kernel-Mode Driver Architecture], _UNICODE_STRING, UNICODE_STRING, *PUNICODE_STRING, kernel.unicode_string, PUNICODE_STRING, kstruct_d_9f862aaa-4cd6-4420-8255-ad577d8a8c59.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	wudfwdm.h
apiname: 
-	UNICODE_STRING
product: Windows
targetos: Windows
req.typenames: UNICODE_STRING
req.product: Windows 10 or later.
---

# _UNICODE_STRING structure


## -description


The <b>UNICODE_STRING</b> structure is used to define Unicode strings.


## -syntax


````
typedef struct _UNICODE_STRING {
  USHORT Length;
  USHORT MaximumLength;
  PWSTR  Buffer;
} UNICODE_STRING, *PUNICODE_STRING;
````


## -struct-fields




### -field Length

The length, in bytes, of the string stored in <b>Buffer</b>.


### -field MaximumLength

The length, in bytes, of <b>Buffer</b>.


### -field Buffer.size_is

 


### -field Buffer.size_is.MaximumLength/2

 


### -field Buffer.length_is

 


### -field Buffer.length_is.(Length)/2

 


### -field Buffer

Pointer to a buffer used to contain a string of wide characters.


## -remarks


The <b>UNICODE_STRING</b> structure is used to pass Unicode strings. Use <a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringinit.md">RtlUnicodeStringInit</a> or   <a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringinitex.md">RtlUnicodeStringInitEx</a> to initialize a <b>UNICODE_STRING</b> structure.

If the string is null-terminated, <b>Length</b> does not include the trailing null character.

The <b>MaximumLength</b> is used to indicate the length of <b>Buffer</b> so that if the string is passed to a conversion routine such as <a href="..\wdm\nf-wdm-rtlansistringtounicodestring.md">RtlAnsiStringToUnicodeString</a> the returned string does not exceed the buffer size.



## -see-also

<a href="..\wdm\nf-wdm-rtlinitunicodestring.md">RtlInitUnicodeString</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558741">OEM_STRING</a>

<a href="..\wdm\nf-wdm-rtlfreeunicodestring.md">RtlFreeUnicodeString</a>

<a href="..\wdm\nf-wdm-rtlansistringtounicodesize.md">RtlAnsiStringToUnicodeSize</a>

<a href="..\wdm\nf-wdm-rtlunicodestringtoansisize.md">RtlUnicodeStringToAnsiSize</a>

<a href="..\wdm\nf-wdm-rtlunicodestringtoansistring.md">RtlUnicodeStringToAnsiString</a>

<a href="..\wdm\nf-wdm-rtlansistringtounicodestring.md">RtlAnsiStringToUnicodeString</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20UNICODE_STRING structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

