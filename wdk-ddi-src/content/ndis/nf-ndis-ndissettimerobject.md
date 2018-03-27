---
UID: NF:ndis.NdisSetTimerObject
title: NdisSetTimerObject function
author: windows-driver-content
description: The NdisSetTimerObject function sets a timer object to fire after a specified interval or periodically.
old-location: netvista\ndissettimerobject.htm
old-project: netvista
ms.assetid: 75f8fa1b-5b79-4bc2-8b7b-aa1101c9c331
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisSetTimerObject, NdisSetTimerObject function [Network Drivers Starting with Windows Vista], ndis/NdisSetTimerObject, ndis_timer_ref_7be2aa63-67ef-4416-87d5-d11260a57d3f.xml, netvista.ndissettimerobject
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisSetTimerObject
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisSetTimerObject function


## -description


The 
  <b>NdisSetTimerObject</b> function sets a timer object to fire after a specified interval or
  periodically.


## -parameters




### -param TimerObject [in]

A handle to a timer object that NDIS provides when a driver calls the 
     <a href="https://msdn.microsoft.com/feb5e4cf-7e23-434e-9dc5-bb445a6f5606">
     NdisAllocateTimerObject</a> function.


### -param DueTime [in]

The absolute or relative time at which the timer is to expire. If the value of the 
     <i>DueTime</i> parameter is negative, the expiration time is relative to the current system time.
     Otherwise, the expiration time is absolute. The expiration time is expressed in system time units
     (100-nanosecond intervals). Absolute expiration times track any changes in the system time; relative
     expiration times are not affected by system time changes.


### -param MillisecondsPeriod [in, optional]

The periodic time interval, in milliseconds, that elapses between each time the timer fires and
     the next call to the 
     <i>NetTimerCallback</i> function, unless the timer is canceled. The value of this parameter must be less
     than or equal to MAXLONG.


### -param FunctionContext [in, optional]

A pointer to a caller-supplied context area that NDIS passes to the associated 
     <i>NetTimerCallback</i> function when a timer fires. If this parameter is <b>NULL</b>, NDIS uses the default
     value that is specified in the 
     <a href="https://msdn.microsoft.com/9a62e94c-f635-4ab7-b439-b98c60ba2854">
     NDIS_TIMER_CHARACTERISTICS</a> structure.


## -returns



<b>NdisSetTimerObject</b> returns <b>TRUE</b> if the timer object was already in the system timer queue;
     otherwise, it returns <b>FALSE</b>.




## -remarks



After a driver calls 
    <b>NdisSetTimerObject</b>, the timer object is queued until the interval that is specified in the 
    <i>DueTime</i> parameter expires. After the interval expires, the timer object is dequeued and the
    caller-supplied 
    <a href="https://msdn.microsoft.com/76e59376-58a4-4e35-bac4-ec5938c88cd7">NetTimerCallback</a> function is run once
    at IRQL = DISPATCH_LEVEL as soon as a processor becomes available.

If a nonzero value is specified in the 
    <i>MillisecondsPeriod</i> parameter, the timer object is queued again until the interval that is specified
    in 
    <i>MillisecondsPeriod</i> expires. After this interval expires, the timer object is requeued and the
    caller-supplied 
    <i>NetTimerCallback</i> function is run once at IRQL = DISPATCH_LEVEL as soon as a processor becomes
    available.

<div class="alert"><b>Note</b>  Starting with Windows 7, you can reduce power consumption by calling 
    <a href="https://msdn.microsoft.com/f6f50bba-cda5-41ed-9e0b-1aea5113a22b">
    NdisSetCoalescableTimerObject</a> instead of 
    <b>NdisSetTimerObject</b> if exact timer precision is not required.</div>
<div> </div>
For more information about timer behavior, see 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff553292">KeSetTimerEx</a>.

To cancel a timer, call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561624">NdisCancelTimerObject</a> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553292">KeSetTimerEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567886">NDIS_TIMER_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561618">NdisAllocateTimerObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561624">NdisCancelTimerObject</a>



<a href="https://msdn.microsoft.com/f6f50bba-cda5-41ed-9e0b-1aea5113a22b">
   NdisSetCoalescableTimerObject</a>



<a href="https://msdn.microsoft.com/76e59376-58a4-4e35-bac4-ec5938c88cd7">NetTimerCallback</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisSetTimerObject function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

