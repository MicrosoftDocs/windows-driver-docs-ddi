---
UID: NF:ndis.NdisCancelTimerObject
title: NdisCancelTimerObject function
author: windows-driver-content
description: The NdisCancelTimerObject function cancels a timer object that is associated with a previous call to the NdisSetTimerObject function.
old-location: netvista\ndiscanceltimerobject.htm
old-project: netvista
ms.assetid: b66652b7-2e02-49f5-a7e3-60ff35363a19
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NdisCancelTimerObject, NdisCancelTimerObject function [Network Drivers Starting with Windows Vista], ndis/NdisCancelTimerObject, ndis_timer_ref_39b68ae4-4fd7-4609-aebc-e2be21bead04.xml, netvista.ndiscanceltimerobject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Timer_Function, PeriodicTimer
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: See Remarks section
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisCancelTimerObject
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisCancelTimerObject function


## -description


The 
  <b>NdisCancelTimerObject</b> function cancels a timer object that is associated with a previous call to the 
  <a href="..\ndis\nf-ndis-ndissettimerobject.md">NdisSetTimerObject</a> function.


## -syntax


````
BOOLEAN NdisCancelTimerObject(
  _In_ NDIS_HANDLE TimerObject
);
````


## -parameters




### -param TimerObject [in]

A handle to a timer object that NDIS provides when a driver calls the 
     <a href="..\ndis\nf-ndis-ndisallocatetimerobject.md">
     NdisAllocateTimerObject</a> function.


## -returns



<b>NdisCancelTimerObject</b> returns <b>TRUE</b> if the specified timer object is in the system timer queue;
     otherwise, it returns <b>FALSE</b>.




## -remarks



A call to 
    <b>NdisCancelTimerObject</b> cancels execution of a 
    <a href="..\ndis\nc-ndis-ndis_timer_function.md">NetTimerCallback</a> function, provided
    that the last specified timeout interval has not yet expired.

NDIS drivers should call 
    <b>NdisCancelTimerObject</b> first when they are halting or unloading to ensure that a 
    <i>NetTimerCallback</i> function does not attempt to access resources that the driver has already
    released.

If a nonzero value was specified in the 
    <i>MillisecondsPeriod</i> parameter of the 
    <a href="..\ndis\nf-ndis-ndissettimerobject.md">NdisSetTimerObject</a> function, the timer is known as a <i>periodic timer</i>. If a zero value was specified in the <i>MillisecondsPeriod</i> parameter, the timer is known as a <i>one-shot timer</i>. The following points apply to canceling both types of timers:

<ul>
<li>
If  the caller of
    <b>NdisCancelTimerObject</b> is canceling a periodic timer, it must be running at IRQL = PASSIVE_LEVEL. Otherwise, the caller of 
    <b>NdisCancelTimerObject</b> should be running at IRQL &lt;= DISPATCH_LEVEL.

</li>
<li>
If  the caller of
    <b>NdisCancelTimerObject</b> is canceling a periodic timer, <b>NdisCancelTimerObject</b> calls <a href="..\wdm\nf-wdm-keflushqueueddpcs.md">KeFlushQueuedDpcs</a> to ensure that the timer is not currently running. Therefore, the caller is not required to have a separate synchronization mechanism to ensure that the timer is not currently being executed on another processor.

If  the caller of
    <b>NdisCancelTimerObject</b> is canceling a one-shot timer, the caller is required to have a separate synchronization mechanism to ensure the timer is not currently running on another processor. For example, the caller could call <a href="https://msdn.microsoft.com/library/windows/hardware/ff567897">NDIS_WAIT_FOR_MUTEX</a> in order to wait for the timer thread to signal a mutex object when the thread is about to complete.

For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/synchronization-and-notification-in-network-drivers">Synchronization and Notification in Network Drivers</a>.

</li>
</ul>



## -see-also

<a href="..\ndis\nc-ndis-ndis_timer_function.md">NetTimerCallback</a>



<a href="..\ndis\nf-ndis-ndissettimerobject.md">NdisSetTimerObject</a>



<a href="..\ndis\nf-ndis-ndisallocatetimerobject.md">NdisAllocateTimerObject</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCancelTimerObject function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

