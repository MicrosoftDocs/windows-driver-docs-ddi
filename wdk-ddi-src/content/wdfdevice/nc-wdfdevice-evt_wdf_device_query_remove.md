---
UID: NC:wdfdevice.EVT_WDF_DEVICE_QUERY_REMOVE
title: EVT_WDF_DEVICE_QUERY_REMOVE
author: windows-driver-content
description: A driver's EvtDeviceQueryRemove event callback function determines whether a specified device can be stopped and removed.
old-location: wdf\evtdevicequeryremove.htm
old-project: wdf
ms.assetid: 59e6a8bc-e2f9-4d26-92b0-8f8944e1aa88
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_e982c552-e635-4fa9-8d84-dc4d7c143925.xml, EVT_WDF_DEVICE_QUERY_REMOVE, EVT_WDF_DEVICE_QUERY_REMOVE callback, EvtDeviceQueryRemove, EvtDeviceQueryRemove callback function, kmdf.evtdevicequeryremove, wdf.evtdevicequeryremove, wdfdevice/EvtDeviceQueryRemove
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfdevice.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdfdevice.h
api_name:
-	EvtDeviceQueryRemove
product: Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_QUERY_REMOVE callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtDeviceQueryRemove</i> event callback function determines whether a specified device can be stopped and removed.


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns



If the driver determines that the device can be stopped and removed, the <i>EvtDeviceQueryRemove</i> callback function must return STATUS_SUCCESS or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. Do not return STATUS_NOT_SUPPORTED.




## -remarks



To register an <i>EvtDeviceQueryRemove</i> callback function, a driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546135">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

If the device and driver support idle power-down, the device might not be in its working state when the framework calls the driver's <i>EvtDeviceQueryRemove</i> callback function. The callback function can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546921">WdfDeviceStopIdle</a> to force the device into its working (D0) state, and then the callback function can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546838">WdfDeviceResumeIdle</a> before it returns.

For more information about the <i>EvtDeviceQueryRemove</i> callback function, see <a href="https://msdn.microsoft.com/4c8f37b3-7961-4c78-a88b-3eec58155e66">Handling Requests to Stop a Device</a>.

The framework does not synchronize the <i>EvtDeviceQueryRemove</i> callback function with other PnP and power management callback functions. For information about how the framework synchronizes the execution of a driver's event callback functions, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-automatic-synchronization">Using Automatic Synchronization</a>. 


#### Examples

To define an <i>EvtDeviceQueryRemove</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceQueryRemove</i> callback function that is named <i>MyDeviceQueryRemove</i>, use the <b>EVT_WDF_DEVICE_QUERY_REMOVE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_QUERY_REMOVE  MyDeviceQueryRemove;</pre>
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
NTSTATUS
 MyDeviceQueryRemove (
    WDFDEVICE  Device
    )
 {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_QUERY_REMOVE</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_QUERY_REMOVE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/4f2ed29a-fed0-4286-81db-7a4c8a15a7dd">EvtDeviceQueryStop</a>
 

 

