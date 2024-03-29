---
UID: NC:wdfpdo.EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS
title: EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS (wdfpdo.h)
description: A bus driver's EvtDeviceDisableWakeAtBus event callback function performs bus-level operations that disable the ability of one of the bus's devices to trigger a wake-up signal on the bus.
old-location: wdf\evtdevicedisablewakeatbus.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS callback function"]
ms.keywords: DFDeviceObjectFdoPdoRef_3f6a4a69-a6aa-48a5-9a6a-fd64c569edca.xml, EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS, EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS callback, EvtDeviceDisableWakeAtBus, EvtDeviceDisableWakeAtBus callback function, kmdf.evtdevicedisablewakeatbus, wdf.evtdevicedisablewakeatbus, wdfpdo/EvtDeviceDisableWakeAtBus
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
 - EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS
 - wdfpdo/EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfpdo.h
api_name:
 - EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS
---

# EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS callback function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

A bus driver's <i>EvtDeviceDisableWakeAtBus</i> event callback function performs bus-level operations that disable the ability of one of the bus's devices to trigger a wake-up signal on the bus.

## -parameters

### -param Device [in]


A handle to a framework device object.

## -remarks

To register this callback function, the bus driver must call <a href="/windows-hardware/drivers/ddi/wdfpdo/nf-wdfpdo-wdfpdoinitseteventcallbacks">WdfPdoInitSetEventCallbacks</a>.

For more information about this callback function, see <a href="/windows-hardware/drivers/wdf/supporting-system-wake-up">Supporting System Wake-Up</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfpdo/nf-wdfpdo-wdfpdoinitseteventcallbacks">WdfPdoInitSetEventCallbacks</a>

<a href="/windows-hardware/drivers/ddi/wdfpdo/nc-wdfpdo-evt_wdf_device_enable_wake_at_bus">EvtDeviceEnableWakeAtBus</a>

