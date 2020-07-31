---
UID: NC:wdfdevice.EVT_WDF_DEVICE_SELF_MANAGED_IO_FLUSH
title: EVT_WDF_DEVICE_SELF_MANAGED_IO_FLUSH (wdfdevice.h)
description: A driver's EvtDeviceSelfManagedIoFlush event callback function handles flush activity for the device's self-managed I/O operations.
old-location: wdf\evtdeviceselfmanagedioflush.htm
tech.root: wdf
ms.assetid: ad4ace83-c6c1-4b5f-b998-f46f3e721165
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_SELF_MANAGED_IO_FLUSH callback function"]
ms.keywords: DFDeviceObjectGeneralRef_d464c7ae-10fa-4838-b152-9bbaeaac76de.xml, EVT_WDF_DEVICE_SELF_MANAGED_IO_FLUSH, EVT_WDF_DEVICE_SELF_MANAGED_IO_FLUSH callback, EvtDeviceSelfManagedIoFlush, EvtDeviceSelfManagedIoFlush callback function, kmdf.evtdeviceselfmanagedioflush, wdf.evtdeviceselfmanagedioflush, wdfdevice/EvtDeviceSelfManagedIoFlush
f1_keywords:
 - "wdfdevice/EvtDeviceSelfManagedIoFlush"
 - "EvtDeviceSelfManagedIoFlush"
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
- EvtDeviceSelfManagedIoFlush
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_SELF_MANAGED_IO_FLUSH callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceSelfManagedIoFlush</i> event callback function handles flush activity for the device's self-managed I/O operations.


## -parameters




### -param Device [in]

A handle to a framework device object.


## -remarks



To register an <i>EvtDeviceSelfManagedIoFlush</i> callback function, a driver must call  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

If the driver has registered an <i>EvtDeviceSelfManagedIoFlush</i> callback function, the framework calls it after the device has been removed. The driver should flush (that is, remove) I/O requests that are associated with the device's self-managed I/O operations.

For more information about when the framework calls this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/pnp-and-power-management-scenarios">PnP and Power Management Scenarios</a>.

For more information about drivers that provide this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-self-managed-i-o">Using Self-Managed I/O</a>.

You must declare the function by using the EVT_WDF_DEVICE_SELF_MANAGED_IO_FLUSH type. For more information, see the following Example section.





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_cleanup">EvtDeviceSelfManagedIoCleanup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_init">EvtDeviceSelfManagedIoInit</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_restart">EvtDeviceSelfManagedIoRestart</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_suspend">EvtDeviceSelfManagedIoSuspend</a>
 

 

