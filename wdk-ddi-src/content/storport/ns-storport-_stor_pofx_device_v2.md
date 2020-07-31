---
UID: NS:storport._STOR_POFX_DEVICE_V2
title: _STOR_POFX_DEVICE_V2 (storport.h)
description: The STOR_POFX_DEVICE_V2 structure describes the power attributes of a storage device to the power management framework (PoFx).
old-location: storage\stor_pofx_device_v2.htm
tech.root: storage
ms.assetid: 1AD3B5E6-CF90-49D2-8FF7-FE309E4331CE
ms.date: 03/29/2018
keywords: ["_STOR_POFX_DEVICE_V2 structure"]
ms.keywords: "*PSTOR_POFX_DEVICE_V2, PSTOR_POFX_DEVICE_V2, PSTOR_POFX_DEVICE_V2 structure pointer [Storage Devices], STOR_POFX_DEVICE_FLAG_ENABLE_D3_COLD, STOR_POFX_DEVICE_FLAG_IDLE_TIMEOUT, STOR_POFX_DEVICE_FLAG_NO_D0, STOR_POFX_DEVICE_FLAG_NO_D3, STOR_POFX_DEVICE_FLAG_NO_DUMP_ACTIVE, STOR_POFX_DEVICE_V2, STOR_POFX_DEVICE_V2 structure [Storage Devices], _STOR_POFX_DEVICE_V2, storage.stor_pofx_device_v2, storport/PSTOR_POFX_DEVICE_V2, storport/STOR_POFX_DEVICE_V2"
f1_keywords:
 - "storport/STOR_POFX_DEVICE_V2"
 - "STOR_POFX_DEVICE_V2"
req.header: storport.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- storport.h
api_name:
- STOR_POFX_DEVICE_V2
targetos: Windows
req.typenames: STOR_POFX_DEVICE_V2, *PSTOR_POFX_DEVICE_V2
---

# _STOR_POFX_DEVICE_V2 structure


## -description


The <b>STOR_POFX_DEVICE_V2</b> structure describes the power attributes of a storage device to the power management framework (PoFx). This structure is similar to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_stor_pofx_device">STOR_POFX_DEVICE</a> but contains additional timeout settings.


## -struct-fields




### -field Version

The version number of this structure. Set this member to <b>STOR_POFX_DEVICE_VERSION_V2</b>.


### -field Size

The size of this structure. Set this value to <b>STOR_POFX_DEVICE_SIZE</b>.


### -field ComponentCount

The number of elements in the <b>Components</b> array. Set this member to 1. Currently, only a single component is supported for either a storage adapter or logical unit.


### -field Flags

The device power state capabilities flags. The miniport sets one or more of the PoFx device flags to enable or disable power state capabilities.


<b>Flags</b> is a bitwise OR combination of the following.



<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="STOR_POFX_DEVICE_FLAG_NO_D0"></a><a id="stor_pofx_device_flag_no_d0"></a><dl>
<dt><b>STOR_POFX_DEVICE_FLAG_NO_D0</b></dt>
</dl>
</td>
<td width="60%">
Requests that a  power up IRP not be sent to the device object for the adapter or unit.

</td>
</tr>
<tr>
<td width="40%"><a id="STOR_POFX_DEVICE_FLAG_NO_D3"></a><a id="stor_pofx_device_flag_no_d3"></a><dl>
<dt><b>STOR_POFX_DEVICE_FLAG_NO_D3</b></dt>
</dl>
</td>
<td width="60%">
Requests that a  power down IRP not be sent to the device object for the adapter or unit.

</td>
</tr>
<tr>
<td width="40%"><a id="STOR_POFX_DEVICE_FLAG_ENABLE_D3_COLD"></a><a id="stor_pofx_device_flag_enable_d3_cold"></a><dl>
<dt><b>STOR_POFX_DEVICE_FLAG_ENABLE_D3_COLD</b></dt>
</dl>
</td>
<td width="60%">
Enables Storport to set the D3 Cold state for the adapter if
  it supports it. This flag applies to adapters only.

</td>
</tr>
<tr>
<td width="40%"><a id="STOR_POFX_DEVICE_FLAG_NO_DUMP_ACTIVE"></a><a id="stor_pofx_device_flag_no_dump_active"></a><dl>
<dt><b>STOR_POFX_DEVICE_FLAG_NO_DUMP_ACTIVE</b></dt>
</dl>
</td>
<td width="60%">
The miniport is not able to bring the storage device active in dump mode if the device has entered the idle state or the power off when idle state.
This flag indicates whether a device is available for dump when it is idle.

</td>
</tr>
<tr>
<td width="40%"><a id="STOR_POFX_DEVICE_FLAG_IDLE_TIMEOUT"></a><a id="stor_pofx_device_flag_idle_timeout"></a><dl>
<dt><b>STOR_POFX_DEVICE_FLAG_IDLE_TIMEOUT</b></dt>
</dl>
</td>
<td width="60%">
The timeout value in <b>UnitMinIdleTimeoutInMS</b>  or <b>AdapterIdleTimeoutInMS</b> is used for the D3 idle timeout.

</td>
</tr>
</table>
 


### -field UnitMinIdleTimeoutInMS

The minimum idle time in milliseconds for an unit. This value is only valid when STOR_POFX_DEVICE_FLAG_IDLE_TIMEOUT is set in <b>Flags</b>.


### -field AdapterIdleTimeoutInMS

The adapter idle timeout value in milliseconds. This value is only valid when STOR_POFX_DEVICE_FLAG_IDLE_TIMEOUT is set in <b>Flags</b>.


### -field Components

This member is the first element in an array of one or more <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_stor_pofx_component">STOR_POFX_COMPONENT</a> elements. If the array contains more than one element, the additional elements immediately follow the <b>STOR_POFX_DEVICE</b> structure. The array contains one element for each component in the device.  Currently, storage devices have only  one component so additional component structures are unnecessary.


## -remarks



To register a storage adapter for Storport PoFx support, the miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportenablepassiveinitialization">StorPortEnablePassiveInitialization</a> in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_initialize">HwStorInitialize</a> routine and implements a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_passive_initialize_routine">HwStorPassiveInitializeRoutine</a>. The miniport calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinitializepofxpower">StorPortInitializePoFxPower</a> within it's <b>HwStorPassiveInitializeRoutine</b> to provide information about the adapter component.

To register a storage unit for Storport PoFx support, the miniport driver implements the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_unit_control">HwStorUnitControl</a> callback routine and provides handling of the <b>ScsiUnitPoFxPowerInfo</b> unit control code. When the handling the <b>ScsiUnitPoFxPowerInfo</b> control code, the miniport calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinitializepofxpower">StorPortInitializePoFxPower</a> if idle power management for the unit component is enabled.

The component for the storage device identified by its <b>Components</b> array index. Storage devices have only one component so the index of 0 is used.  Routines such as  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportpofxactivatecomponent">StorPortPoFxActivateComponent</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportpofxidlecomponent">StorPortPoFxIdleComponent</a> use the array index of a component to identify the component.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_stor_pofx_component">STOR_POFX_COMPONENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_stor_pofx_device">STOR_POFX_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinitializepofxpower">StorPortInitializePoFxPower</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportpofxactivatecomponent">StorPortPoFxActivateComponent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportpofxidlecomponent">StorPortPoFxIdleComponent</a>
 

 

