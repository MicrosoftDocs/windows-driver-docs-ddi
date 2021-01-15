---
UID: NC:wdfdriver.EVT_WDF_DRIVER_DEVICE_ADD
title: EVT_WDF_DRIVER_DEVICE_ADD (wdfdriver.h)
description: A driver's EvtDriverDeviceAdd event callback function performs device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.
old-location: wdf\evtdriverdeviceadd.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["EVT_WDF_DRIVER_DEVICE_ADD callback function"]
ms.keywords: DFDriverObjectRef_9b5ff898-9b1b-4eb6-87f7-42bee5deab18.xml, EVT_WDF_DRIVER_DEVICE_ADD, EVT_WDF_DRIVER_DEVICE_ADD callback, EvtDriverDeviceAdd, EvtDriverDeviceAdd callback function, kmdf.evtdriverdeviceadd, wdf.evtdriverdeviceadd, wdfdriver/EvtDriverDeviceAdd
req.header: wdfdriver.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDF_DRIVER_DEVICE_ADD
 - wdfdriver/EVT_WDF_DRIVER_DEVICE_ADD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfdriver.h
api_name:
 - EVT_WDF_DRIVER_DEVICE_ADD
---

# EVT_WDF_DRIVER_DEVICE_ADD callback function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDriverDeviceAdd</i> event callback function performs device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.

## -parameters

### -param Driver 

[in]
A handle to a framework driver object that represents the driver.

### -param DeviceInit 

[in, out]
A pointer to a framework-allocated <a href="/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure.

## -returns

The<i>EvtDriverDeviceAdd</i> callback function must return STATUS_SUCCESS if the operation succeeds. Otherwise, this callback function must return one of the error status values that are defined in <i>Ntstatus.h</i>. For more information, see the following Remarks section.

## -remarks

Each framework-based driver that supports PnP devices must provide the <i>EvtDriverDeviceAdd</i> callback function. The driver must place the callback function's address in its <a href="/windows-hardware/drivers/ddi/wdfdriver/ns-wdfdriver-_wdf_driver_config">WDF_DRIVER_CONFIG</a> structure before calling <a href="/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdrivercreate">WdfDriverCreate</a>.

The framework calls your driver's <i>EvtDriverDeviceAdd</i> callback function after a bus driver detects a device that has a hardware identifier (ID) that matches a hardware ID that your driver supports. You specify the hardware IDs that your driver supports by providing an INF file, which the operating system uses to install drivers the first time that one of your devices is connected to the computer. For more information about how the system uses INF files and hardware IDs, see <a href="/windows-hardware/drivers/install/how-setup-selects-drivers">How Setup Selects Drivers</a>.

A driver's <i>EvtDriverDeviceAdd</i> callback function typically performs at least some of the following initialization operations:

<ul>
<li>

<a href="/windows-hardware/drivers/wdf/creating-a-framework-device-object">Create a framework device object</a> to represent the device.

</li>
<li>

<a href="/windows-hardware/drivers/wdf/creating-i-o-queues">Create I/O queues</a> so the driver can receive I/O requests.

</li>
<li>

<a href="/windows-hardware/drivers/wdf/using-device-interfaces">Create device interfaces</a> that applications use to communicate with the device.

</li>
<li>

<a href="/windows-hardware/drivers/wdf/using-driver-defined-interfaces">Create driver-defined interfaces</a> that other drivers can use.

</li>
<li>
Initialize <a href="/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Windows Management Instrumentation (WMI)</a> support.

</li>
<li>

<a href="/windows-hardware/drivers/wdf/creating-an-interrupt-object">Create interrupt objects</a>, if the driver handles device interrupts.

</li>
<li>

<a href="/windows-hardware/drivers/wdf/enabling-dma-transactions">Enable direct memory access (DMA) transactions</a>, if the driver handles DMA operations.

</li>
</ul>
Some drivers, especially filter drivers, might not create device objects for some devices. If an <i>EvtDriverDeviceAdd</i> callback function does not create a device object, it must still return STATUS_SUCCESS unless an error was encountered.

If a driver's <i>EvtDriverDeviceAdd</i> callback function creates a device object but does not return STATUS_SUCCESS, the framework deletes the device object and its child devices.

If a function driver's <i>EvtDriverDeviceAdd</i> callback function does not return STATUS_SUCCESS, the I/O manager does not build a device stack for the device.

If a filter driver's <i>EvtDriverDeviceAdd</i> callback function does not return STATUS_SUCCESS, the framework converts the return value to STATUS_SUCCESS, and the I/O manager builds the device stack without the filter driver.

## -see-also

<a href="/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a>



<a href="/windows-hardware/drivers/ddi/wdfdriver/ns-wdfdriver-_wdf_driver_config">WDF_DRIVER_CONFIG</a>



<a href="/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdrivercreate">WdfDriverCreate</a>

