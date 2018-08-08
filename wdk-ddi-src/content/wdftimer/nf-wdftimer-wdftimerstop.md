---
UID: NF:wdftimer.WdfTimerStop
title: WdfTimerStop function
author: windows-driver-content
description: The WdfTimerStop method stops a timer's clock.
old-location: wdf\wdftimerstop.htm
tech.root: wdf
ms.assetid: 394593f5-92eb-4f84-adbe-67e0e5320ff0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFTimerObjectRef_6b433db6-e7a0-4521-961d-56c3de8a97ad.xml, WdfTimerStop, WdfTimerStop method, kmdf.wdftimerstop, wdf.wdftimerstop, wdftimer/WdfTimerStop
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
req.irql: See Remarks section.
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
-	WdfTimerStop
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfTimerStop function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfTimerStop</b> method stops a timer's clock.


## -parameters




### -param Timer [in]

A handle to a framework timer object that was obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550050">WdfTimerCreate</a>.


### -param Wait [in]

<b>KMDF </b>A Boolean value that, if <b>TRUE</b>, specifies that the framework does not return until all queued calls to the driver's deferred procedure calls (DPCs), including the driver's <a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a> callback functions, have executed. 

<b>UMDF </b>A Boolean value that, if <b>TRUE</b>, specifies that the framework does not return until all queued calls to the timer's <a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a> callback function have executed.


## -returns



<b>WdfTimerStop</b> returns <b>TRUE</b> if the timer object was in the system's timer queue. Otherwise, this method returns <b>FALSE</b>. For more information, see the following Remarks section. 

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



When a driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550054">WdfTimerStart</a>, its timer object is added to the system's queue of timer objects. If the timer is not a periodic timer, the system removes the timer object from the queue after the timer's "due time" has elapsed. If the timer is a periodic timer, the timer object remains in the queue until the driver calls <b>WdfTimerStop</b>. 

For more information about framework timer objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-timers">Using Timers</a>.

<b>WdfTimerStop</b> must be called at IRQL = PASSIVE_LEVEL if the <i>Wait</i> parameter is <b>TRUE</b>. Otherwise, this method must be called at IRQL &lt;= DISPATCH_LEVEL.



Do not call <b>WdfTimerStop</b> from inside <a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a> with the <i>Wait</i> parameter set to <b>TRUE</b>.  Doing so may result in deadlock.


#### Examples

The following code example stops a specified timer and waits for all of the driver's queued DPCs to execute.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfTimerStop(
             timerHandle,
             TRUE
             );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550050">WdfTimerCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550054">WdfTimerStart</a>
 

 

