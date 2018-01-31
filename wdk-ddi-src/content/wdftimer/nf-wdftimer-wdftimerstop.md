---
UID: NF:wdftimer.WdfTimerStop
title: WdfTimerStop function
author: windows-driver-content
description: The WdfTimerStop method stops a timer's clock.
old-location: wdf\wdftimerstop.htm
old-project: wdf
ms.assetid: 394593f5-92eb-4f84-adbe-67e0e5320ff0
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: DFTimerObjectRef_6b433db6-e7a0-4521-961d-56c3de8a97ad.xml, wdf.wdftimerstop, WdfTimerStop, WdfTimerStop method, kmdf.wdftimerstop, wdftimer/WdfTimerStop
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfTimerStop
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_SEND_OPTIONS, *PWDF_REQUEST_SEND_OPTIONS
req.product: Windows 10 or later.
---

# WdfTimerStop function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfTimerStop</b> method stops a timer's clock.


## -syntax


````
BOOLEAN WdfTimerStop(
  _In_ WDFTIMER Timer,
  _In_ BOOLEAN  Wait
);
````


## -parameters




#### - Timer [in]

A handle to a framework timer object that was obtained by calling <a href="..\wdftimer\nf-wdftimer-wdftimercreate.md">WdfTimerCreate</a>.


#### - Wait [in]

<b>KMDF </b>A Boolean value that, if <b>TRUE</b>, specifies that the framework does not return until all queued calls to the driver's deferred procedure calls (DPCs), including the driver's <a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a> callback functions, have executed. 

<b>UMDF </b>A Boolean value that, if <b>TRUE</b>, specifies that the framework does not return until all queued calls to the timer's <a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a> callback function have executed.


## -returns


<b>WdfTimerStop</b> returns <b>TRUE</b> if the timer object was in the system's timer queue. Otherwise, this method returns <b>FALSE</b>. For more information, see the following Remarks section. 

A bug check occurs if the driver supplies an invalid object handle.



## -remarks


When a driver calls <a href="..\wdftimer\nf-wdftimer-wdftimerstart.md">WdfTimerStart</a>, its timer object is added to the system's queue of timer objects. If the timer is not a periodic timer, the system removes the timer object from the queue after the timer's "due time" has elapsed. If the timer is a periodic timer, the timer object remains in the queue until the driver calls <b>WdfTimerStop</b>. 

<b>WdfTimerStop</b> must be called at IRQL = PASSIVE_LEVEL if the <i>Wait</i> parameter is <b>TRUE</b>. Otherwise, this method must be called at IRQL &lt;= DISPATCH_LEVEL.

If the timer callback restarts the timer, <code>WdfTimerStop(Wait=TRUE)</code> will also wait for the new instance of the timer to finish.

Do not call <b>WdfTimerStop</b> from inside <a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a> with the <i>Wait</i> parameter set to <b>TRUE</b>.  Doing so may result in deadlock.

For more information about framework timer objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-timers">Using Timers</a>.



## -see-also

<a href="..\wdftimer\nf-wdftimer-wdftimerstart.md">WdfTimerStart</a>

<a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a>

<a href="..\wdftimer\nf-wdftimer-wdftimercreate.md">WdfTimerCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfTimerStop method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

