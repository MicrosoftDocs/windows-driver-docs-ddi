---
UID: NC:wdfdevice.EVT_WDF_DEVICE_WAKE_FROM_S0_TRIGGERED
title: EVT_WDF_DEVICE_WAKE_FROM_S0_TRIGGERED (wdfdevice.h)
description: A driver's EvtDeviceWakeFromS0Triggered event callback function informs the driver that its device, which had previously entered a low-power device state while the system power state remained at S0, might have triggered a wake signal.
old-location: wdf\evtdevicewakefroms0triggered.htm
tech.root: wdf
ms.assetid: 4395b1c1-ae67-42fc-b6c7-b1bdbf090c5b
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_WAKE_FROM_S0_TRIGGERED callback function"]
ms.keywords: DFDeviceObjectGeneralRef_d5f1f5da-3fa1-4d26-ab15-587b66c7d5c2.xml, EVT_WDF_DEVICE_WAKE_FROM_S0_TRIGGERED, EVT_WDF_DEVICE_WAKE_FROM_S0_TRIGGERED callback, EvtDeviceWakeFromS0Triggered, EvtDeviceWakeFromS0Triggered callback function, kmdf.evtdevicewakefroms0triggered, wdf.evtdevicewakefroms0triggered, wdfdevice/EvtDeviceWakeFromS0Triggered
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
 - EVT_WDF_DEVICE_WAKE_FROM_S0_TRIGGERED
 - wdfdevice/EVT_WDF_DEVICE_WAKE_FROM_S0_TRIGGERED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfdevice.h
api_name:
 - EvtDeviceWakeFromS0Triggered
---

# EVT_WDF_DEVICE_WAKE_FROM_S0_TRIGGERED callback function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceWakeFromS0Triggered</i> event callback function informs the driver that its device, which had previously entered a low-power device state while the system power state remained at S0, might have triggered a wake signal.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

## -remarks

To register an <i>EvtDeviceWakeFromS0Triggered</i> callback function, a driver must call <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpowerpolicyeventcallbacks">WdfDeviceInitSetPowerPolicyEventCallbacks</a>.

If the driver has registered  this callback, the framework calls it after calling the driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_entry">EvtDeviceD0Entry</a> callback function and before calling the driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_disarm_wake_from_s0">EvtDeviceDisarmWakeFromS0</a> callback function.

System hardware (BIOSes, motherboards, bus adapters) can sometimes drop a wake signal before the bus driver detects it, even though the signal wakes up the system. In such cases, the driver's <i>EvtDeviceWakeFromS0Triggered</i> callback function will not be called even though the driver's device triggered a wake signal.

Some buses combine wake signals from several children. If your device is connected to one of these buses, the callback function might have to determine if the current device triggered the wake-up signal. If your device provides a hardware latch that saves the device's triggered state, it is best to check that state in the driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_disarm_wake_from_s0">EvtDeviceDisarmWakeFromS0</a> callback function, because that callback is always called after the device wakes up, even if the wake signal was dropped.

For more information about this callback function, see <a href="/windows-hardware/drivers/wdf/supporting-idle-power-down">Supporting Idle Power-Down</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0">EvtDeviceArmWakeFromS0</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_disarm_wake_from_s0">EvtDeviceDisarmWakeFromS0</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_wake_from_sx_triggered">EvtDeviceWakeFromSxTriggered</a>