---
UID: NC:wdfdevice.EVT_WDF_DEVICE_PREPARE_HARDWARE
title: EVT_WDF_DEVICE_PREPARE_HARDWARE (wdfdevice.h)
description: A driver's EvtDevicePrepareHardware event callback function performs any operations that are needed to make a device accessible to the driver.
old-location: wdf\evtdevicepreparehardware.htm
tech.root: wdf
ms.assetid: a3d4a983-8a75-44be-bd72-8673d89f9f87
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_PREPARE_HARDWARE callback function"]
ms.keywords: DFDeviceObjectGeneralRef_a447de77-9692-4a48-83c2-3ced294863e4.xml, EVT_WDF_DEVICE_PREPARE_HARDWARE, EVT_WDF_DEVICE_PREPARE_HARDWARE callback, EvtDevicePrepareHardware, EvtDevicePrepareHardware callback function, kmdf.evtdevicepreparehardware, wdf.evtdevicepreparehardware, wdfdevice/EvtDevicePrepareHardware
f1_keywords:
 - "wdfdevice/EvtDevicePrepareHardware"
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
- EvtDevicePrepareHardware
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_PREPARE_HARDWARE callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDevicePrepareHardware</i> event callback function performs any operations that are needed to make a device accessible to the driver.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param ResourcesRaw [in]

A handle to a framework resource-list object that identifies the raw hardware resources that the Plug and Play manager has assigned to the device.


### -param ResourcesTranslated [in]

A handle to a framework resource-list object that identifies the translated hardware resources that the Plug and Play manager has assigned to the device.


## -returns



If the <i>EvtDevicePrepareHardware</i> callback function encounters no errors, it must return STATUS_SUCCESS or another status value for which <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise, it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. Do not return STATUS_NOT_SUPPORTED.

If NT_SUCCESS(status) equals <b>FALSE</b>, the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_release_hardware">EvtDeviceReleaseHardware</a> callback function. 

For more information about this callback function's return values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.




## -remarks



To register an <i>EvtDevicePrepareHardware</i> callback function, a driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

If the driver has registered an <i>EvtDevicePrepareHardware</i> callback function for a device, the framework calls the function after the Plug and Play manager has assigned hardware resources to the device and after the device has entered its uninitialized D0 state. (The Plug and Play manager always starts a parent device before it starts that device's child devices.)

The framework calls the driver's <i>EvtDevicePrepareHardware</i> callback function before calling the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_entry">EvtDeviceD0Entry</a> callback function.

The <i>EvtDevicePrepareHardware</i> callback function accesses the device's raw and translated hardware resources by using the <i>ResourcesRaw</i> and <i>ResourcesTranslated</i> handles that it receives. The callback function can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfresource/nf-wdfresource-wdfcmresourcelistgetcount">WdfCmResourceListGetCount</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfresource/nf-wdfresource-wdfcmresourcelistgetdescriptor">WdfCmResourceListGetDescriptor</a> to traverse the resource lists. This callback function cannot modify the resource lists.

For more information about resource lists and the order in which the resources appear, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/raw-and-translated-resources">raw and translated hardware resources</a>.

Typically, your driver's <i>EvtDevicePrepareHardware</i> callback function does the following, if necessary:

<ul>
<li>
Maps physical memory addresses to virtual addresses so the driver can access memory that is assigned to the device

</li>
<li>
Determines the device's revision number

</li>
<li>
Configures USB devices

</li>
<li>
Obtains <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-driver-defined-interfaces">driver-defined interfaces</a> from other drivers

</li>
</ul>
Optionally, your driver's <i>EvtDevicePrepareHardware</i> callback function might queue a work item to complete any other time-intensive configuration tasks. Using a work item for such operations can help ensure that your device's start up time does not increase the system boot time. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-framework-work-items">Using Framework Work Items</a>.

Typically, all other hardware initialization operations, including loading firmware, should take place each time that the device enters its working (D0) state and should therefore take place in the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_entry">EvtDeviceD0Entry</a> callback function.

The <i>ResourcesRaw</i> and <i>ResourcesTranslated</i> handles that the <i>EvtDevicePrepareHardware</i> callback function receives remain valid until the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_release_hardware">EvtDeviceReleaseHardware</a> callback function returns.

For more information about hardware resources, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.

For more information about when the framework calls this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/pnp-and-power-management-scenarios">PnP and Power Management Scenarios</a>.

For more information about drivers that provide this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-pnp-and-power-management-in-function-drivers">Supporting PnP and Power Management in Function Drivers</a>.


#### Examples

To define an <i>EvtDevicePrepareHardware</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDevicePrepareHardware</i> callback function that is named <i>MyDevicePrepareHardware</i>, use the <b>EVT_WDF_DEVICE_PREPARE_HARDWARE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_PREPARE_HARDWARE  MyDevicePrepareHardware;</pre>
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
 MyDevicePrepareHardware (
    WDFDEVICE  Device,
    WDFCMRESLIST  ResourcesRaw,
    WDFCMRESLIST  ResourcesTranslated
    )
 {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_PREPARE_HARDWARE</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_PREPARE_HARDWARE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_release_hardware">EvtDeviceReleaseHardware</a>
 

 

