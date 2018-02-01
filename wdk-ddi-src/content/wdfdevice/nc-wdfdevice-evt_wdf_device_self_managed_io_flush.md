---
UID: NC:wdfdevice.EVT_WDF_DEVICE_SELF_MANAGED_IO_FLUSH
title: EVT_WDF_DEVICE_SELF_MANAGED_IO_FLUSH
author: windows-driver-content
description: A driver's EvtDeviceSelfManagedIoFlush event callback function handles flush activity for the device's self-managed I/O operations.
old-location: wdf\evtdeviceselfmanagedioflush.htm
old-project: wdf
ms.assetid: ad4ace83-c6c1-4b5f-b998-f46f3e721165
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtdeviceselfmanagedioflush, EvtDeviceSelfManagedIoFlush callback function, EvtDeviceSelfManagedIoFlush, EVT_WDF_DEVICE_SELF_MANAGED_IO_FLUSH, EVT_WDF_DEVICE_SELF_MANAGED_IO_FLUSH, wdfdevice/EvtDeviceSelfManagedIoFlush, DFDeviceObjectGeneralRef_d464c7ae-10fa-4838-b152-9bbaeaac76de.xml, kmdf.evtdeviceselfmanagedioflush
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
-	EvtDeviceSelfManagedIoFlush
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# EVT_WDF_DEVICE_SELF_MANAGED_IO_FLUSH callback


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtDeviceSelfManagedIoFlush</i> event callback function handles flush activity for the device's self-managed I/O operations.


## -prototype


````
EVT_WDF_DEVICE_SELF_MANAGED_IO_FLUSH EvtDeviceSelfManagedIoFlush;

VOID EvtDeviceSelfManagedIoFlush(
  _In_ WDFDEVICE Device
)
{ ... }
````


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns


None



## -remarks


To register an <i>EvtDeviceSelfManagedIoFlush</i> callback function, a driver must call  <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks.md">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

If the driver has registered an <i>EvtDeviceSelfManagedIoFlush</i> callback function, the framework calls it after the device has been removed. The driver should flush (that is, remove) I/O requests that are associated with the device's self-managed I/O operations.

For more information about when the framework calls this callback function, see <a href="https://msdn.microsoft.com/9175ce95-196d-44bd-b31c-88386fa0d3d3">PnP and Power Management Scenarios</a>.

For more information about drivers that provide this callback function, see <a href="https://msdn.microsoft.com/539b3618-44bb-41fd-a9f2-ed6a377c94e2">Using Self-Managed I/O</a>.

You must declare the function by using the EVT_WDF_DEVICE_SELF_MANAGED_IO_FLUSH type. For more information, see the following Example section.



## -see-also

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_init.md">EvtDeviceSelfManagedIoInit</a>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_suspend.md">EvtDeviceSelfManagedIoSuspend</a>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_cleanup.md">EvtDeviceSelfManagedIoCleanup</a>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_restart.md">EvtDeviceSelfManagedIoRestart</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_SELF_MANAGED_IO_FLUSH callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

