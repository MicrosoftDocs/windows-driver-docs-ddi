---
UID: NC:wdfdevice.EVT_WDF_DEVICE_QUERY_REMOVE
title: EVT_WDF_DEVICE_QUERY_REMOVE (wdfdevice.h)
description: A driver's EvtDeviceQueryRemove event callback function determines whether a specified device can be stopped and removed.
old-location: wdf\evtdevicequeryremove.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_QUERY_REMOVE callback function"]
ms.keywords: DFDeviceObjectGeneralRef_e982c552-e635-4fa9-8d84-dc4d7c143925.xml, EVT_WDF_DEVICE_QUERY_REMOVE, EVT_WDF_DEVICE_QUERY_REMOVE callback, EvtDeviceQueryRemove, EvtDeviceQueryRemove callback function, kmdf.evtdevicequeryremove, wdf.evtdevicequeryremove, wdfdevice/EvtDeviceQueryRemove
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
 - EVT_WDF_DEVICE_QUERY_REMOVE
 - wdfdevice/EVT_WDF_DEVICE_QUERY_REMOVE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfdevice.h
api_name:
 - EvtDeviceQueryRemove
---

# EVT_WDF_DEVICE_QUERY_REMOVE callback function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceQueryRemove</i> event callback function determines whether a specified device can be stopped and removed.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

## -returns

If the driver determines that the device can be stopped and removed, the <i>EvtDeviceQueryRemove</i> callback function must return STATUS_SUCCESS or another status value for which <a href="/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. Do not return STATUS_NOT_SUPPORTED.

## -remarks

To register an <i>EvtDeviceQueryRemove</i> callback function, a driver must call <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

If the device and driver support idle power-down, the device might not be in its working state when the framework calls the driver's <i>EvtDeviceQueryRemove</i> callback function. The callback function can call <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicestopidle">WdfDeviceStopIdle</a> to force the device into its working (D0) state, and then the callback function can call <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceresumeidle">WdfDeviceResumeIdle</a> before it returns.

For more information about the <i>EvtDeviceQueryRemove</i> callback function, see <a href="/windows-hardware/drivers/wdf/handling-requests-to-stop-a-device">Handling Requests to Stop a Device</a>.

The framework does not synchronize the <i>EvtDeviceQueryRemove</i> callback function with other PnP and power management callback functions. For information about how the framework synchronizes the execution of a driver's event callback functions, see <a href="/windows-hardware/drivers/wdf/using-automatic-synchronization">Using Automatic Synchronization</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_query_stop">EvtDeviceQueryStop</a>
