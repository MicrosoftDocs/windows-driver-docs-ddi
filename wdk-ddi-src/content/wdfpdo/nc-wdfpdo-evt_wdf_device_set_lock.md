---
UID: NC:wdfpdo.EVT_WDF_DEVICE_SET_LOCK
title: EVT_WDF_DEVICE_SET_LOCK (wdfpdo.h)
description: A driver's EvtDeviceSetLock event callback function locks the specified device so that it cannot be ejected, or unlocks the device so that it can be ejected.
old-location: wdf\evtdevicesetlock.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_SET_LOCK callback function"]
ms.keywords: DFDeviceObjectFdoPdoRef_932fbb3b-df8b-49ca-9b86-3d98b6fdd39f.xml, EVT_WDF_DEVICE_SET_LOCK, EVT_WDF_DEVICE_SET_LOCK callback, EvtDeviceSetLock, EvtDeviceSetLock callback function, kmdf.evtdevicesetlock, wdf.evtdevicesetlock, wdfpdo/EvtDeviceSetLock
req.header: wdfpdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
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
 - EVT_WDF_DEVICE_SET_LOCK
 - wdfpdo/EVT_WDF_DEVICE_SET_LOCK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfpdo.h
api_name:
 - EVT_WDF_DEVICE_SET_LOCK
---

# EVT_WDF_DEVICE_SET_LOCK callback function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtDeviceSetLock</i> event callback function locks the specified device so that it cannot be ejected, or unlocks the device so that it can be ejected.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

### -param IsLocked 

[in]
A Boolean value that indicates whether the driver must lock or unlock the device. If <b>TRUE</b>, the driver must lock the device so that it cannot be ejected. If <b>FALSE</b>, the driver must unlock the device so that it can be ejected.

## -returns

If the driver successfully locks or unlocks the device, it must return STATUS_SUCCESS. Otherwise it must return an NTSTATUS value that <a href="/windows-hardware/drivers/kernel/ntstatus-values">NT_SUCCESS</a> evaluates as <b>FALSE</b>.

 

For more information about this callback function's return values, see <a href="/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.

## -remarks

Framework-based bus drivers can provide an <i>EvtDeviceSetLock</i> callback function. To register this callback function, bus drivers call <a href="/windows-hardware/drivers/ddi/wdfpdo/nf-wdfpdo-wdfpdoinitseteventcallbacks">WdfPdoInitSetEventCallbacks</a>.

The framework calls the driver's <i>EvtDeviceSetLock</i> callback function when the PnP manager requests the bus driver to lock or unlock one of its enumerated child devices. 

Not implementing an <i>EvtDeviceSetLock</i> callback function for a device is equivalent to returning an NTSTATUS value that evaluates as <b>FALSE</b>.

For more information about return values, see <a href="/windows-hardware/drivers/wdf/supporting-ejectable-devices">Supporting Ejectable Devices</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfpdo/nc-wdfpdo-evt_wdf_device_eject">EvtDeviceEject</a>

