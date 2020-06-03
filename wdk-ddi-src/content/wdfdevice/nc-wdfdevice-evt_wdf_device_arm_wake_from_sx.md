---
UID: NC:wdfdevice.EVT_WDF_DEVICE_ARM_WAKE_FROM_SX
title: EVT_WDF_DEVICE_ARM_WAKE_FROM_SX (wdfdevice.h)
description: A driver's EvtDeviceArmWakeFromSx event callback function arms (that is, enables) a device so that it can trigger a wake signal while in a low-power device state.
old-location: wdf\evtdevicearmwakefromsx.htm
tech.root: wdf
ms.assetid: 4954a278-8470-402c-a8ba-5e46ca56ddf7
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_ARM_WAKE_FROM_SX callback function"]
ms.keywords: DFDeviceObjectGeneralRef_7d373786-c5fd-41fe-a5b8-341fdb703984.xml, EVT_WDF_DEVICE_ARM_WAKE_FROM_SX, EVT_WDF_DEVICE_ARM_WAKE_FROM_SX callback, EvtDeviceArmWakeFromSx, EvtDeviceArmWakeFromSx callback function, kmdf.evtdevicearmwakefromsx, wdf.evtdevicearmwakefromsx, wdfdevice/EvtDeviceArmWakeFromSx
f1_keywords:
 - "wdfdevice/EvtDeviceArmWakeFromSx"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfdevice.h
api_name:
- EvtDeviceArmWakeFromSx
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_ARM_WAKE_FROM_SX callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceArmWakeFromSx</i> event callback function arms (that is, enables) a device so that it can trigger a wake signal while in a low-power device state. The wake signal causes the device to enter its working state (D0) and causes the system to enter its working state (S0). 


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns



If the <i>EvtDeviceArmWakeFromSx</i> callback function encounters no error, it must return STATUS_SUCCESS or another status value for which <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>.

If NT_SUCCESS(status) equals <b>FALSE</b>, the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_disarm_wake_from_sx">EvtDeviceDisarmWakeFromSx</a> callback function. (The framework does not report a device failure to the PnP manager.)




## -remarks



To register an <i>EvtDeviceArmWakeFromSx</i> callback function, a driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpowerpolicyeventcallbacks">WdfDeviceInitSetPowerPolicyEventCallbacks</a>. Drivers can register either an <i>EvtDeviceArmWakeFromSx</i> callback function or an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx_with_reason">EvtDeviceArmWakeFromSxWithReason</a> callback function, but not both.

This callback function handles device-specific operations that are needed to enable the device to detect an external event that triggers a wake signal on the bus. The bus driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nc-wdfpdo-evt_wdf_device_enable_wake_at_bus">EvtDeviceEnableWakeAtBus</a> callback function handles bus-specific operations, such as enabling the PCI bus's Power Management Event (PME) signal.

If a driver has registered an <i>EvtDeviceArmWakeFromSx</i> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx_with_reason">EvtDeviceArmWakeFromSxWithReason</a> callback function, the framework calls it while the device is still in the D0 device power state, before the bus driver lowers the device's power state but after the framework has sent a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/sending-a-wait-wake-irp">wait/wake IRP</a> on behalf of the driver. 

The process occurs in the following sequence:

<ol>
<li>
The framework determines that the system is about to enter a low-power system state.

</li>
<li>
The framework calls the driver's <i>EvtDeviceArmWakeFromSx</i> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx_with_reason">EvtDeviceArmWakeFromSxWithReason</a> callback function.

</li>
<li>
The framework asks the driver for the device's bus to lower the device's power.

</li>
</ol>
Immediately before a device enters a low-power state, the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_exit">EvtDeviceD0Exit</a> callback function.

For more information about when the framework calls this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/pnp-and-power-management-scenarios">PnP and Power Management Scenarios</a>.

You do not need to provide an <i>EvtDeviceArmWakeFromSx</i> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx_with_reason">EvtDeviceArmWakeFromSxWithReason</a> callback function if your device does not require special hardware operations that enable the device to trigger a wake signal.

For more information about this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-system-wake-up">Supporting System Wake-Up</a>.





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0">EvtDeviceArmWakeFromS0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx_with_reason">EvtDeviceArmWakeFromSxWithReason</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_disarm_wake_from_sx">EvtDeviceDisarmWakeFromSx</a>
 

 

