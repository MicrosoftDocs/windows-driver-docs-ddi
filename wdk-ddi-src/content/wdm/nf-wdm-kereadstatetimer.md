---
UID: NF:wdm.KeReadStateTimer
title: KeReadStateTimer function
author: windows-driver-content
description: The KeReadStateTimer routine reads the current state of a timer object.
old-location: kernel\kereadstatetimer.htm
old-project: kernel
ms.assetid: 0f7fc534-4a81-42e0-a3e6-8b91baa28b55
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.kereadstatetimer, wdm/KeReadStateTimer, KeReadStateTimer routine [Kernel-Mode Driver Architecture], k105_8e101501-f419-40ff-91cd-a8aee0ffcbc8.xml, KeReadStateTimer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlKeDispatchLte, HwStorPortProhibitedDDIs
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
-	KeReadStateTimer
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeReadStateTimer function


## -description


The <b>KeReadStateTimer</b> routine reads the current state of a timer object.


## -syntax


````
BOOLEAN KeReadStateTimer(
  _In_ PKTIMER Timer
);
````


## -parameters




#### - Timer [in]

A pointer to an initialized timer object, for which the caller provides the storage.


## -returns


<b>KeReadStateTimer</b> returns <b>TRUE</b> if the current state of the timer object is signaled; otherwise, it returns <b>FALSE</b>.



## -remarks


This routine provides an efficient way to poll the signal state of a timer. <b>KeReadStateTimer</b> reads the state of the timer without synchronizing its access to the timer. Do not assume that accesses of a timer state by <b>KeReadStateTimer</b> are mutually exclusive of accesses by routines, such as <a href="..\wdm\nf-wdm-kesettimer.md">KeSetTimer</a> and <a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a>, that do synchronize their access to the timer state.

For more information about timer objects, see <a href="https://msdn.microsoft.com/b58487de-6e9e-45f4-acb8-9233c8718ee2">Timer Objects and DPCs</a>.



## -see-also

<a href="..\wdm\nf-wdm-keinitializetimer.md">KeInitializeTimer</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554250">KTIMER</a>

<a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a>

<a href="..\wdm\nf-wdm-kecanceltimer.md">KeCancelTimer</a>

<a href="..\wdm\nf-wdm-kesettimer.md">KeSetTimer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeReadStateTimer routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

