---
UID: NS:storport._STOR_POFX_DEVICE_V2
title: "_STOR_POFX_DEVICE_V2"
author: windows-driver-content
description: The STOR_POFX_DEVICE_V2 structure describes the power attributes of a storage device to the power management framework (PoFx).
old-location: storage\stor_pofx_device_v2.htm
old-project: storage
ms.assetid: 1AD3B5E6-CF90-49D2-8FF7-FE309E4331CE
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: STOR_POFX_DEVICE_V2 structure [Storage Devices], STOR_POFX_DEVICE_FLAG_IDLE_TIMEOUT, _STOR_POFX_DEVICE_V2, PSTOR_POFX_DEVICE_V2 structure pointer [Storage Devices], STOR_POFX_DEVICE_FLAG_NO_D0, *PSTOR_POFX_DEVICE_V2, STOR_POFX_DEVICE_FLAG_NO_DUMP_ACTIVE, STOR_POFX_DEVICE_FLAG_NO_D3, PSTOR_POFX_DEVICE_V2, storport/STOR_POFX_DEVICE_V2, storport/PSTOR_POFX_DEVICE_V2, STOR_POFX_DEVICE_V2, storage.stor_pofx_device_v2, STOR_POFX_DEVICE_FLAG_ENABLE_D3_COLD
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	storport.h
apiname:
-	STOR_POFX_DEVICE_V2
product: Windows
targetos: Windows
req.typenames: "*PSTOR_POFX_DEVICE_V2, STOR_POFX_DEVICE_V2"
req.product: Windows 10 or later.
---

# _STOR_POFX_DEVICE_V2 structure


## -description


The <b>STOR_POFX_DEVICE_V2</b> structure describes the power attributes of a storage device to the power management framework (PoFx). This structure is similar to <a href="..\storport\ns-storport-_stor_pofx_device.md">STOR_POFX_DEVICE</a> but contains additional timeout settings.


## -syntax


````
typedef struct _STOR_POFX_DEVICE_V2 {
  ULONG               Version;
  USHORT              Size;
  ULONG               ComponentCount;
  ULONG               Flags;
  union {
    ULONG UnitMinIdleTimeoutInMS;
    ULONG AdapterIdleTimeoutInMS;
  };
  STOR_POFX_COMPONENT Components[ANYSIZE_ARRAY];
} STOR_POFX_DEVICE_V2, *PSTOR_POFX_DEVICE_V2;
````


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

This member is the first element in an array of one or more <a href="..\wdm\ns-wdm-_po_fx_component_v2.md">STOR_POFX_COMPONENT</a> elements. If the array contains more than one element, the additional elements immediately follow the <b>STOR_POFX_DEVICE</b> structure. The array contains one element for each component in the device.  Currently, storage devices have only  one component so additional component structures are unnecessary.


## -remarks



To register a storage adapter for Storport PoFx support, the miniport driver calls <a href="..\storport\nf-storport-storportenablepassiveinitialization.md">StorPortEnablePassiveInitialization</a> in its <a href="..\storport\nc-storport-hw_initialize.md">HwStorInitialize</a> routine and implements a <a href="..\storport\nc-storport-hw_passive_initialize_routine.md">HwStorPassiveInitializeRoutine</a>. The miniport calls <a href="..\storport\nf-storport-storportinitializepofxpower.md">StorPortInitializePoFxPower</a> within it's <b>HwStorPassiveInitializeRoutine</b> to provide information about the adapter component.

To register a storage unit for Storport PoFx support, the miniport driver implements the <a href="..\storport\nc-storport-hw_unit_control.md">HwStorUnitControl</a> callback routine and provides handling of the <b>ScsiUnitPoFxPowerInfo</b> unit control code. When the handling the <b>ScsiUnitPoFxPowerInfo</b> control code, the miniport calls <a href="..\storport\nf-storport-storportinitializepofxpower.md">StorPortInitializePoFxPower</a> if idle power management for the unit component is enabled.

The component for the storage device identified by its <b>Components</b> array index. Storage devices have only one component so the index of 0 is used.  Routines such as  <a href="..\storport\nf-storport-storportpofxactivatecomponent.md">StorPortPoFxActivateComponent</a> and <a href="..\storport\nf-storport-storportpofxidlecomponent.md">StorPortPoFxIdleComponent</a> use the array index of a component to identify the component.




## -see-also

<a href="..\storport\ns-storport-_stor_pofx_device.md">STOR_POFX_DEVICE</a>



<a href="..\wdm\ns-wdm-_po_fx_component_v2.md">STOR_POFX_COMPONENT</a>



<a href="..\storport\nf-storport-storportinitializepofxpower.md">StorPortInitializePoFxPower</a>



<a href="..\storport\nf-storport-storportpofxactivatecomponent.md">StorPortPoFxActivateComponent</a>



<a href="..\storport\nf-storport-storportpofxidlecomponent.md">StorPortPoFxIdleComponent</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STOR_POFX_DEVICE_V2 structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

