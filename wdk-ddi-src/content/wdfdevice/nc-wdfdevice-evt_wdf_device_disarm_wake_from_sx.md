---
UID: NC:wdfdevice.EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX
title: EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX (wdfdevice.h)
description: A driver's EvtDeviceDisarmWakeFromSx event callback function disarms (that is, disables) a device's ability to trigger a wake signal while the device and system are in low-power states.
old-location: wdf\evtdevicedisarmwakefromsx.htm
tech.root: wdf
ms.assetid: 79bf7a42-5053-428a-a78b-dd8bdff93a69
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX callback function"]
ms.keywords: DFDeviceObjectGeneralRef_ea30bcf7-25ce-493a-a8e0-310657a98c60.xml, EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX, EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX callback, EvtDeviceDisarmWakeFromSx, EvtDeviceDisarmWakeFromSx callback function, kmdf.evtdevicedisarmwakefromsx, wdf.evtdevicedisarmwakefromsx, wdfdevice/EvtDeviceDisarmWakeFromSx
f1_keywords:
 - "wdfdevice/EvtDeviceDisarmWakeFromSx"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfdevice.h
api_name:
- EvtDeviceDisarmWakeFromSx
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceDisarmWakeFromSx</i> event callback function disarms (that is, disables) a device's ability to trigger a wake signal while the device and system are in low-power states.


## -parameters




### -param Device [in]

A handle to a framework device object.


## -remarks



To register an <i>EvtDeviceDisarmWakeFromSx</i> callback function, a driver must call  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpowerpolicyeventcallbacks">WdfDeviceInitSetPowerPolicyEventCallbacks</a>.

If the driver has registered this callback function, the framework calls it after the framework has determined that system power is being restored, and after the bus driver completes the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/sending-a-wait-wake-irp">wait/wake IRP</a>. Before calling the driver's <i>EvtDeviceDisarmWakeFromSx</i> callback function, the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_entry">EvtDeviceD0Entry</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_enable">EvtInterruptEnable</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_wake_from_sx_triggered">EvtDeviceWakeFromSxTriggered</a> callback functions.

The <i>EvtDeviceDisarmWakeFromSx</i> callback function must perform any hardware operations that are needed to disable the device's ability to trigger a wake signal after the power has been lowered.

For more information about when the framework calls this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/pnp-and-power-management-scenarios">PnP and Power Management Scenarios</a>.

For more information about this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-system-wake-up">Supporting System Wake-Up</a>.

The <i>EvtDeviceDisarmWakeFromSx</i> callback function is called at IRQL = PASSIVE_LEVEL. You should not make this callback function <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-pageable-code-in-a-kmdf-driver">pageable</a>.





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx">EvtDeviceArmWakeFromSx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_disarm_wake_from_s0">EvtDeviceDisarmWakeFromS0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_wake_from_sx_triggered">EvtDeviceWakeFromSxTriggered</a>
 

 

