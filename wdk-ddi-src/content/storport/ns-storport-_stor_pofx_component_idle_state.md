---
UID: NS:storport._STOR_POFX_COMPONENT_IDLE_STATE
title: "_STOR_POFX_COMPONENT_IDLE_STATE"
author: windows-driver-content
description: The STOR_POFX_COMPONENT_IDLE_STATE structure specifies the attributes of an functional power state (F-state) of a component in a storage device.
old-location: storage\stor_pofx_component_idle_state.htm
old-project: storage
ms.assetid: 2600405F-AE07-4284-84AD-D19EEE2058BF
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSTOR_POFX_COMPONENT_IDLE_STATE, PSTOR_POFX_COMPONENT_IDLE_STATE, PSTOR_POFX_COMPONENT_IDLE_STATE structure pointer [Storage Devices], STOR_POFX_COMPONENT_IDLE_STATE, STOR_POFX_COMPONENT_IDLE_STATE structure [Storage Devices], _STOR_POFX_COMPONENT_IDLE_STATE, storage.stor_pofx_component_idle_state, storport/PSTOR_POFX_COMPONENT_IDLE_STATE, storport/STOR_POFX_COMPONENT_IDLE_STATE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h
req.target-type: Windows
req.target-min-winverclnt: Available in starting with Windows 8.
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
-	Storport.h
api_name:
-	STOR_POFX_COMPONENT_IDLE_STATE
product:
- Windows
targetos: Windows
req.typenames: STOR_POFX_COMPONENT_IDLE_STATE, *PSTOR_POFX_COMPONENT_IDLE_STATE
---

# _STOR_POFX_COMPONENT_IDLE_STATE structure


## -description


The <b>STOR_POFX_COMPONENT_IDLE_STATE</b> structure specifies the attributes of an functional power state (F-state) of a component in a storage device.


## -struct-fields




### -field Version

The version of this structure. Set this member to <b>STOR_POFX_COMPONENT_IDLE_STATE_VERSION_V1</b>.


### -field Size

The size of this structure. Set this value to <b>STOR_POFX_COMPONENT_IDLE_STATE_SIZE</b>.


### -field TransitionLatency

The transition latency. This latency is the amount of time, in 100-nanosecond units, that the component requires to return from this F-state to the F0 state. For a <b>STOR_POFX_COMPONENT_IDLE_STATE</b> structure that specifies the attributes of the F0 state, set this member to zero. Set this member to STOR_PO_FX_UNKNOWN_TIME to indicate that the power management framework (PoFx) should ignore (treat as negligible) the component's transition latency from this F-state when PoFx evaluates which power state to switch to when the component is idle.


### -field ResidencyRequirement

The residency requirement. The residency requirement is the minimum amount of time, in 100-nanosecond units, that the component must spend in this F-state to make a transition to this F-state worthwhile. PoFx uses this member value as a hint to avoid switching a component to an F-state unless the component is likely to remain in this state for at least the amount of time specified by <b>ResidencyRequirement</b>. For a STOR_PO_FX_COMPONENT_IDLE_STATE structure that describes the attributes of the F0 state, set this member to zero. Set this member to STOR_PO_FX_UNKNOWN_TIME to indicate that PoFx should ignore (treat as negligible) the component's residency requirement for this F-state when PoFx evaluates which power state to switch to when the component is idle.


### -field NominalPower

The power, in microwatts, that the component consumes in this F-state. Set this member to STOR_PO_FX_UNKNOWN_POWER to indicate that PoFx should ignore (treat as negligible) the component's internal power consumption in this F-state when PoFx evaluates which power state to switch to when the component is idle. 


## -remarks



 The <a href="https://msdn.microsoft.com/library/windows/hardware/hh920427">STOR_POFX_COMPONENT</a> structure contains an array of <b>STOR_POFX_COMPONENT_IDLE_STATE</b> structures. Each array element specifies the attributes of an F-state. Element 0 describes F0, element 1 describes F1, and so on.

When the miniport driver registers a device with the Storport power management framework, the driver supplies an array of <a href="https://msdn.microsoft.com/library/windows/hardware/hh920427">STOR_POFX_COMPONENT</a> structures. Each array element describes the power attributes of a component in the device.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh920427">STOR_POFX_COMPONENT</a>
 

 

