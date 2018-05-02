---
UID: NF:wdm.RtlFreeUnicodeString
title: RtlFreeUnicodeString function
author: windows-driver-content
description: The RtlFreeUnicodeString routine releases storage that was allocated by RtlAnsiStringToUnicodeString or RtlUpcaseUnicodeString.
old-location: kernel\rtlfreeunicodestring.htm
old-project: kernel
ms.assetid: 505e2ab7-13c3-4cdd-90ba-a37bb38fe160
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: RtlFreeUnicodeString, RtlFreeUnicodeString routine [Kernel-Mode Driver Architecture], k109_c23e6c5e-d2dd-4b88-8249-5f88ad8482ad.xml, kernel.rtlfreeunicodestring, wdm/RtlFreeUnicodeString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Wudfwdm.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: "<=APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlFreeUnicodeString
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlFreeUnicodeString function


## -description


The <b>RtlFreeUnicodeString</b> routine releases storage that was allocated by <b>RtlAnsiStringToUnicodeString</b> or <b>RtlUpcaseUnicodeString</b>.


## -parameters




### -param UnicodeString [in, out]

Pointer to the Unicode string buffer previously allocated by <b>RtlAnsiStringToUnicodeString</b> or <b>RtlUpcaseUnicodeString</b>. 


## -returns



None




## -remarks



This routine does not release the ANSI string buffer passed to <b>RtlAnsiStringToUnicodeString</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561729">RtlAnsiStringToUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563005">RtlUpcaseUnicodeString</a>
 

 

