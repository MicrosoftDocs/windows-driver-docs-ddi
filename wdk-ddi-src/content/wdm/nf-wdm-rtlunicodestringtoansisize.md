---
UID: NF:wdm.RtlUnicodeStringToAnsiSize
title: RtlUnicodeStringToAnsiSize macro
author: windows-driver-content
description: The RtlUnicodeStringToAnsiSize routine returns the number of bytes required for a null-terminated ANSI string that is equivalent to a specified Unicode string.
old-location: kernel\rtlunicodestringtoansisize.htm
old-project: kernel
ms.assetid: 4deaa42e-8c8b-461a-845e-424b543b52b1
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.rtlunicodestringtoansisize, k109_3a436ab4-80f1-4fb2-b4b6-98b4dc1ba1f1.xml, RtlUnicodeStringToAnsiSize, RtlUnicodeStringToAnsiSize routine [Kernel-Mode Driver Architecture], wdm/RtlUnicodeStringToAnsiSize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlUnicodeStringToAnsiSize
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlUnicodeStringToAnsiSize macro


## -description


The <b>RtlUnicodeStringToAnsiSize</b> routine returns the number of bytes required for a null-terminated ANSI string that is equivalent to a specified Unicode string.


## -syntax


````
ULONG RtlUnicodeStringToAnsiSize(
  _In_ PUNICODE_STRING UnicodeString
);
````


## -parameters




### -param STRING

TBD




#### - UnicodeString [in]

Pointer to the Unicode string for which to compute the number of bytes required for an equivalent null-terminated ANSI string.


## -remarks


The Unicode string is interpreted for the current system locale.

<b>RtlUnicodeStringToAnsiSize</b> performs the same operation as <a href="..\wdm\nf-wdm-rtlxunicodestringtoansisize.md">RtlxUnicodeStringToAnsiSize</a>, but executes faster if the system does not use multibyte code pages.



## -see-also

<a href="..\wdm\nf-wdm-rtlxunicodestringtoansisize.md">RtlxUnicodeStringToAnsiSize</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlUnicodeStringToAnsiSize routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

