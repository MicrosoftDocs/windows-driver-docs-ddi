---
UID: NC:wdfpdo.EVT_WDF_DEVICE_SET_LOCK
title: EVT_WDF_DEVICE_SET_LOCK (wdfpdo.h)
description: A driver's EvtDeviceSetLock event callback function locks the specified device so that it cannot be ejected, or unlocks the device so that it can be ejected.
old-location: wdf\evtdevicesetlock.htm
tech.root: wdf
ms.assetid: 2ac42710-9f44-4982-a0d9-c49048870aeb
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_932fbb3b-df8b-49ca-9b86-3d98b6fdd39f.xml, EVT_WDF_DEVICE_SET_LOCK, EVT_WDF_DEVICE_SET_LOCK callback, EvtDeviceSetLock, EvtDeviceSetLock callback function, kmdf.evtdevicesetlock, wdf.evtdevicesetlock, wdfpdo/EvtDeviceSetLock
f1_keywords:
 - "wdfpdo/EvtDeviceSetLock"
req.header: wdfpdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
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
- Wdfpdo.h
api_name:
- EvtDeviceSetLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_SET_LOCK callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtDeviceSetLock</i> event callback function locks the specified device so that it cannot be ejected, or unlocks the device so that it can be ejected.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param IsLocked [in]

A Boolean value that indicates whether the driver must lock or unlock the device. If <b>TRUE</b>, the driver must lock the device so that it cannot be ejected. If <b>FALSE</b>, the driver must unlock the device so that it can be ejected. 


## -returns



If the driver successfully locks or unlocks the device, it must return STATUS_SUCCESS. Otherwise it must return an NTSTATUS value that <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NT_SUCCESS</a> evaluates as <b>FALSE</b>.

 

For more information about this callback function's return values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.






## -remarks



Framework-based bus drivers can provide an <i>EvtDeviceSetLock</i> callback function. To register this callback function, bus drivers call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nf-wdfpdo-wdfpdoinitseteventcallbacks">WdfPdoInitSetEventCallbacks</a>.

The framework calls the driver's <i>EvtDeviceSetLock</i> callback function when the PnP manager requests the bus driver to lock or unlock one of its enumerated child devices. 

Not implementing an <i>EvtDeviceSetLock</i> callback function for a device is equivalent to returning an NTSTATUS value that evaluates as <b>FALSE</b>.

For more information about return values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-ejectable-devices">Supporting Ejectable Devices</a>.


#### Examples

To define an <i>EvtDeviceSetLock</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceSetLock</i> callback function that is named <i>MyDeviceSetLock</i>, use the <b>EVT_WDF_DEVICE_SET_LOCK</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_SET_LOCK  MyDeviceSetLock;</pre>
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
 MyDeviceSetLock (
    WDFDEVICE  Device,
    BOOLEAN  IsLocked
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_SET_LOCK</b> function type is defined in the Wdfpdo.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_SET_LOCK</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nc-wdfpdo-evt_wdf_device_eject">EvtDeviceEject</a>
 

 

