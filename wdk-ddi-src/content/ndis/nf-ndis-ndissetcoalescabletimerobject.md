---
UID: NF:ndis.NdisSetCoalescableTimerObject
title: NdisSetCoalescableTimerObject function (ndis.h)
description: The NdisSetCoalescableTimerObject function sets a timer object that the operating system coordinates with other timers, typically to reduce power consumption, when the exact expiration of the timer is not important to driver operation.
old-location: netvista\ndissetcoalescabletimerobject.htm
tech.root: netvista
ms.assetid: f6f50bba-cda5-41ed-9e0b-1aea5113a22b
ms.date: 05/02/2018
ms.keywords: NdisSetCoalescableTimerObject, NdisSetCoalescableTimerObject function [Network Drivers Starting with Windows Vista], ndis/NdisSetCoalescableTimerObject, ndis_timer_ref_1f787022-10cd-4ae1-97d9-f40bae70a844.xml, netvista.ndissetcoalescabletimerobject
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisSetCoalescableTimerObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisSetCoalescableTimerObject function


## -description


The 
  <b>NdisSetCoalescableTimerObject</b> function sets a timer object that the operating system coordinates with
  other timers, typically to reduce power consumption, when the exact expiration of the timer is not
  important to driver operation.


## -parameters




### -param TimerObject [in]

A handle to a timer object that NDIS provides when a driver calls the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisallocatetimerobject">
     NdisAllocateTimerObject</a> function.


### -param DueTime [in]

The absolute or relative time at which the timer will expire. If the value of the 
     <i>DueTime</i> parameter is negative, the expiration time is relative to the current system time.
     Otherwise, the expiration time is absolute. The expiration time is expressed in system time units
     (100-nanosecond intervals). Absolute expiration times track any changes in the system time; relative
     expiration times are not affected by system time changes.


### -param MillisecondsPeriod [in, optional]

The optional periodic time interval, in milliseconds, that elapses between every instance when the
     timer fires and the next call to the 
     <i>NetTimerCallback</i> function, unless the timer is canceled. The value of this parameter must be less
     than or equal to MAXLONG. This parameter can be set to zero to indicate that the timer is
     non-periodic.


### -param FunctionContext [in, optional]

A pointer to a caller-supplied context area that NDIS passes to the associated 
     <i>NetTimerCallback</i> function when a timer fires. If this parameter is <b>NULL</b>, NDIS uses the default
     value that is specified in the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_timer_characteristics">
     NDIS_TIMER_CHARACTERISTICS</a> structure.


### -param Tolerance [in, optional]

The tolerance, in milliseconds, between the timer period specified by 
     <i>MillisecondsPeriod</i> and the initial time interval specified by 
     <i>DueTime</i> . A periodic timer will first expire in the time interval between (
     <i>DueTime</i> - 
     <i>Tolerance</i> ) and (
     <i>DueTime</i> + 
     <i>Tolerance</i> ). The time interval between two later expirations of a periodic timer will be in the
     range of (
     <i>MillisecondsPeriod</i> - 
     <i>Tolerance</i> ) and (
     <i>MillisecondsPeriod</i> + 
     <i>Tolerance</i> ).


## -returns



<b>NdisSetCoalescableTimerObject</b> returns <b>TRUE</b> if the timer object was already in the system timer
     queue; otherwise, it returns <b>FALSE</b>.




## -remarks



A timer object set by this function operates the same as a timer set by 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndissettimerobject">NdisSetTimerObject</a>, with an additional
    tolerance value added to the expiration parameter 
    <i>DueTime</i> . The operating system uses this additional tolerance value to adjust the expiration time
    of the timer to coincide with the expiration of other software timers. By doing this, the operating
    system can reduce power consumption and improve energy efficiency.

<b>NdisSetTimerObject</b> operates similarly to 
    <b>NdisSetCoalescableTimerObject</b> when 
    <i>Tolerance</i> is set to zero.

After a driver calls 
    <b>NdisSetCoalescableTimerObject</b>, the timer object is queued until expiration of an interval that is
    in the range of (
    <i>DueTime</i> - 
    <i>Tolerance</i> ) and (
    <i>DueTime</i> + 
    <i>Tolerance</i> ). After the interval expires, the operating system removes the timer object from the
    queue, and the caller-supplied 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-ndis_timer_function">NetTimerCallback</a> function is run one
    time at IRQL = DISPATCH_LEVEL as soon as a processor becomes available.

If a nonzero value is specified in the 
    <i>MillisecondsPeriod</i> parameter, the timer object is queued again until an interval in the range of (
    <i>MillisecondsPeriod</i> - 
    <i>Tolerance</i> ) and (
    <i>MillisecondsPeriod</i> + 
    <i>Tolerance</i> ) expires. After this interval expires, the timer object is resubmitted to the queue, and
    the caller-supplied 
    <i>NetTimerCallback</i> function is run one time at IRQL = DISPATCH_LEVEL as soon as a processor becomes
    available.

To use timer coalescing effectively, a caller should specify a 
    <i>Tolerance</i> value of at least 32 milliseconds. This value equals approximately two default system
    clock intervals of 15.6 milliseconds. Use a larger 
    <i>Tolerance</i> value if you can do this, such as 100 milliseconds.

We recommend that 
    <i>MillisecondsPeriod</i> and 
    <i>Tolerance</i> be set to multiples of 50 milliseconds. Typical 
    <i>MillisecondsPeriod</i> values are 50, 100, 250, 500, and 1000 milliseconds. Typical 
    <i>Tolerance</i> values are 50, 100, 150, and 250 milliseconds.

Typically, a timer with a large 
    <i>MillisecondsPeriod</i> value can use a proportionally large 
    <i>Tolerance</i> value. For example, a timer with 
    <i>MillisecondsPeriod</i> = 500 milliseconds might use 
    <i>Tolerance</i> = 50 milliseconds. But a timer with 
    <i>MillisecondsPeriod</i> = 10 seconds might use 
    <i>Tolerance</i> = 1 second.

For more information about timer behavior, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kesettimerex">KeSetTimerEx</a>.

To cancel a timer, call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndiscanceltimerobject">NdisCancelTimerObject</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kesettimerex">KeSetTimerEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_timer_characteristics">NDIS_TIMER_CHARACTERISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisallocatetimerobject">NdisAllocateTimerObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndiscanceltimerobject">NdisCancelTimerObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndissettimerobject">NdisSetTimerObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-ndis_timer_function">NetTimerCallback</a>
 

 

