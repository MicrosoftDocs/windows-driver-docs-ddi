---
UID: NS:storport._STOR_POFX_COMPONENT_IDLE_STATE
title: "_STOR_POFX_COMPONENT_IDLE_STATE"
author: windows-driver-content
description: The STOR_POFX_COMPONENT_IDLE_STATE structure specifies the attributes of an functional power state (F-state) of a component in a storage device.
old-location: storage\stor_pofx_component_idle_state.htm
old-project: storage
ms.assetid: 2600405F-AE07-4284-84AD-D19EEE2058BF
ms.author: windowsdriverdev
ms.date: 2/24/2018
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Storport.h
apiname:
-	STOR_POFX_COMPONENT_IDLE_STATE
product: Windows
targetos: Windows
req.typenames: STOR_POFX_COMPONENT_IDLE_STATE, *PSTOR_POFX_COMPONENT_IDLE_STATE
req.product: Windows 10 or later.
---

# _STOR_POFX_COMPONENT_IDLE_STATE structure


## -description


The <b>STOR_POFX_COMPONENT_IDLE_STATE</b> structure specifies the attributes of an functional power state (F-state) of a component in a storage device.


## -syntax


````
typedef struct _STOR_POFX_COMPONENT_IDLE_STATE {
  USHORT    Version;
  USHORT    Size;
  ULONGLONG TransitionLatency;
  ULONGLONG ResidencyRequirement;
  ULONG     NominalPower;
} STOR_POFX_COMPONENT_IDLE_STATE, *PSTOR_POFX_COMPONENT_IDLE_STATE;
````


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



 The <a href="..\storport\ns-storport-_stor_pofx_component.md">STOR_POFX_COMPONENT</a> structure contains an array of <b>STOR_POFX_COMPONENT_IDLE_STATE</b> structures. Each array element specifies the attributes of an F-state. Element 0 describes F0, element 1 describes F1, and so on.

When the miniport driver registers a device with the Storport power management framework, the driver supplies an array of <a href="..\storport\ns-storport-_stor_pofx_component.md">STOR_POFX_COMPONENT</a> structures. Each array element describes the power attributes of a component in the device.




## -see-also

<a href="..\storport\ns-storport-_stor_pofx_component.md">STOR_POFX_COMPONENT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STOR_POFX_COMPONENT_IDLE_STATE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

