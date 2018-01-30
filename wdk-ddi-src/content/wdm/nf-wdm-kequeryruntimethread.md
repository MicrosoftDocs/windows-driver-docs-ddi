---
UID: NF:wdm.KeQueryRuntimeThread
title: KeQueryRuntimeThread function
author: windows-driver-content
description: The KeQueryRuntimeThread routine reports the accumulated kernel-mode and user-mode run time of a thread, in clock ticks.
old-location: kernel\kequeryruntimethread.htm
old-project: kernel
ms.assetid: 300720f6-8049-4558-ba8b-ecdbb8a59dbd
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeQueryRuntimeThread, k105_e8f1a28f-98f1-447c-bb72-1d1da6b50f01.xml, kernel.kequeryruntimethread, KeQueryRuntimeThread routine [Kernel-Mode Driver Architecture], wdm/KeQueryRuntimeThread
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
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
-	KeQueryRuntimeThread
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeQueryRuntimeThread function


## -description


The <b>KeQueryRuntimeThread</b> routine reports the accumulated kernel-mode and user-mode run time of a thread, in clock ticks.


## -syntax


````
ULONG KeQueryRuntimeThread(
  _In_  PKTHREAD Thread,
  _Out_ PULONG   UserTime
);
````


## -parameters




### -param Thread [in]

Pointer to a dispatcher object of type KTHREAD.


### -param UserTime [out]

Pointer to the memory location where <b>KeQueryRuntimeThread</b> returns the accumulated user-mode run time of the current thread, in clock ticks.


## -returns


<b>KeQueryRuntimeThread</b> returns the accumulated kernel-mode run time of the current thread, in clock ticks.



## -see-also

<a href="..\wdm\nf-wdm-kequerytimeincrement.md">KeQueryTimeIncrement</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeQueryRuntimeThread routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

