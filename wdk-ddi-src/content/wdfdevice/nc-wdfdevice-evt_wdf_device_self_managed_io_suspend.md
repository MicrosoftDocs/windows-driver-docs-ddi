---
UID: NC:wdfdevice.EVT_WDF_DEVICE_SELF_MANAGED_IO_SUSPEND
title: EVT_WDF_DEVICE_SELF_MANAGED_IO_SUSPEND (wdfdevice.h)
description: A driver's EvtDeviceSelfManagedIoSuspend event callback function suspends a device's self-managed I/O operations.
old-location: wdf\evtdeviceselfmanagediosuspend.htm
tech.root: wdf
ms.assetid: 85a569ea-eb14-4453-9591-fc44afbd3a59
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_SELF_MANAGED_IO_SUSPEND callback function"]
ms.keywords: DFDeviceObjectGeneralRef_10625e27-0ff8-47fa-aff0-ddca49c7f326.xml, EVT_WDF_DEVICE_SELF_MANAGED_IO_SUSPEND, EVT_WDF_DEVICE_SELF_MANAGED_IO_SUSPEND callback, EvtDeviceSelfManagedIoSuspend, EvtDeviceSelfManagedIoSuspend callback function, kmdf.evtdeviceselfmanagediosuspend, wdf.evtdeviceselfmanagediosuspend, wdfdevice/EvtDeviceSelfManagedIoSuspend
f1_keywords:
 - "wdfdevice/EvtDeviceSelfManagedIoSuspend"
 - "EvtDeviceSelfManagedIoSuspend"
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
- EvtDeviceSelfManagedIoSuspend
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_SELF_MANAGED_IO_SUSPEND callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceSelfManagedIoSuspend</i> event callback function suspends a device's self-managed I/O operations.


## -parameters




### -param Device 
[in]
A handle to a framework device object.


## -returns



If the operation is successful, the <i>EvtDeviceSelfManagedIoSuspend</i> callback function must return STATUS_SUCCESS, or another status value for which <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. If NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>, the framework stops the device and removes its device objects.

If NT_SUCCESS(status) equals <b>FALSE</b>, the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_flush">EvtDeviceSelfManagedIoFlush</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_cleanup">EvtDeviceSelfManagedIoCleanup</a> callback functions. 



For more information about this callback function's return values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.




## -remarks



To register an <i>EvtDeviceSelfManagedIoSuspend</i> callback function, a driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

If the driver has registered an <i>EvtDeviceSelfManagedIoSuspend</i> callback function, the framework calls it for one of the following reasons:

<ul>
<li>
The device is about to enter a low-power state.

</li>
<li>
The device is being removed or was surprise-removed.

</li>
<li>
The Plug and Play manager is about to redistribute the system's hardware resources among system's attached devices.

</li>
</ul>
Because you do not know which of these events causes the framework to call your driver, you must assume that the device might return to its working (D0) state.

If the device is about to enter a low-power state, the framework calls the driver's <i>EvtDeviceSelfManagedIoSuspend</i> callback function before it calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_exit">EvtDeviceD0Exit</a> callback function.

If the callback function returns a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>, and if the framework is attempting to lower the device's power, the framework stops the device and removes its device objects.

The <i>EvtDeviceSelfManagedIoSuspend</i> callback function must do whatever is needed to stop the device's self-managed I/O operations.

For more information about when the framework calls this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/pnp-and-power-management-scenarios">PnP and Power Management Scenarios</a>.

For more information about drivers that provide this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-self-managed-i-o">Using Self-Managed I/O</a>.





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_cleanup">EvtDeviceSelfManagedIoCleanup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_flush">EvtDeviceSelfManagedIoFlush</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_init">EvtDeviceSelfManagedIoInit</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_restart">EvtDeviceSelfManagedIoRestart</a>
 

 

