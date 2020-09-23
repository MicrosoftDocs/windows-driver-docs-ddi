---
UID: NC:wdfdevice.EVT_WDF_DEVICE_SELF_MANAGED_IO_INIT
title: EVT_WDF_DEVICE_SELF_MANAGED_IO_INIT (wdfdevice.h)
description: A driver's EvtDeviceSelfManagedIoInit event callback function initializes and starts the device's self-managed I/O operations.
old-location: wdf\evtdeviceselfmanagedioinit.htm
tech.root: wdf
ms.assetid: 9dbc66db-ea94-4e6a-9618-00999a9dd641
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_SELF_MANAGED_IO_INIT callback function"]
ms.keywords: DFDeviceObjectGeneralRef_7c67b851-b6d0-450d-bdc9-2a32aa384a36.xml, EVT_WDF_DEVICE_SELF_MANAGED_IO_INIT, EVT_WDF_DEVICE_SELF_MANAGED_IO_INIT callback, EvtDeviceSelfManagedIoInit, EvtDeviceSelfManagedIoInit callback function, kmdf.evtdeviceselfmanagedioinit, wdf.evtdeviceselfmanagedioinit, wdfdevice/EvtDeviceSelfManagedIoInit
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
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDF_DEVICE_SELF_MANAGED_IO_INIT
 - wdfdevice/EVT_WDF_DEVICE_SELF_MANAGED_IO_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfdevice.h
api_name:
 - EvtDeviceSelfManagedIoInit
---

# EVT_WDF_DEVICE_SELF_MANAGED_IO_INIT callback function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceSelfManagedIoInit</i> event callback function initializes and starts the device's self-managed I/O operations.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

## -returns

If the <i>EvtDeviceSelfManagedIoInit</i> callback function encounters no errors, it must return STATUS_SUCCESS, or another status value for which <a href="/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise, it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. If NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>, the framework does not start the device.

If NT_SUCCESS(status) equals <b>FALSE</b>, the framework calls the driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_flush">EvtDeviceSelfManagedIoFlush</a> and <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_cleanup">EvtDeviceSelfManagedIoCleanup</a> callback functions.

For more information about this callback function's return values, see <a href="/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.

## -remarks

To register an <i>EvtDeviceSelfManagedIoInit</i> callback function, a driver must call <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

If the driver has registered an <i>EvtDeviceSelfManagedIoInit</i> callback function, the framework calls it once for each device, after the framework has called the driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_entry">EvtDeviceD0Entry</a> callback function for the first time. The framework does not call the <i>EvtDeviceSelfManagedIoInit</i> callback function again for that device, unless the device is removed and reconnected, or the drivers are reloaded.

The <i>EvtDeviceSelfManagedIoInit</i> callback function must initialize and start the self-managed I/O operations that the driver will handle for the device.

For more information about when the framework calls this callback function, see <a href="/windows-hardware/drivers/wdf/pnp-and-power-management-scenarios">PnP and Power Management Scenarios</a>.

For more information about drivers that provide this callback function, see <a href="/windows-hardware/drivers/wdf/using-self-managed-i-o">Using Self-Managed I/O</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_cleanup">EvtDeviceSelfManagedIoCleanup</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_flush">EvtDeviceSelfManagedIoFlush</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_restart">EvtDeviceSelfManagedIoRestart</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_suspend">EvtDeviceSelfManagedIoSuspend</a>