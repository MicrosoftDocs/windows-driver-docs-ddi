---
UID: NS:ks._KSDEVICE_THERMAL_DISPATCH
title: "_KSDEVICE_THERMAL_DISPATCH"
author: windows-driver-content
description: The KSDEVICE_THERMAL_DISPATCH structure is used by the miniport driver in the API call to register thermal notification callbacks. This structure contains the callback function pointers for active and passive cooling interfaces.
old-location: stream\ksdevice_thermal_dispatch.htm
old-project: stream
ms.assetid: 6E4ADD86-EFC4-4369-83A1-1D2824235310
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSDEVICE_THERMAL_DISPATCH, DeviceThermalState, Engaged, KSDEVICE_THERMAL_DISPATCH, KSDEVICE_THERMAL_DISPATCH structure [Streaming Media Devices], KsDevice, PKSDEVICE_THERMAL_DISPATCH, PKSDEVICE_THERMAL_DISPATCH structure pointer [Streaming Media Devices], Percentage, _KSDEVICE_THERMAL_DISPATCH, ks/KSDEVICE_THERMAL_DISPATCH, ks/PKSDEVICE_THERMAL_DISPATCH, stream.ksdevice_thermal_dispatch"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
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
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KSDEVICE_THERMAL_DISPATCH
product:
- Windows
targetos: Windows
req.typenames: KSDEVICE_THERMAL_DISPATCH, *PKSDEVICE_THERMAL_DISPATCH
---

# _KSDEVICE_THERMAL_DISPATCH structure


## -description


The <b>KSDEVICE_THERMAL_DISPATCH</b> structure is used by the miniport driver in the API call to register thermal notification callbacks. This structure contains the callback function pointers for active and passive cooling interfaces. 


## -struct-fields




### -field ActiveCooling

The active thermal callback notification. The routine is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_IRQL_requires_max_(PASSIVE_LEVEL)
typedef
void
(*PFNKSDEVICETHERMALACTIVECOOLING)(
    _In_  PKSDEVICE KsDevice,
    _In_  BOOLEAN Engaged,
    _Out_ KSDEVICE_THERMAL_STATE* DeviceThermalState
);</pre>
</td>
</tr>
</table></span></div>


#### KsDevice

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff561681">KSDEVICE</a> object representing the device managed by KS.



#### Engaged

[in] Indicates whether to engage or disengage active cooling. If <b>TRUE</b>, the driver must engage active cooling (for example, by turning the fan on). If <b>FALSE</b>, the driver must disengage active cooling (for example, by turning the fan off).



#### DeviceThermalState

[out] Return value: Avstream-determined thermal state. If the state changes the pipeline is notified of the change. The pipeline notifies any app registered for thermal notifications. For more information, see the <a href="https://msdn.microsoft.com/library/windows/hardware/hh698235">ActiveCooling</a> routine.


### -field PassiveCooling

The passive thermal callback notification.. The routine is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_IRQL_requires_max_(PASSIVE_LEVEL)
typedef
void
(*PFNKSDEVICETHERMALPASSIVECOOLING)(
    _In_  PKSDEVICE KsDevice,
    _In_  ULONG Percentage,
    _Out_ KSDEVICE_THERMAL_STATE* DeviceThermalState
);</pre>
</td>
</tr>
</table></span></div>


#### KsDevice

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff561681">KSDEVICE</a> object representing the device managed by KS.



#### Percentage

[in] The percentage of full performance at which the device is permitted to operate. A parameter value of 100 indicates that the device is under no cooling restrictions and can operate at full performance level. A parameter value of zero indicates that the device must operate at its lowest thermal level. A parameter value between 0 and 100 indicates the degree to which the device's performance must be throttled to reduce heat generation. This parameter value is a threshold that the device must not exceed.



#### DeviceThermalState

[out] Return value: Avstream-determined thermal state. If the state changes the pipeline is notified of the change. The pipeline notifies any app registered for thermal notifications. For more information, see the  <a href="https://msdn.microsoft.com/library/windows/hardware/hh698270">PassiveCooling</a> routine.

