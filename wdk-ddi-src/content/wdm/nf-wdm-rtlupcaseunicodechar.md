---
UID: NF:wdm.RtlUpcaseUnicodeChar
title: RtlUpcaseUnicodeChar function
author: windows-driver-content
description: The RtlUpcaseUnicodeChar routine converts the specified Unicode character to uppercase.
old-location: kernel\rtlupcaseunicodechar.htm
old-project: kernel
ms.assetid: e8584c60-57ba-4b9c-949f-041bb37dfb13
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlUpcaseUnicodeChar, RtlUpcaseUnicodeChar routine [Kernel-Mode Driver Architecture], k109_81806669-d742-4cb9-b4dd-d7e40fef171a.xml, kernel.rtlupcaseunicodechar, wdm/RtlUpcaseUnicodeChar
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
-	Ntdll.dll
api_name:
-	RtlUpcaseUnicodeChar
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlUpcaseUnicodeChar function


## -description


The <b>RtlUpcaseUnicodeChar</b> routine converts the specified Unicode character to uppercase.


## -parameters




### -param SourceCharacter [in]

Specifies the character to convert.


## -returns



<b>RtlUpcaseUnicodeChar</b> returns the uppercase version of the specified Unicode character.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563005">RtlUpcaseUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563009">RtlUpperChar</a>
 

 

