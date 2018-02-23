---
UID: NF:wdm.KeInitializeTimerEx
title: KeInitializeTimerEx function
author: windows-driver-content
description: The KeInitializeTimerEx routine initializes an extended kernel timer object.
old-location: kernel\keinitializetimerex.htm
old-project: kernel
ms.assetid: 57ed4f33-6ce6-41ae-b424-147318ba7656
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: KeInitializeTimerEx routine [Kernel-Mode Driver Architecture], wdm/KeInitializeTimerEx, k105_62ca8d08-a87a-4cbd-80fa-18b646b8500d.xml, KeInitializeTimerEx, kernel.keinitializetimerex
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
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeInitializeTimerEx
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeInitializeTimerEx function


## -description


The <b>KeInitializeTimerEx</b> routine initializes an extended kernel timer object.


## -syntax


````
VOID KeInitializeTimerEx(
  _Out_ PKTIMER    Timer,
  _In_  TIMER_TYPE Type
);
````


## -parameters




### -param Timer [out]

Pointer to a timer object, for which the caller provides the storage.


### -param Type [in]

Specifies the type of the timer object, either <b>NotificationTimer</b> or <b>SynchronizationTimer</b>.


## -returns



None




## -remarks



The timer object is initialized to a not-signaled state.

Storage for a timer object must be resident: in the device extension of a driver-created device object, in the controller extension of a driver-created controller object, or in nonpaged pool allocated by the caller.

When a notification timer expires, all waiting threads are released and the timer remains in the signaled state until it is explicitly reset. When a synchronization timer expires, it is set to a signaled state until a single waiting thread is released and then the timer is reset to a not-signaled state.

Callers of <b>KeInitializeTimerEx</b> should be running at IRQL = DISPATCH_LEVEL or lower. It is best to initialize timers at IRQL = PASSIVE_LEVEL.

For more information about timer objects, see <a href="https://msdn.microsoft.com/b58487de-6e9e-45f4-acb8-9233c8718ee2">Timer Objects and DPCs</a>.

Use <a href="..\wdm\nf-wdm-kesettimer.md">KeSetTimer</a> or <a href="..\wdm\nf-wdm-kesettimerex.md">KeSetTimerEx</a> to define when the timer will expire.




## -see-also

<a href="..\wdm\nf-wdm-kecanceltimer.md">KeCancelTimer</a>



<a href="..\wdm\nf-wdm-kesettimerex.md">KeSetTimerEx</a>



<a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a>



<a href="..\wdm\nf-wdm-kereadstatetimer.md">KeReadStateTimer</a>



<a href="..\wdm\nf-wdm-kewaitformultipleobjects.md">KeWaitForMultipleObjects</a>



<a href="..\wdm\nf-wdm-kesettimer.md">KeSetTimer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeInitializeTimerEx routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

