---
UID: NF:wdm.ExFlushLookasideListEx
title: ExFlushLookasideListEx function
author: windows-driver-content
description: The ExFlushLookasideListEx routine flushes all entries from the specified lookaside list and frees the allocated storage for each entry.
old-location: kernel\exflushlookasidelistex.htm
old-project: kernel
ms.assetid: 38601573-750f-46fc-ae04-cef0d90d9ea9
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ExFlushLookasideListEx routine [Kernel-Mode Driver Architecture], ExFlushLookasideListEx, k102_bb02a725-bc22-4c22-91f2-0232c1cb0f1f.xml, kernel.exflushlookasidelistex, wdm/ExFlushLookasideListEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ExFlushLookasideListEx
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExFlushLookasideListEx function


## -description


The <b>ExFlushLookasideListEx</b> routine flushes all entries from the specified lookaside list and frees the allocated storage for each entry.


## -syntax


````
VOID ExFlushLookasideListEx(
  _Inout_ PLOOKASIDE_LIST_EX Lookaside
);
````


## -parameters




### -param Lookaside [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554329">LOOKASIDE_LIST_EX</a> structure that describes a lookaside list. This structure was previously initialized by the <a href="..\wdm\nf-wdm-exinitializelookasidelistex.md">ExInitializeLookasideListEx</a> routine.


## -returns


None



## -remarks


On return from this routine, the lookaside list is empty and the allocated storage for all its entries has been freed.

For more information about lookaside lists, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565416">Using Lookaside Lists</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554329">LOOKASIDE_LIST_EX</a>

<a href="..\wdm\nf-wdm-exinitializelookasidelistex.md">ExInitializeLookasideListEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExFlushLookasideListEx routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

