---
UID: NC:wdfdevice.EVT_WDF_DEVICE_ARM_WAKE_FROM_S0
title: EVT_WDF_DEVICE_ARM_WAKE_FROM_S0 (wdfdevice.h)
description: A driver's EvtDeviceArmWakeFromS0 event callback function arms (that is, enables) a device so that it can trigger a wake signal while in a low-power device state, if the system remains in the system working state (S0).
old-location: wdf\evtdevicearmwakefroms0.htm
tech.root: wdf
ms.assetid: a3579239-517f-4df0-a632-31e1176c6552
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_c5a02b74-5290-4eaf-9994-eef5e71116fe.xml, EVT_WDF_DEVICE_ARM_WAKE_FROM_S0, EVT_WDF_DEVICE_ARM_WAKE_FROM_S0 callback, EvtDeviceArmWakeFromS0, EvtDeviceArmWakeFromS0 callback function, kmdf.evtdevicearmwakefroms0, wdf.evtdevicearmwakefroms0, wdfdevice/EvtDeviceArmWakeFromS0
ms.topic: callback
f1_keywords:
 - "wdfdevice/EvtDeviceArmWakeFromS0"
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
- EvtDeviceArmWakeFromS0
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_ARM_WAKE_FROM_S0 callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceArmWakeFromS0</i> event callback function arms (that is, enables) a device so that it can trigger a wake signal while in a low-power device state, if the system remains in the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/system-working-state-s0">system working state</a> (S0). 


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns



If the operation is successful, the <i>EvtDeviceArmWakeFromS0</i> callback function must return STATUS_SUCCESS or another status value for which <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>.

If NT_SUCCESS(status) equals <b>FALSE</b>, the framework does not call the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_disarm_wake_from_s0">EvtDeviceDisarmWakeFromS0</a> callback function. (The framework does not report a device failure to the PnP manager.) 




## -remarks



To register an <i>EvtDeviceArmWakeFromS0</i> callback function, a driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpowerpolicyeventcallbacks">WdfDeviceInitSetPowerPolicyEventCallbacks</a>. Additionally, the driver must set <b>IdleCanWakeFromS0</b> in the <b>IdleCaps</b> member of its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_policy_idle_settings">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure.

The <i>EvtDeviceArmWakeFromS0</i> callback function handles device-specific operations that are needed to enable the device to detect an external event that triggers a wake signal on the bus. The bus driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nc-wdfpdo-evt_wdf_device_enable_wake_at_bus">EvtDeviceEnableWakeAtBus</a> callback function handles bus-specific operations, such as enabling the PCI bus's Power Management Event (PME) signal.

If the driver has registered an <i>EvtDeviceArmWakeFromS0</i> callback function, the framework calls it while the device is still in the D0 device power state, before the bus driver lowers the device's power state but after the framework has sent a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/sending-a-wait-wake-irp">wait/wake IRP</a> on behalf of the driver. 

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
</ol>
Immediately before your device enters a low power state, the framework will call your driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_exit">EvtDeviceD0Exit</a> callback function.

For more information about when the framework calls this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/pnp-and-power-management-scenarios">PnP and Power Management Scenarios</a>.

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
</ul>
If your device supports USB "selective suspend" and if your driver sets <b>IdleUsbSelectiveSuspend</b> in the <b>IdleCaps</b> member of its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_policy_idle_settings">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure, the framework sends a "selective suspend" request to the USB bus driver when the device has been idle for a preset amount of time.

For more information about this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-idle-power-down">Supporting Idle Power-Down</a>.




#### Examples

To define an <i>EvtDeviceArmWakeFromS0</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceArmWakeFromS0</i> callback function that is named <i>MyDeviceArmWakeFromS0</i>, use the <b>EVT_WDF_DEVICE_ARM_WAKE_FROM_S0</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_ARM_WAKE_FROM_S0 MyDeviceArmWakeFromS0;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
_Use_decl_annotations_
NTSTATUS
 MyDeviceArmWakeFromS0 (
    WDFDEVICE  Device
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_ARM_WAKE_FROM_S0</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_ARM_WAKE_FROM_S0</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx">EvtDeviceArmWakeFromSx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_disarm_wake_from_s0">EvtDeviceDisarmWakeFromS0</a>
 

 

