---
UID: NC:wdfdevice.EVT_WDF_DEVICE_SELF_MANAGED_IO_INIT
title: EVT_WDF_DEVICE_SELF_MANAGED_IO_INIT
author: windows-driver-content
description: A driver's EvtDeviceSelfManagedIoInit event callback function initializes and starts the device's self-managed I/O operations.
old-location: wdf\evtdeviceselfmanagedioinit.htm
old-project: wdf
ms.assetid: 9dbc66db-ea94-4e6a-9618-00999a9dd641
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtdeviceselfmanagedioinit, EvtDeviceSelfManagedIoInit callback function, EvtDeviceSelfManagedIoInit, EVT_WDF_DEVICE_SELF_MANAGED_IO_INIT, EVT_WDF_DEVICE_SELF_MANAGED_IO_INIT, wdfdevice/EvtDeviceSelfManagedIoInit, DFDeviceObjectGeneralRef_7c67b851-b6d0-450d-bdc9-2a32aa384a36.xml, kmdf.evtdeviceselfmanagedioinit
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
-	EvtDeviceSelfManagedIoInit
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# EVT_WDF_DEVICE_SELF_MANAGED_IO_INIT callback


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtDeviceSelfManagedIoInit</i> event callback function initializes and starts the device's self-managed I/O operations.


## -prototype


````
EVT_WDF_DEVICE_SELF_MANAGED_IO_INIT EvtDeviceSelfManagedIoInit;

NTSTATUS EvtDeviceSelfManagedIoInit(
  _In_ WDFDEVICE Device
)
{ ... }
````


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns


If the <i>EvtDeviceSelfManagedIoInit</i> callback function encounters no errors, it must return STATUS_SUCCESS, or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise, it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. If NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>, the framework does not start the device.

If NT_SUCCESS(status) equals <b>FALSE</b>, the framework calls the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_flush.md">EvtDeviceSelfManagedIoFlush</a> and <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_cleanup.md">EvtDeviceSelfManagedIoCleanup</a> callback functions.

For more information about this callback function's return values, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.



## -remarks


To register an <i>EvtDeviceSelfManagedIoInit</i> callback function, a driver must call <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks.md">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

If the driver has registered an <i>EvtDeviceSelfManagedIoInit</i> callback function, the framework calls it once for each device, after the framework has called the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_entry.md">EvtDeviceD0Entry</a> callback function for the first time. The framework does not call the <i>EvtDeviceSelfManagedIoInit</i> callback function again for that device, unless the device is removed and reconnected, or the drivers are reloaded.

The <i>EvtDeviceSelfManagedIoInit</i> callback function must initialize and start the self-managed I/O operations that the driver will handle for the device.

For more information about when the framework calls this callback function, see <a href="https://msdn.microsoft.com/9175ce95-196d-44bd-b31c-88386fa0d3d3">PnP and Power Management Scenarios</a>.

For more information about drivers that provide this callback function, see <a href="https://msdn.microsoft.com/539b3618-44bb-41fd-a9f2-ed6a377c94e2">Using Self-Managed I/O</a>.



## -see-also

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_cleanup.md">EvtDeviceSelfManagedIoCleanup</a>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_suspend.md">EvtDeviceSelfManagedIoSuspend</a>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_flush.md">EvtDeviceSelfManagedIoFlush</a>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_restart.md">EvtDeviceSelfManagedIoRestart</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_SELF_MANAGED_IO_INIT callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

