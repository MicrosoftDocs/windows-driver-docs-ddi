---
UID: NC:wdfdevice.EVT_WDF_DEVICE_SELF_MANAGED_IO_CLEANUP
title: EVT_WDF_DEVICE_SELF_MANAGED_IO_CLEANUP (wdfdevice.h)
description: A driver's EvtDeviceSelfManagedIoCleanup event callback function handles deallocation activity for the device's self-managed I/O operations, after a device has been removed.
old-location: wdf\evtdeviceselfmanagediocleanup.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_SELF_MANAGED_IO_CLEANUP callback function"]
ms.keywords: DFDeviceObjectGeneralRef_73e3f47e-1f3d-4dee-9fb2-62acbb5aaea2.xml, EVT_WDF_DEVICE_SELF_MANAGED_IO_CLEANUP, EVT_WDF_DEVICE_SELF_MANAGED_IO_CLEANUP callback, EvtDeviceSelfManagedIoCleanup, EvtDeviceSelfManagedIoCleanup callback function, kmdf.evtdeviceselfmanagediocleanup, wdf.evtdeviceselfmanagediocleanup, wdfdevice/EvtDeviceSelfManagedIoCleanup
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
 - EVT_WDF_DEVICE_SELF_MANAGED_IO_CLEANUP
 - wdfdevice/EVT_WDF_DEVICE_SELF_MANAGED_IO_CLEANUP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfdevice.h
api_name:
 - EvtDeviceSelfManagedIoCleanup
---

# EVT_WDF_DEVICE_SELF_MANAGED_IO_CLEANUP callback function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceSelfManagedIoCleanup</i> event callback function handles deallocation activity for the device's self-managed I/O operations, after a device has been removed.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

## -remarks

To register an <i>EvtDeviceSelfManagedIoCleanup</i> callback function, a driver must call <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

If the driver has registered an <i>EvtDeviceSelfManagedIoCleanup</i> callback function, the framework calls it after the specified device has been removed from the system. For more information about when the framework calls this callback function, see <a href="/windows-hardware/drivers/wdf/pnp-and-power-management-scenarios">PnP and Power Management Scenarios</a>.

The framework calls the driver's <i>EvtDeviceSelfManagedIoCleanup</i> callback function after it has called the driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_suspend">EvtDeviceSelfManagedIoSuspend</a> callback function. The <i>EvtDeviceSelfManagedIoCleanup</i> callback function must release any system resources that the driver allocated and associated with the device's self-managed I/O operations. 

For more information about when the framework calls this callback function, see <a href="/windows-hardware/drivers/wdf/pnp-and-power-management-scenarios">PnP and Power Management Scenarios</a>.

For more information about drivers that provide this callback function, see <a href="/windows-hardware/drivers/wdf/using-self-managed-i-o">Using Self-Managed I/O</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_flush">EvtDeviceSelfManagedIoFlush</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_init">EvtDeviceSelfManagedIoInit</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_restart">EvtDeviceSelfManagedIoRestart</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_suspend">EvtDeviceSelfManagedIoSuspend</a>
