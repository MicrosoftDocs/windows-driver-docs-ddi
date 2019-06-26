---
UID: NF:portcls.PcRequestNewPowerState
title: PcRequestNewPowerState function (portcls.h)
description: The PcRequestNewPowerState function is used to request a new power state for the device. This function is typically not needed by adapter drivers but can occasionally be useful in working around some kinds of hardware problems.
old-location: audio\pcrequestnewpowerstate.htm
tech.root: audio
ms.assetid: fbe2c665-a7e8-43e4-95e5-a7e87521e163
ms.date: 05/08/2018
ms.keywords: PcRequestNewPowerState, PcRequestNewPowerState function [Audio Devices], audio.pcrequestnewpowerstate, audpc-routines_c3341fb0-4609-4b3f-a0b2-ef589c804f1d.xml, portcls/PcRequestNewPowerState
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcRequestNewPowerState function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
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
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Portcls.lib
- Portcls.dll
api_name:
- PcRequestNewPowerState
product:
- Windows
targetos: Windows
req.typenames: 
---

# PcRequestNewPowerState function


## -description


The <b>PcRequestNewPowerState</b> function is used to request a new power state for the device. This function is typically not needed by adapter drivers but can occasionally be useful in working around some kinds of hardware problems.


## -parameters




### -param pDeviceObject [in]

Pointer to the adapter's <a href="https://docs.microsoft.com/windows-hardware/drivers/">functional device object (FDO)</a>. This parameter must point to a system structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>.


### -param RequestedNewState [in]

Specifies the device power state being requested. Set this parameter to one of the following DEVICE_POWER_STATE enumeration values: <b>PowerDeviceD0</b>, <b>PowerDeviceD1</b>, <b>PowerDeviceD2</b>, or <b>PowerDeviceD3</b>.


## -returns



<b>PcRequestNewPowerState</b> returns STATUS_SUCCESS if the call was successful. Otherwise, returns an appropriate error message.




## -remarks



An adapter driver can call <b>PcRequestNewPowerState</b> to compensate for hardware design flaws. For example, if the functions in an audio adapter are not mutually independent and need to be shut down in a particular order, the adapter can call <b>PcRequestNewPowerState</b> to ensure that a particular subdevice is shut down first.

The <b>RequestedNewState</b> parameter can be set to one of the DEVICE_POWER_STATE enumeration values in the following table.

<table>
<tr>
<th>Power State</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>PowerDeviceD0</b>

</td>
<td>
Full power state

</td>
</tr>
<tr>
<td>
<b>PowerDeviceD1</b>

</td>
<td>
The sleep state with the lowest power-up latency

</td>
</tr>
<tr>
<td>
<b>PowerDeviceD2</b>

</td>
<td>
A medium-latency sleep state

</td>
</tr>
<tr>
<td>
<b>PowerDeviceD3</b>

</td>
<td>
A full hibernation state and the sleep state with the longest power-up latency

</td>
</tr>
</table>
 

The hardware can be accessed only in power state <b>PowerDeviceD0</b>. In any other state, the driver must cache any attempted hardware accesses and defer those accesses until the <b>PowerDeviceD0</b> state is restored.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/power-management-for-audio-devices">Power Management for Audio Devices</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>
 

 

