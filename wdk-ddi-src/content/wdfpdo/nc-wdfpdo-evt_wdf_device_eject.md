---
UID: NC:wdfpdo.EVT_WDF_DEVICE_EJECT
title: EVT_WDF_DEVICE_EJECT (wdfpdo.h)
description: A driver's EvtDeviceEject event callback function handles operations that are necessary to eject a device from its docking station.
old-location: wdf\evtdeviceeject.htm
tech.root: wdf
ms.assetid: fc3f3a15-9a79-4275-9ba4-b01ab8851390
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_38feba70-59b4-4981-af2d-0fc0fa4ff68a.xml, EVT_WDF_DEVICE_EJECT, EVT_WDF_DEVICE_EJECT callback, EvtDeviceEject, EvtDeviceEject callback function, kmdf.evtdeviceeject, wdf.evtdeviceeject, wdfpdo/EvtDeviceEject
ms.topic: callback
f1_keywords:
 - "wdfpdo/EvtDeviceEject"
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
- EvtDeviceEject
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_EJECT callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtDeviceEject</i> event callback function handles operations that are necessary to eject a device from its docking station.


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns



If the operation succeeds, the driver must return STATUS_SUCCESS. Otherwise it must return an NTSTATUS value that <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a> evaluates as <b>FALSE</b>. Do not return STATUS_NOT_SUPPORTED.

For more information about return values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.




## -remarks



Framework-based bus drivers can provide an <i>EvtDeviceEject</i> callback function. A bus driver must provide an <i>EvtDeviceEject</i> callback function if the driver must perform operations that physically eject one of its enumerated child devices from the device's docking station. To register this callback function, the bus driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfpdo/nf-wdfpdo-wdfpdoinitseteventcallbacks">WdfPdoInitSetEventCallbacks</a>.

Before calling the <i>EvtDeviceEject</i> callback function, the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_exit">EvtDeviceD0Exit</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_release_hardware">EvtDeviceReleaseHardware</a> callback functions.

If a driver's <i>EvtDeviceEject</i> callback function returns STATUS_SUCCESS, the framework updates the driver's child list to indicate that the ejected device is no longer available. Therefore the driver does not have to call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfpdo/nf-wdfpdo-wdfpdomarkmissing">WdfPdoMarkMissing</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistupdatechilddescriptionasmissing">WdfChildListUpdateChildDescriptionAsMissing</a>.

For more information about device ejection, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-ejectable-devices">Supporting Ejectable Devices</a>.


#### Examples

To define an <i>EvtDeviceEject</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceEject</i> callback function that is named <i>MyDeviceEject</i>, use the <b>EVT_WDF_DEVICE_EJECT</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_EJECT  MyDeviceEject;</pre>
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
 MyDeviceEject (
    WDFDEVICE  Device
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_EJECT</b> function type is defined in the Wdfpdo.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_EJECT</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfpdo/nc-wdfpdo-evt_wdf_device_set_lock">EvtDeviceSetLock</a>
 

 

