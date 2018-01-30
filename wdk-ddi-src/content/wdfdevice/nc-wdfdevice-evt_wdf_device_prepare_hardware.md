---
UID: NC:wdfdevice.EVT_WDF_DEVICE_PREPARE_HARDWARE
title: EVT_WDF_DEVICE_PREPARE_HARDWARE
author: windows-driver-content
description: A driver's EvtDevicePrepareHardware event callback function performs any operations that are needed to make a device accessible to the driver.
old-location: wdf\evtdevicepreparehardware.htm
old-project: wdf
ms.assetid: a3d4a983-8a75-44be-bd72-8673d89f9f87
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtdevicepreparehardware, EvtDevicePrepareHardware callback function, EvtDevicePrepareHardware, EVT_WDF_DEVICE_PREPARE_HARDWARE, EVT_WDF_DEVICE_PREPARE_HARDWARE, wdfdevice/EvtDevicePrepareHardware, DFDeviceObjectGeneralRef_a447de77-9692-4a48-83c2-3ced294863e4.xml, kmdf.evtdevicepreparehardware
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdfdevice.h
apiname:
-	EvtDevicePrepareHardware
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# EVT_WDF_DEVICE_PREPARE_HARDWARE callback


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtDevicePrepareHardware</i> event callback function performs any operations that are needed to make a device accessible to the driver.


## -prototype


````
EVT_WDF_DEVICE_PREPARE_HARDWARE EvtDevicePrepareHardware;

NTSTATUS EvtDevicePrepareHardware(
  _In_ WDFDEVICE    Device,
  _In_ WDFCMRESLIST ResourcesRaw,
  _In_ WDFCMRESLIST ResourcesTranslated
)
{ ... }
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param ResourcesRaw [in]

A handle to a framework resource-list object that identifies the raw hardware resources that the Plug and Play manager has assigned to the device.


### -param ResourcesTranslated [in]

A handle to a framework resource-list object that identifies the translated hardware resources that the Plug and Play manager has assigned to the device.


## -returns


If the <i>EvtDevicePrepareHardware</i> callback function encounters no errors, it must return STATUS_SUCCESS or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise, it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. Do not return STATUS_NOT_SUPPORTED.

If NT_SUCCESS(status) equals <b>FALSE</b>, the framework calls the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a> callback function. 

For more information about this callback function's return values, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.



## -remarks


To register an <i>EvtDevicePrepareHardware</i> callback function, a driver must call <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks.md">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

If the driver has registered an <i>EvtDevicePrepareHardware</i> callback function for a device, the framework calls the function after the Plug and Play manager has assigned hardware resources to the device and after the device has entered its uninitialized D0 state. (The Plug and Play manager always starts a parent device before it starts that device's child devices.)

The framework calls the driver's <i>EvtDevicePrepareHardware</i> callback function before calling the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_entry.md">EvtDeviceD0Entry</a> callback function.

The <i>EvtDevicePrepareHardware</i> callback function accesses the device's raw and translated hardware resources by using the <i>ResourcesRaw</i> and <i>ResourcesTranslated</i> handles that it receives. The callback function can call <a href="..\wdfresource\nf-wdfresource-wdfcmresourcelistgetcount.md">WdfCmResourceListGetCount</a> and <a href="..\wdfresource\nf-wdfresource-wdfcmresourcelistgetdescriptor.md">WdfCmResourceListGetDescriptor</a> to traverse the resource lists. This callback function cannot modify the resource lists.

For more information about resource lists and the order in which the resources appear, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/raw-and-translated-resources">raw and translated hardware resources</a>.

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
Obtains <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-driver-defined-interfaces">driver-defined interfaces</a> from other drivers

</li>
</ul>Optionally, your driver's <i>EvtDevicePrepareHardware</i> callback function might queue a work item to complete any other time-intensive configuration tasks. Using a work item for such operations can help ensure that your device's start up time does not increase the system boot time. For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-framework-work-items">Using Framework Work Items</a>.

Typically, all other hardware initialization operations, including loading firmware, should take place each time that the device enters its working (D0) state and should therefore take place in the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_entry.md">EvtDeviceD0Entry</a> callback function.

The <i>ResourcesRaw</i> and <i>ResourcesTranslated</i> handles that the <i>EvtDevicePrepareHardware</i> callback function receives remain valid until the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a> callback function returns.

For more information about hardware resources, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.

For more information about when the framework calls this callback function, see <a href="https://msdn.microsoft.com/9175ce95-196d-44bd-b31c-88386fa0d3d3">PnP and Power Management Scenarios</a>.

For more information about drivers that provide this callback function, see <a href="https://msdn.microsoft.com/487d4a69-a8a8-406c-8572-688388deabe3">Supporting PnP and Power Management in Function Drivers</a>.



## -see-also

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_PREPARE_HARDWARE callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

