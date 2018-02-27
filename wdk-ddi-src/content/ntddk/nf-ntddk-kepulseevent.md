---
UID: NF:ntddk.KePulseEvent
title: KePulseEvent function
author: windows-driver-content
description: The KePulseEvent routine atomically sets an event object to a signaled state, attempts to satisfy as many waits as possible, and then resets the event object to a not-signaled state.
old-location: kernel\kepulseevent.htm
old-project: kernel
ms.assetid: 57505700-9775-4dac-a106-951da0744631
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: KePulseEvent, KePulseEvent routine [Kernel-Mode Driver Architecture], k105_86079f76-4593-4ef2-ab1b-6f4c3ba17142.xml, kernel.kepulseevent, ntddk/KePulseEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
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
-	KePulseEvent
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# KePulseEvent function


## -description


The <b>KePulseEvent</b> routine atomically sets an event object to a signaled state, attempts to satisfy as many waits as possible, and then resets the event object to a not-signaled state. 


## -syntax


````
LONG KePulseEvent(
  _Inout_ PRKEVENT  Event,
  _In_    KPRIORITY Increment,
  _In_    BOOLEAN   Wait
);
````


## -parameters




### -param Event [in, out]

A pointer to a dispatcher object of type KEVENT. 


### -param Increment [in]

Specifies the priority increment that is to be applied if setting the event causes a wait to be satisfied.


### -param Wait [in]

Specifies a Boolean value that signifies whether the call to <b>KePulseEvent</b> will be immediately followed by a call to one of the <b>KeWait<i>Xxx</i></b> routines. If <b>TRUE</b>, the <b>KePulseEvent</b> call is immediately followed by a call to <a href="..\wdm\nf-wdm-kewaitformultipleobjects.md">KeWaitForMultipleObjects</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff553344">KeWaitForMutexObject</a>, or <a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a>. For more information, see the following Remarks section.


## -returns



The previous signal state of the event object.




## -remarks



For more information about event objects, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544323">Event Objects</a>.

The <b>KePulseEvent</b> routine might temporarily raise the IRQL. If the <i>Wait</i> parameter is <b>FALSE</b>, the routine, before it returns, restores the IRQL to the original value that it had at the start of the call.

If <i>Wait</i> = <b>TRUE</b>, the routine returns without lowering the IRQL. In this case, the <b>KePulseEvent</b> call must be immediately followed by a <b>KeWait<i>Xxx</i></b> call. By setting <i>Wait</i> = <b>TRUE</b>, the caller can prevent an unnecessary context switch from occurring between the <b>KePulseEvent</b> call and the <b>KeWait<i>Xxx</i></b> call. The <b>KeWait<i>Xxx</i></b> routine, before it returns, restores the IRQL to its original value at the start of the <b>KePulseEvent</b> call. Although the IRQL disables context switches between the two calls, these calls cannot reliably be used as the start and end of an atomic operation. For example, between these two calls, a thread that is running at the same time on another processor might change the state of the event object or of the target of the wait.

If the caller is executing at IRQL = DISPATCH_LEVEL or in an arbitrary thread context, the <i>Timeout</i> parameter to <b>KeWait<i>Xxx</i></b> must be zero.


<div class="alert"><b>Warning</b>    If a thread waiting for <i>Event</i> is currently running a kernel APC, then, when <b>KePulseEvent</b> is called, this thread's wait is not satisfied. After the kernel APC completes, the thread remains in the wait state.</div>
<div> </div>





## -see-also

<a href="..\wdm\nf-wdm-keinitializeevent.md">KeInitializeEvent</a>



<a href="..\wdm\nf-wdm-kereadstateevent.md">KeReadStateEvent</a>



<a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a>



<a href="..\wdm\nf-wdm-kesetevent.md">KeSetEvent</a>



<a href="..\wdm\nf-wdm-keresetevent.md">KeResetEvent</a>



<a href="..\wdm\nf-wdm-kewaitformultipleobjects.md">KeWaitForMultipleObjects</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553344">KeWaitForMutexObject</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KePulseEvent routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

