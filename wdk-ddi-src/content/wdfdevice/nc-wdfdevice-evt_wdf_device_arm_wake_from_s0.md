---
UID: NC:wdfdevice.EVT_WDF_DEVICE_ARM_WAKE_FROM_S0
title: EVT_WDF_DEVICE_ARM_WAKE_FROM_S0
author: windows-driver-content
description: A driver's EvtDeviceArmWakeFromS0 event callback function arms (that is, enables) a device so that it can trigger a wake signal while in a low-power device state, if the system remains in the system working state (S0).
old-location: wdf\evtdevicearmwakefroms0.htm
old-project: wdf
ms.assetid: a3579239-517f-4df0-a632-31e1176c6552
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtdevicearmwakefroms0, EvtDeviceArmWakeFromS0 callback function, EvtDeviceArmWakeFromS0, EVT_WDF_DEVICE_ARM_WAKE_FROM_S0, EVT_WDF_DEVICE_ARM_WAKE_FROM_S0, wdfdevice/EvtDeviceArmWakeFromS0, DFDeviceObjectGeneralRef_c5a02b74-5290-4eaf-9994-eef5e71116fe.xml, kmdf.evtdevicearmwakefroms0
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
-	EvtDeviceArmWakeFromS0
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# EVT_WDF_DEVICE_ARM_WAKE_FROM_S0 callback


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtDeviceArmWakeFromS0</i> event callback function arms (that is, enables) a device so that it can trigger a wake signal while in a low-power device state, if the system remains in the <a href="https://msdn.microsoft.com/93ab0943-a4cc-4ef0-a250-1c63b2c915d5">system working state</a> (S0). 


## -prototype


````
EVT_WDF_DEVICE_ARM_WAKE_FROM_S0 EvtDeviceArmWakeFromS0;

NTSTATUS EvtDeviceArmWakeFromS0(
  _In_ WDFDEVICE Device
)
{ ... }
````


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns


If the operation is successful, the <i>EvtDeviceArmWakeFromS0</i> callback function must return STATUS_SUCCESS or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>.

If NT_SUCCESS(status) equals <b>FALSE</b>, the framework calls the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_disarm_wake_from_s0.md">EvtDeviceDisarmWakeFromS0</a> callback function. (The framework does not report a device failure to the PnP manager.) 



## -remarks


To register an <i>EvtDeviceArmWakeFromS0</i> callback function, a driver must call <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpowerpolicyeventcallbacks.md">WdfDeviceInitSetPowerPolicyEventCallbacks</a>. Additionally, the driver must set <b>IdleCanWakeFromS0</b> in the <b>IdleCaps</b> member of its <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_policy_idle_settings.md">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure.

The <i>EvtDeviceArmWakeFromS0</i> callback function handles device-specific operations that are needed to enable the device to detect an external event that triggers a wake signal on the bus. The bus driver's <a href="..\wdfpdo\nc-wdfpdo-evt_wdf_device_enable_wake_at_bus.md">EvtDeviceEnableWakeAtBus</a> callback function handles bus-specific operations, such as enabling the PCI bus's Power Management Event (PME) signal.

If the driver has registered an <i>EvtDeviceArmWakeFromS0</i> callback function, the framework calls it while the device is still in the D0 device power state, before the bus driver lowers the device's power state but after the framework has sent a <a href="https://msdn.microsoft.com/ed582644-af51-4841-be59-6a3deb6d9de5">wait/wake IRP</a> on behalf of the driver. 

The process occurs in the following sequence:
<ol>
<li>
The framework determines that the device has been idle for a preset amount of time.

</li>
<li>
The framework calls the driver's <i>EvtDeviceArmWakeFromS0</i> callback function.

</li>
<li>
The framework requests the driver for the device's bus to lower the device's power.

</li>
</ol>Immediately before your device enters a low power state, the framework will call your driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_exit.md">EvtDeviceD0Exit</a> callback function.

For more information about when the framework calls this callback function, see <a href="https://msdn.microsoft.com/9175ce95-196d-44bd-b31c-88386fa0d3d3">PnP and Power Management Scenarios</a>.

You do not need to provide an <i>EvtDeviceArmWakeFromS0</i> callback function if your device:
<ul>
<li>
Is a USB device that supports "selective suspend."

</li>
<li>
Cannot be powered down while the system remains fully powered.

</li>
<li>
Does not require special hardware operations that enable the device to trigger a wake signal.

</li>
</ul>If your device supports USB "selective suspend" and if your driver sets <b>IdleUsbSelectiveSuspend</b> in the <b>IdleCaps</b> member of its <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_policy_idle_settings.md">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure, the framework sends a "selective suspend" request to the USB bus driver when the device has been idle for a preset amount of time.

For more information about this callback function, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-idle-power-down">Supporting Idle Power-Down</a>.





## -see-also

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_disarm_wake_from_s0.md">EvtDeviceDisarmWakeFromS0</a>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md">EvtDeviceArmWakeFromSx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_ARM_WAKE_FROM_S0 callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

