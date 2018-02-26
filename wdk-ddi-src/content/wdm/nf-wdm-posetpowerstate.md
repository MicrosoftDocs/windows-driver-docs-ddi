---
UID: NF:wdm.PoSetPowerState
title: PoSetPowerState function
author: windows-driver-content
description: The PoSetPowerState routine notifies the system of a change in the device power state for a device.
old-location: kernel\posetpowerstate.htm
old-project: kernel
ms.assetid: 9fff319e-0428-4185-a792-d3842ab9feb8
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , P, PoSetPowerState, PoSetPowerState routine [Kernel-Mode Driver Architecture], S, a, e, kernel.posetpowerstate, o, portn_b6d6559d-e4c7-4fa8-b0f2-556b840391f9.xml, r, t, w, wdm/PoSetPowerState"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	PoSetPowerState
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# PoSetPowerState function


## -description


The <b>PoSetPowerState</b> routine notifies the system of a change in the <a href="https://msdn.microsoft.com/2229f34c-9b88-4e3e-802e-f7be2c7ef168">device power state</a> for a device.


## -syntax


````
POWER_STATE PoSetPowerState(
  _In_ PDEVICE_OBJECT   DeviceObject,
  _In_ POWER_STATE_TYPE Type,
  _In_ POWER_STATE      State
);
````


## -parameters




### -param DeviceObject [in]

A pointer to the target <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>.


### -param Type [in]

Indicates a <a href="..\wdm\ne-wdm-_power_state_type.md">POWER_STATE_TYPE</a> value. Drivers must specify <b>DevicePowerState</b>.


### -param State [in]

Specifies the power state to be set. Drivers must specify a <a href="..\wudfddi\ne-wudfddi-_device_power_state.md">DEVICE_POWER_STATE</a> value.


## -returns



On Windows 2000 and later versions of the operating system, <b>PoSetPowerState</b> returns the previous power state. On Windows 98/Me, <b>PoSetPowerState</b> returns the state passed in <i>State</i>.




## -remarks



<b>PoSetPowerState</b> notifies the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559829">power manager</a> of the new power state for a device. Each driver in a device stack (filter, function, and bus drivers) must call <b>PoSetPowerState</b> to inform the power manager of a change in the power state of its corresponding device object. For example:

<ul>
<li>
A driver calls this routine after receiving a device set-power request and before calling <a href="..\wdm\nf-wdm-postartnextpowerirp.md">PoStartNextPowerIrp</a>. When handling a PnP <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a> request, the driver should call <b>PoSetPowerState</b> to notify the power manager that the device is in the D0 state.

</li>
<li>
If the device is powering down, the driver must call <b>PoSetPowerState</b> before leaving the D0 state. In addition, the driver must be able to process client requests before <b>PoSetPowerState</b> returns.

</li>
<li>
If the device is powering up, the driver must call <b>PoSetPowerState</b> after the device is successfully put into the D0 state.

</li>
</ul>
For more information about powering a device up and down, see <a href="https://msdn.microsoft.com/b4a19995-7933-41f7-b951-15ce0e4627da">Handling IRP_MN_SET_POWER for Device Power States</a>.

Callers of <b>PoSetPowerState</b> must be running at IRQL &lt;= APC_LEVEL except when setting state to D0. When setting state to D0, callers can be running at IRQL &lt;= DISPATCH_LEVEL.




## -see-also

<a href="..\wdm\nf-wdm-postartnextpowerirp.md">PoStartNextPowerIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PoSetPowerState routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

