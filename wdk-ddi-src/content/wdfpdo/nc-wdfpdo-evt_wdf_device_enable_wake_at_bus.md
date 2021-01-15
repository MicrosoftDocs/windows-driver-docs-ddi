---
UID: NC:wdfpdo.EVT_WDF_DEVICE_ENABLE_WAKE_AT_BUS
title: EVT_WDF_DEVICE_ENABLE_WAKE_AT_BUS (wdfpdo.h)
description: A bus driver's EvtDeviceEnableWakeAtBus event callback function performs bus-level operations that enable one of the bus's devices to trigger a wake-up signal on the bus.
old-location: wdf\evtdeviceenablewakeatbus.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_ENABLE_WAKE_AT_BUS callback function"]
ms.keywords: DFDeviceObjectFdoPdoRef_c418526b-2cf2-4193-b75c-f6af5d669433.xml, EVT_WDF_DEVICE_ENABLE_WAKE_AT_BUS, EVT_WDF_DEVICE_ENABLE_WAKE_AT_BUS callback, EvtDeviceEnableWakeAtBus, EvtDeviceEnableWakeAtBus callback function, kmdf.evtdeviceenablewakeatbus, wdf.evtdeviceenablewakeatbus, wdfpdo/EvtDeviceEnableWakeAtBus
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
 - EVT_WDF_DEVICE_ENABLE_WAKE_AT_BUS
 - wdfpdo/EVT_WDF_DEVICE_ENABLE_WAKE_AT_BUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfpdo.h
api_name:
 - EVT_WDF_DEVICE_ENABLE_WAKE_AT_BUS
---

# EVT_WDF_DEVICE_ENABLE_WAKE_AT_BUS callback function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

A bus driver's <i>EvtDeviceEnableWakeAtBus</i> event callback function performs bus-level operations that enable one of the bus's devices to trigger a wake-up signal on the bus.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

### -param PowerState 

[in]
A SYSTEM_POWER_STATE-typed enumerator that identifies the system power state that the system or device will wake from.

## -returns

If the <i>EvtDeviceEnableWakeAtBus</i> callback function encountered no errors, it must return STATUS_SUCCESS or another status value for which <a href="/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>.

If NT_SUCCESS(status) equals <b>FALSE</b>, the framework calls the driver's <a href="/windows-hardware/drivers/ddi/wdfpdo/nc-wdfpdo-evt_wdf_device_disable_wake_at_bus">EvtDeviceDisableWakeAtBus</a> callback function.

 

For more information about this callback function's return values, see <a href="/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.

## -remarks

For more information about this callback function, see <a href="/windows-hardware/drivers/wdf/supporting-system-wake-up">Supporting System Wake-Up</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfpdo/nc-wdfpdo-evt_wdf_device_disable_wake_at_bus">EvtDeviceDisableWakeAtBus</a>

