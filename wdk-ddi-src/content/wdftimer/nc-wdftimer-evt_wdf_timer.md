---
UID: NC:wdftimer.EVT_WDF_TIMER
title: EVT_WDF_TIMER (wdftimer.h)
description: The EvtTimerFunc event callback function is called when a specified time period has elapsed.
old-location: wdf\evttimerfunc.htm
tech.root: wdf
ms.assetid: abe15fd9-620e-4c24-9a82-32d20a7e49cc
ms.date: 02/26/2018
ms.keywords: DFTimerObjectRef_adf533a0-e5e3-4036-b1fd-5071d010adb5.xml, EVT_WDF_TIMER, EVT_WDF_TIMER callback, EvtTimerFunc, EvtTimerFunc callback function, kmdf.evttimerfunc, wdf.evttimerfunc, wdftimer/EvtTimerFunc
ms.topic: callback
f1_keywords:
 - "wdftimer/EvtTimerFunc"
req.header: wdftimer.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdftimer.h
api_name:
- EvtTimerFunc
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_TIMER callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <i>EvtTimerFunc</i> event callback function is called when a specified time period has elapsed.


## -parameters




### -param Timer [in]

A handle to a framework timer object that was obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdftimer/nf-wdftimer-wdftimercreate">WdfTimerCreate</a>. 


## -returns



None




## -remarks



To register an <i>EvtTimerFunc</i> callback function and specify the time period that should elapse before the framework calls this function, your driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdftimer/nf-wdftimer-wdftimercreate">WdfTimerCreate</a>.

In KMDF versions prior to version 1.9, the framework implements <i>EvtTimerFunc</i> callback functions as deferred procedure calls (DPCs). Therefore, when a time period elapses, the system adds a call to an <i>EvtTimerFunc</i> callback function to a DPC queue. The system calls the <i>EvtTimerFunc</i> callback function at IRQL = DISPATCH_LEVEL when it reaches the front of the queue and a CPU that is running at IRQL < DISPATCH_LEVEL is available.

In KMDF versions 1.9 and later, by default the framework implements <i>EvtTimerFunc</i> callback functions as DPCs. Alternatively, if the driver sets the timer object's execution level to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ne-wdfobject-_wdf_execution_level">WdfExecutionLevelPassive</a>, the framework calls the <i>EvtTimerFunc</i> callback function from a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-framework-work-items">work item</a> at IRQL = PASSIVE_LEVEL. (Callback functions that are called at PASSIVE_LEVEL cannot delete timer objects.)

Starting in UMDF version 2.0, a UMDF driver's <i>EvtTimerFunc</i> callback functions always run at PASSIVE_LEVEL.

For more information about framework timer objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-timers">Using Timers</a>.


#### Examples

To define an <i>EvtTimerFunc</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtTimerFunc</i> callback function that is named <i>MyTimerFunc</i>, use the <b>EVT_WDF_TIMER</b> type as shown in this code example:

To define an <i>EvtTimerFunc</i> callback function that is named <b>MyTimerFunc</b>, you must first provide a function declaration that SDV and other verification tools require, as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_TIMER  MyTimerFunc;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyTimerFunc (
    WDFTIMER  Timer
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_TIMER</b> function type is defined in the Wdftimer.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_TIMER</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdftimer/nf-wdftimer-wdftimercreate">WdfTimerCreate</a>
 

 

