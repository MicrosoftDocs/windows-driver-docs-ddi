---
UID: NC:wdfdevice.EVT_WDF_DEVICE_QUERY_REMOVE
title: EVT_WDF_DEVICE_QUERY_REMOVE
author: windows-driver-content
description: A driver's EvtDeviceQueryRemove event callback function determines whether a specified device can be stopped and removed.
old-location: wdf\evtdevicequeryremove.htm
old-project: wdf
ms.assetid: 59e6a8bc-e2f9-4d26-92b0-8f8944e1aa88
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtdevicequeryremove, EvtDeviceQueryRemove callback function, EvtDeviceQueryRemove, EVT_WDF_DEVICE_QUERY_REMOVE, EVT_WDF_DEVICE_QUERY_REMOVE, wdfdevice/EvtDeviceQueryRemove, DFDeviceObjectGeneralRef_e982c552-e635-4fa9-8d84-dc4d7c143925.xml, kmdf.evtdevicequeryremove
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
-	EvtDeviceQueryRemove
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# EVT_WDF_DEVICE_QUERY_REMOVE callback


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtDeviceQueryRemove</i> event callback function determines whether a specified device can be stopped and removed.


## -prototype


````
EVT_WDF_DEVICE_QUERY_REMOVE EvtDeviceQueryRemove;

NTSTATUS EvtDeviceQueryRemove(
  _In_ WDFDEVICE Device
)
{ ... }
````


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns


If the driver determines that the device can be stopped and removed, the <i>EvtDeviceQueryRemove</i> callback function must return STATUS_SUCCESS or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. Do not return STATUS_NOT_SUPPORTED.



## -remarks


To register an <i>EvtDeviceQueryRemove</i> callback function, a driver must call <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks.md">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

If the device and driver support idle power-down, the device might not be in its working state when the framework calls the driver's <i>EvtDeviceQueryRemove</i> callback function. The callback function can call <a href="..\wdfdevice\nf-wdfdevice-wdfdevicestopidle.md">WdfDeviceStopIdle</a> to force the device into its working (D0) state, and then the callback function can call <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceresumeidle.md">WdfDeviceResumeIdle</a> before it returns.

For more information about the <i>EvtDeviceQueryRemove</i> callback function, see <a href="https://msdn.microsoft.com/4c8f37b3-7961-4c78-a88b-3eec58155e66">Handling Requests to Stop a Device</a>.

The framework does not synchronize the <i>EvtDeviceQueryRemove</i> callback function with other PnP and power management callback functions. For information about how the framework synchronizes the execution of a driver's event callback functions, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-automatic-synchronization">Using Automatic Synchronization</a>. 



## -see-also

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_query_stop.md">EvtDeviceQueryStop</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_QUERY_REMOVE callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

