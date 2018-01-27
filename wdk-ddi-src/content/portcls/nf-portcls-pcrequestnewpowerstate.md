---
UID: NF:portcls.PcRequestNewPowerState
title: PcRequestNewPowerState function
author: windows-driver-content
description: The PcRequestNewPowerState function is used to request a new power state for the device. This function is typically not needed by adapter drivers but can occasionally be useful in working around some kinds of hardware problems.
old-location: audio\pcrequestnewpowerstate.htm
old-project: audio
ms.assetid: fbe2c665-a7e8-43e4-95e5-a7e87521e163
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PcRequestNewPowerState, audio.pcrequestnewpowerstate, PcRequestNewPowerState function [Audio Devices], audpc-routines_c3341fb0-4609-4b3f-a0b2-ef589c804f1d.xml, portcls/PcRequestNewPowerState
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	Portcls.lib
-	Portcls.dll
apiname: 
-	PcRequestNewPowerState
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# PcRequestNewPowerState function


## -description


The <b>PcRequestNewPowerState</b> function is used to request a new power state for the device. This function is typically not needed by adapter drivers but can occasionally be useful in working around some kinds of hardware problems.


## -syntax


````
NTSTATUS PcRequestNewPowerState(
  _In_ PDEVICE_OBJECT     pDeviceObject,
  _In_ DEVICE_POWER_STATE RequestedNewState
);
````


## -parameters




### -param pDeviceObject [in]

Pointer to the adapter's <a href="https://msdn.microsoft.com/f697e0db-1db0-4a81-94d8-0ca079885480">functional device object (FDO)</a>. This parameter must point to a system structure of type <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>.


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

For more information, see <a href="https://msdn.microsoft.com/3d3d63af-5790-4760-9099-7116ed5a5446">Power Management for Audio Devices</a>.



## -see-also

<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcRequestNewPowerState function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

