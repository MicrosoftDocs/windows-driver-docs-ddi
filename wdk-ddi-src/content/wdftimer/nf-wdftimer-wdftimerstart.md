---
UID: NF:wdftimer.WdfTimerStart
title: WdfTimerStart function
author: windows-driver-content
description: The WdfTimerStart method starts a timer's clock.
old-location: wdf\wdftimerstart.htm
old-project: wdf
ms.assetid: 32c40be2-dee0-4ac7-9f78-a64b9f985f51
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFTimerObjectRef_42b50b58-85f6-4f1b-9824-f1c9ed675371.xml, WdfTimerStart, WdfTimerStart method, kmdf.wdftimerstart, wdf.wdftimerstart, wdftimer/WdfTimerStart
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdftimer.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfTimerStart
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_SEND_OPTIONS, *PWDF_REQUEST_SEND_OPTIONS
req.product: Windows 10 or later.
---

# WdfTimerStart function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfTimerStart</b> method starts a timer's clock.


## -syntax


````
BOOLEAN WdfTimerStart(
  _In_ WDFTIMER Timer,
  _In_ LONGLONG DueTime
);
````


## -parameters




### -param Timer [in]

A handle to a framework timer object that was obtained by calling <a href="..\wdftimer\nf-wdftimer-wdftimercreate.md">WdfTimerCreate</a>.


### -param DueTime [in]

A time period, in system time units (100-nanosecond intervals). The framework calls the driver's <a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a> callback function when the specified time period elapses. The time period value can be negative or positive as follows:
<ul>
<li>
If the value is negative, the time period is relative to the current system time.

</li>
<li>If the value is positive, the time period specifies an absolute time (which is actually relative to January 1, 1601).</li>
</ul>


<div class="alert"><b>Warning</b>  If you set the <b>UseHighResolutionTimer</b> member of <a href="..\wdftimer\ns-wdftimer-_wdf_timer_config.md">WDF_TIMER_CONFIG</a> to <b>WdfTrue</b>, you must call <b>WdfTimerStart</b> with the <i>DueTime</i> parameter set to a negative value.  Otherwise, the call causes the system to crash.</div>
<div> </div>
Relative times are not affected by any changes to the system time that might occur within the specified time period. Absolute times do reflect system time changes.

The framework provides <a href="https://msdn.microsoft.com/E7D5564D-7BAA-412E-959F-3655B963B4C1">time conversion functions</a> that convert time values into system time units.






## -returns



<b>WdfTimerStart</b> returns <b>TRUE</b> if the timer object was in the system's timer queue. Otherwise, this method returns <b>FALSE</b>. For more information, see the following Remarks section. 

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



After a driver calls <b>WdfTimerStart</b>, the framework calls the driver's <a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a> callback function when the time that is specified for the <i>DueTime</i> parameter elapses. After this first call, the framework calls the callback function each time that the time period that is specified by the <b>Period</b> member of the driver's <a href="..\wdftimer\ns-wdftimer-_wdf_timer_config.md">WDF_TIMER_CONFIG</a> structure elapses. 

The expiration of the timer ultimately depends on the granularity of the system clock. The value specified for <i>DueTime</i> guarantees that the framework calls the driver's <a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a> callback function on or after the given <i>DueTime</i>. However, <b>WdfTimerStart</b> cannot override the granularity of the system clock, whatever the value specified for <i>DueTime</i>. 

When a driver calls <b>WdfTimerStart</b>, its timer object is added to the system's queue of timer objects. If the timer is not a periodic timer, the system removes the timer object from the queue after the timer's "due time" has elapsed. If the timer is a periodic timer, the timer object remains in the queue until the driver calls <a href="..\wdftimer\nf-wdftimer-wdftimerstop.md">WdfTimerStop</a>.

A driver might call <b>WdfTimerStart</b> from its <a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a> callback function in order to restart a non-periodic timer after it expires.

<b>WdfTimerStart</b> returns <b>TRUE</b> if the driver has previously called <b>WdfTimerStart</b> and the timer object is still in the system's queue because the time period has not elapsed (or because it is a periodic timer). Before <b>WdfTimerStart</b> returns <b>TRUE</b>, the operating system resets the time period to the value that the driver specified in the new call to <b>WdfTimerStart</b>. The framework calls the <a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a> callback function only after the new time period elapses.

To stop the timer's clock, the driver can call <a href="..\wdftimer\nf-wdftimer-wdftimerstop.md">WdfTimerStop</a>.

For more information about framework timer objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-timers">Using Timers</a>.


#### Examples

The following code example starts a timer. The framework will call the timer's <a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a> callback function after 10 milliseconds. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BOOLEAN inTimerQueue;

inTimerQueue = WdfTimerStart(
                             timerHandle,
                             WDF_REL_TIMEOUT_IN_MS(10)
                             );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdftimer\ns-wdftimer-_wdf_timer_config.md">WDF_TIMER_CONFIG</a>



<a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a>



<a href="..\wdftimer\nf-wdftimer-wdftimercreate.md">WdfTimerCreate</a>



<a href="..\wdftimer\nf-wdftimer-wdftimerstop.md">WdfTimerStop</a>



 

 


