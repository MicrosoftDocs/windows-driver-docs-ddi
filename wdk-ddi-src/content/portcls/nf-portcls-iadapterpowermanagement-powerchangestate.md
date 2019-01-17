---
UID: NF:portcls.IAdapterPowerManagement.PowerChangeState
title: IAdapterPowerManagement::PowerChangeState
description: The PowerChangeState method requests that the device change to a new power state.
old-location: audio\iadapterpowermanagement_powerchangestate.htm
tech.root: audio
ms.assetid: b3e0fca7-d5ab-4d52-9702-dae83c540a71
ms.date: 05/08/2018
ms.keywords: IAdapterPowerManagement interface [Audio Devices],PowerChangeState method, IAdapterPowerManagement.PowerChangeState, IAdapterPowerManagement::PowerChangeState, PowerChangeState, PowerChangeState method [Audio Devices], PowerChangeState method [Audio Devices],IAdapterPowerManagement interface, audio.iadapterpowermanagement_powerchangestate, audmp-routines_7898e689-94c5-4577-80d8-a88676cd44dc.xml, portcls/IAdapterPowerManagement::PowerChangeState
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IAdapterPowerManagement.PowerChangeState
product:
- Windows
targetos: Windows
req.typenames: 
---

# IAdapterPowerManagement::PowerChangeState


## -description


The <code>PowerChangeState</code> method requests that the device change to a new power state.


## -parameters




### -param NewState [in]

Specifies the new power state being requested for the device. This parameter is a union of type POWER_STATE. The new power state (<i>NewState</i>.<b>DeviceState</b>) can be one of the DEVICE_POWER_STATE enumeration values shown in the following table.

<table>
<tr>
<th>Power State</th>
<th>Meaning</th>
</tr>
<tr>
<td>
PowerDeviceD0

</td>
<td>
Full power state (D0). This code may be a function of the current power state. Save the new state. This local value is used to determine when to cache property accesses and when to permit the driver from accessing the hardware.

</td>
</tr>
<tr>
<td>
PowerDeviceD1

</td>
<td>
The sleep state having the lowest latency with respect to the latency time required to return to D0

</td>
</tr>
<tr>
<td>
PowerDeviceD2

</td>
<td>
A medium latency sleep state. In this state, the device driver cannot assume that it can touch the hardware, so any accesses need to be cached and the hardware restored upon entering D0.

</td>
</tr>
<tr>
<td>
PowerDeviceD3

</td>
<td>
A full hibernation state and is the longest latency sleep state. The driver cannot access the hardware in this state and must cache any hardware accesses and restore the hardware upon returning to D0 or D1

</td>
</tr>
</table>
 


## -returns



None




## -remarks



PortCls calls the <code>PowerChangeState</code> method in response to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a> power IRP. This call must not fail. PortCls and the system use the <code>PowerChangeState</code> call to place the device in the desired power state. When the system attempts to suspend or resume an active audio stream, the driver must be capable of saving or restoring its device context appropriately.

To assist the driver, PortCls will pause any active audio streams prior to calling this method to place the device in a sleep state. After calling this method, PortCls will unpause active audio streams, to wake the device up. Miniports can opt for additional notification by utilizing the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536947">IPowerNotify</a> interface.

The miniport driver must perform the requested change to the device's power state before it returns from the <code>PowerChangeState</code> call. If the miniport driver needs to save or restore any device state before a power-state change, the miniport driver should support the <b>IPowerNotify</b> interface, which allows it to receive advance warning of any such change. Before returning from a successful <code>PowerChangeState</code> call, the miniport driver should cache the new power state.

While the miniport driver is in one of the sleep states (any state other than PowerDeviceD0), it must avoid writing to the hardware. The miniport driver must cache any hardware accesses that need to be deferred until the device powers up again. If the power state is changing from one of the sleep states to PowerDeviceD0, the miniport driver should perform any deferred hardware accesses after it has powered up the device. If the power state is changing from PowerDeviceD0 to a sleep state, the miniport driver can perform any necessary hardware accesses during the <code>PowerChangeState</code> call before it powers down the device.

While powered down, a miniport driver is never asked to create a miniport driver object or stream object. PortCls always places the device in the PowerDeviceD0 state before calling the miniport driver's <b>NewStream</b> method.

The code for this method must reside in paged memory.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536485">IAdapterPowerManagement</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536947">IPowerNotify</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a>
 

 

