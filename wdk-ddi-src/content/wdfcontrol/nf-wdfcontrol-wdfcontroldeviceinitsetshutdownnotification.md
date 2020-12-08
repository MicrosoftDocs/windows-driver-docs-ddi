---
UID: NF:wdfcontrol.WdfControlDeviceInitSetShutdownNotification
title: WdfControlDeviceInitSetShutdownNotification function (wdfcontrol.h)
description: The WdfControlDeviceInitSetShutdownNotification method sets shutdown notification information for a control device object.
old-location: wdf\wdfcontroldeviceinitsetshutdownnotification.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfControlDeviceInitSetShutdownNotification function"]
ms.keywords: DFDeviceObjectControllerDevObjRef_ee736de4-6e27-46d9-8f83-40d7368c960a.xml, WdfControlDeviceInitSetShutdownNotification, WdfControlDeviceInitSetShutdownNotification method, kmdf.wdfcontroldeviceinitsetshutdownnotification, wdf.wdfcontroldeviceinitsetshutdownnotification, wdfcontrol/WdfControlDeviceInitSetShutdownNotification
req.header: wdfcontrol.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: ControlDeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfControlDeviceInitSetShutdownNotification
 - wdfcontrol/WdfControlDeviceInitSetShutdownNotification
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfControlDeviceInitSetShutdownNotification
---

# WdfControlDeviceInitSetShutdownNotification function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfControlDeviceInitSetShutdownNotification</b> method sets shutdown notification information for a control device object.

## -parameters

### -param DeviceInit 

[in]
A pointer to a <a href="/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure that the driver obtained by calling <a href="/windows-hardware/drivers/ddi/wdfcontrol/nf-wdfcontrol-wdfcontroldeviceinitallocate">WdfControlDeviceInitAllocate</a>.

### -param Notification 

[in]
A pointer to the driver's <a href="/windows-hardware/drivers/ddi/wdfcontrol/nc-wdfcontrol-evt_wdf_device_shutdown_notification">EvtDeviceShutdownNotification</a> event callback function.

### -param Flags 

[in]
One or more <a href="/windows-hardware/drivers/ddi/wdfcontrol/ne-wdfcontrol-_wdf_device_shutdown_flags">WDF_DEVICE_SHUTDOWN_FLAGS</a>-typed flags that indicate when the <a href="/windows-hardware/drivers/ddi/wdfcontrol/nc-wdfcontrol-evt_wdf_device_shutdown_notification">EvtDeviceShutdownNotification</a> callback function will be called.

## -remarks

The driver must call <b>WdfControlDeviceInitSetShutdownNotification</b> before calling <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>. For more information about calling <b>WdfControlDeviceInitSetShutdownNotification</b>, see <a href="/windows-hardware/drivers/wdf/using-control-device-objects">Using Control Device Objects</a>.


#### Examples

For a code example that uses <b>WdfControlDeviceInitSetShutdownNotification</b>, see <a href="/windows-hardware/drivers/ddi/wdfcontrol/nf-wdfcontrol-wdfcontroldeviceinitallocate">WdfControlDeviceInitAllocate</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfcontrol/nc-wdfcontrol-evt_wdf_device_shutdown_notification">EvtDeviceShutdownNotification</a>



<a href="/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a>



<a href="/windows-hardware/drivers/ddi/wdfcontrol/ne-wdfcontrol-_wdf_device_shutdown_flags">WDF_DEVICE_SHUTDOWN_FLAGS</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>
