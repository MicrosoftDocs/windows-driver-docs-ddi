---
UID: NC:wdfdevice.EVT_WDF_DEVICE_SELF_MANAGED_IO_RESTART
title: EVT_WDF_DEVICE_SELF_MANAGED_IO_RESTART (wdfdevice.h)
description: A driver's EvtDeviceSelfManagedIoRestart event callback function restarts a device's self-managed I/O operations.
old-location: wdf\evtdeviceselfmanagediorestart.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_SELF_MANAGED_IO_RESTART callback function"]
ms.keywords: DFDeviceObjectGeneralRef_31761962-577a-4a53-8b55-226801f42960.xml, EVT_WDF_DEVICE_SELF_MANAGED_IO_RESTART, EVT_WDF_DEVICE_SELF_MANAGED_IO_RESTART callback, EvtDeviceSelfManagedIoRestart, EvtDeviceSelfManagedIoRestart callback function, kmdf.evtdeviceselfmanagediorestart, wdf.evtdeviceselfmanagediorestart, wdfdevice/EvtDeviceSelfManagedIoRestart
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
req.irql: PASSIVE_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDF_DEVICE_SELF_MANAGED_IO_RESTART
 - wdfdevice/EVT_WDF_DEVICE_SELF_MANAGED_IO_RESTART
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfdevice.h
api_name:
 - EVT_WDF_DEVICE_SELF_MANAGED_IO_RESTART
---

# EVT_WDF_DEVICE_SELF_MANAGED_IO_RESTART callback function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceSelfManagedIoRestart</i> event callback function restarts a device's self-managed I/O operations.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

## -returns

If the <i>EvtDeviceSelfManagedIoRestart</i> callback function encounters no errors, it must return STATUS_SUCCESS, or another status value for which <a href="/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. If NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>, the framework stops the device and unloads the device's drivers. 

If NT_SUCCESS(status) equals <b>FALSE</b>, the framework calls the driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_flush">EvtDeviceSelfManagedIoFlush</a> and <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_cleanup">EvtDeviceSelfManagedIoCleanup</a> callback functions. 

For more information about this callback function's return values, see <a href="/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.

## -remarks

To register an <i>EvtDeviceSelfManagedIoRestart</i> callback function, a driver must call <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

If the driver has registered an <i>EvtDeviceSelfManagedIoRestart</i> callback function, the framework calls it each time that the device returns from a low-power state to its working (D0) state. The framework calls the <i>EvtDeviceSelfManagedIoRestart</i> callback function only after calling the driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_suspend">EvtDeviceSelfManagedIoSuspend</a> callback function.

The driver's <i>EvtDeviceSelfManagedIoRestart</i> callback function must do whatever is needed to resume the device's self-managed I/O operations.

For more information about when the framework calls this callback function, see <a href="/windows-hardware/drivers/wdf/pnp-and-power-management-scenarios">PnP and Power Management Scenarios</a>.

For more information about drivers that provide this callback function, see <a href="/windows-hardware/drivers/wdf/using-self-managed-i-o">Using Self-Managed I/O</a>.

The <i>EvtDeviceSelfManagedIoRestart</i> callback function is called at IRQL = PASSIVE_LEVEL. You should not make this callback function <a href="/windows-hardware/drivers/wdf/creating-pageable-code-in-a-kmdf-driver">pageable</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_cleanup">EvtDeviceSelfManagedIoCleanup</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_flush">EvtDeviceSelfManagedIoFlush</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_init">EvtDeviceSelfManagedIoInit</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_suspend">EvtDeviceSelfManagedIoSuspend</a>

