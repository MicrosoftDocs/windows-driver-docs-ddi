---
UID: NC:wdfdevice.EVT_WDF_DEVICE_QUERY_REMOVE
title: EVT_WDF_DEVICE_QUERY_REMOVE (wdfdevice.h)
description: A driver's EvtDeviceQueryRemove event callback function determines whether a specified device can be stopped and removed.
old-location: wdf\evtdevicequeryremove.htm
tech.root: wdf
ms.assetid: 59e6a8bc-e2f9-4d26-92b0-8f8944e1aa88
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_e982c552-e635-4fa9-8d84-dc4d7c143925.xml, EVT_WDF_DEVICE_QUERY_REMOVE, EVT_WDF_DEVICE_QUERY_REMOVE callback, EvtDeviceQueryRemove, EvtDeviceQueryRemove callback function, kmdf.evtdevicequeryremove, wdf.evtdevicequeryremove, wdfdevice/EvtDeviceQueryRemove
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfdevice.h
api_name:
- EvtDeviceQueryRemove
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_QUERY_REMOVE callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceQueryRemove</i> event callback function determines whether a specified device can be stopped and removed.


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns



If the driver determines that the device can be stopped and removed, the <i>EvtDeviceQueryRemove</i> callback function must return STATUS_SUCCESS or another status value for which <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. Do not return STATUS_NOT_SUPPORTED.




## -remarks



To register an <i>EvtDeviceQueryRemove</i> callback function, a driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

If the device and driver support idle power-down, the device might not be in its working state when the framework calls the driver's <i>EvtDeviceQueryRemove</i> callback function. The callback function can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicestopidle">WdfDeviceStopIdle</a> to force the device into its working (D0) state, and then the callback function can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdeviceresumeidle">WdfDeviceResumeIdle</a> before it returns.

For more information about the <i>EvtDeviceQueryRemove</i> callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/handling-requests-to-stop-a-device">Handling Requests to Stop a Device</a>.

The framework does not synchronize the <i>EvtDeviceQueryRemove</i> callback function with other PnP and power management callback functions. For information about how the framework synchronizes the execution of a driver's event callback functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-automatic-synchronization">Using Automatic Synchronization</a>. 


#### Examples

To define an <i>EvtDeviceQueryRemove</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

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
The <b>EVT_WDF_DEVICE_QUERY_REMOVE</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_QUERY_REMOVE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_query_stop">EvtDeviceQueryStop</a>
 

 

