---
UID: NC:wdfdevice.EVT_WDF_DEVICE_DISARM_WAKE_FROM_S0
title: EVT_WDF_DEVICE_DISARM_WAKE_FROM_S0 (wdfdevice.h)
description: A driver's EvtDeviceDisarmWakeFromS0 event callback function disarms (that is, disables) a device's ability to trigger a wake signal while in a low-power device state, if the system remains in the system working state (S0).
old-location: wdf\evtdevicedisarmwakefroms0.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_DISARM_WAKE_FROM_S0 callback function"]
ms.keywords: DFDeviceObjectGeneralRef_75c64592-ec2c-471f-9f9d-484ab181e432.xml, EVT_WDF_DEVICE_DISARM_WAKE_FROM_S0, EVT_WDF_DEVICE_DISARM_WAKE_FROM_S0 callback, EvtDeviceDisarmWakeFromS0, EvtDeviceDisarmWakeFromS0 callback function, kmdf.evtdevicedisarmwakefroms0, wdf.evtdevicedisarmwakefroms0, wdfdevice/EvtDeviceDisarmWakeFromS0
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
req.irql: PASSIVE_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDF_DEVICE_DISARM_WAKE_FROM_S0
 - wdfdevice/EVT_WDF_DEVICE_DISARM_WAKE_FROM_S0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfdevice.h
api_name:
 - EVT_WDF_DEVICE_DISARM_WAKE_FROM_S0
---

# EVT_WDF_DEVICE_DISARM_WAKE_FROM_S0 callback function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceDisarmWakeFromS0</i> event callback function disarms (that is, disables) a device's ability to trigger a wake signal while in a low-power device state, if the system remains in the <a href="/windows-hardware/drivers/kernel/system-working-state-s0">system working state</a> (S0).

## -parameters

### -param Device 

[in]
A handle to a framework device object.

## -remarks

To register an <i>EvtDeviceDisarmWakeFromS0</i> callback function, a driver must call <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpowerpolicyeventcallbacks">WdfDeviceInitSetPowerPolicyEventCallbacks</a>. The driver must also set <b>IdleCanWakeFromS0</b> in the <b>IdleCaps</b> member of its <a href="/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_policy_idle_settings">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure.

If the driver has registered an <i>EvtDeviceDisarmWakeFromS0</i> callback function, the framework calls it after the bus driver determines that an event has awakened the device, and after the bus driver subsequently completes the <a href="/windows-hardware/drivers/kernel/sending-a-wait-wake-irp">wait/wake IRP</a>. Before calling the driver's <i>EvtDeviceDisarmWakeFromS0</i><i>EvtDeviceDisarmWakeFromS0</i> callback function, the framework calls the driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_entry">EvtDeviceD0Entry</a>, <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_enable">EvtInterruptEnable</a>, and <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_wake_from_s0_triggered">EvtDeviceWakeFromS0Triggered</a> callback functions.

The <i>EvtDeviceDisarmWakeFromS0</i> callback function must perform any hardware operations that are needed to disable the device's ability to trigger a wake signal after the power has been lowered.

For more information about when the framework calls this callback function, see <a href="/windows-hardware/drivers/wdf/pnp-and-power-management-scenarios">PnP and Power Management Scenarios</a>.

For more information about this callback function, see <a href="/windows-hardware/drivers/wdf/supporting-idle-power-down">Supporting Idle Power-Down</a>.

The <i>EvtDeviceDisarmWakeFromS0</i> callback function is called at IRQL = PASSIVE_LEVEL. You should not make this callback function <a href="/windows-hardware/drivers/wdf/creating-pageable-code-in-a-kmdf-driver">pageable</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0">EvtDeviceArmWakeFromS0</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_disarm_wake_from_sx">EvtDeviceDisarmWakeFromSx</a>

