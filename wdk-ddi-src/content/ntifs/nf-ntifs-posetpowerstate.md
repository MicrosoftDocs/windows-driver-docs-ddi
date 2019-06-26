---
UID: NF:ntifs.PoSetPowerState
title: PoSetPowerState function (ntifs.h)
description: The PoSetPowerState routine notifies the system of a change in the device power state for a device.
old-location: kernel\posetpowerstate.htm
tech.root: kernel
ms.assetid: 9fff319e-0428-4185-a792-d3842ab9feb8
ms.date: 04/30/2018
ms.keywords: PoSetPowerState, PoSetPowerState routine [Kernel-Mode Driver Architecture], kernel.posetpowerstate, portn_b6d6559d-e4c7-4fa8-b0f2-556b840391f9.xml, wdm/PoSetPowerState
ms.topic: function
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- PoSetPowerState
product:
- Windows
targetos: Windows
req.typenames: 
---

# PoSetPowerState function


## -description


The <b>PoSetPowerState</b> routine notifies the system of a change in the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/device-power-states">device power state</a> for a device.


## -parameters




### -param DeviceObject [in]

A pointer to the target <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>.


### -param Type [in]

Indicates a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_power_state_type">POWER_STATE_TYPE</a> value. Drivers must specify <b>DevicePowerState</b>.


### -param State [in]

Specifies the power state to be set. Drivers must specify a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/ne-wudfddi-_device_power_state">DEVICE_POWER_STATE</a> value.


## -returns



On Windows 2000 and later versions of the operating system, <b>PoSetPowerState</b> returns the previous power state. On Windows 98/Me, <b>PoSetPowerState</b> returns the state passed in <i>State</i>.




## -remarks



<b>PoSetPowerState</b> notifies the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/power-manager">power manager</a> of the new power state for a device. Each driver in a device stack (filter, function, and bus drivers) must call <b>PoSetPowerState</b> to inform the power manager of a change in the power state of its corresponding device object. For example:

<ul>
<li>
A driver calls this routine after receiving a device set-power request and before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-postartnextpowerirp">PoStartNextPowerIrp</a>. When handling a PnP <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-start-device">IRP_MN_START_DEVICE</a> request, the driver should call <b>PoSetPowerState</b> to notify the power manager that the device is in the D0 state.

</li>
<li>
If the device is powering down, the driver must call <b>PoSetPowerState</b> before leaving the D0 state. In addition, the driver must be able to process client requests before <b>PoSetPowerState</b> returns.

</li>
<li>
If the device is powering up, the driver must call <b>PoSetPowerState</b> after the device is successfully put into the D0 state.

</li>
</ul>
For more information about powering a device up and down, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/handling-irp-mn-set-power-for-device-power-states">Handling IRP_MN_SET_POWER for Device Power States</a>.

Callers of <b>PoSetPowerState</b> must be running at IRQL <= APC_LEVEL except when setting state to D0. When setting state to D0, callers can be running at IRQL <= DISPATCH_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-start-device">IRP_MN_START_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-postartnextpowerirp">PoStartNextPowerIrp</a>
 

 

