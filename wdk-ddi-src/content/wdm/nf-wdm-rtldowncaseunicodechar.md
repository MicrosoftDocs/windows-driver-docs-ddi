---
UID: NF:wdm.RtlDowncaseUnicodeChar
title: RtlDowncaseUnicodeChar function
author: windows-driver-content
description: The RtlDowncaseUnicodeChar routine converts the specified Unicode character to lowercase.
old-location: kernel\rtldowncaseunicodechar.htm
old-project: kernel
ms.assetid: 1377a069-5065-4305-a48c-7a84f0071fc3
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: RtlDowncaseUnicodeChar, RtlDowncaseUnicodeChar routine [Kernel-Mode Driver Architecture], k109_e9ba1cee-5de9-4f8f-b964-6668ddef36b7.xml, kernel.rtldowncaseunicodechar, wdm/RtlDowncaseUnicodeChar
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
req.lib: Ntoskrnl.lib; Ntdll.lib
req.dll: Ntoskrnl.exe; Ntdll.dll
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Ntoskrnl.exe
-	Ntdll.dll
api_name:
-	RtlDowncaseUnicodeChar
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlDowncaseUnicodeChar function


## -description


The <b>RtlDowncaseUnicodeChar</b> routine converts the specified Unicode character to lowercase. 


## -syntax


````
WCHAR RtlDowncaseUnicodeChar(
  _In_ WCHAR SourceCharacter
);
````


## -parameters




### -param SourceCharacter [in]

Specifies the character to convert. 


## -returns



<b>RtlDowncaseUnicodeChar</b> returns the lowercase value of the Unicode character.




## -remarks



Ntoskrnl.lib supports the <b>RtlDowncaseUnicodeChar</b> routine in the WDK for Windows 7 and later versions of Windows. Ntdll.dll exports the <b>RtlDowncaseUnicodeChar</b> entry point in Windows XP and later versions of Windows.




## -see-also

<a href="..\ntifs\nf-ntifs-rtldowncaseunicodestring.md">RtlDowncaseUnicodeString</a>



<a href="..\wdm\nf-wdm-rtlupcaseunicodechar.md">RtlUpcaseUnicodeChar</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlDowncaseUnicodeChar routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

