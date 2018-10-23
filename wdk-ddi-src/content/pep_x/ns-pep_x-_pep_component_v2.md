---
UID: NS:pep_x._PEP_COMPONENT_V2
title: "_PEP_COMPONENT_V2"
author: windows-driver-content
description: The PEP_COMPONENT_V2 structure specifies the power state attributes of a component in the device.
old-location: kernel\pep_component_v2.htm
tech.root: kernel
ms.assetid: 6C7AB917-1A98-471C-BA6C-B7C6BFF1AC3F
ms.date: 04/30/2018
ms.keywords: "*PPEP_COMPONENT, *PPEP_COMPONENT_V2, PEP_COMPONENT, PEP_COMPONENT_V2, PEP_COMPONENT_V2 structure [Kernel-Mode Driver Architecture], PPEP_COMPONENT_V2, PPEP_COMPONENT_V2 structure pointer [Kernel-Mode Driver Architecture], _PEP_COMPONENT_V2, kernel.pep_component_v2, pepfx/PEP_COMPONENT_V2, pepfx/PPEP_COMPONENT_V2"
ms.topic: struct
req.header: pep_x.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
-	pepfx.h
api_name:
-	PEP_COMPONENT_V2
product:
- Windows
targetos: Windows
req.typenames: PEP_COMPONENT_V2, *PPEP_COMPONENT_V2
---

# _PEP_COMPONENT_V2 structure


## -description


The <b>PEP_COMPONENT_V2</b> structure specifies the power state attributes of a component in the device.


## -struct-fields




### -field Id

A component ID that uniquely identifies this component with respect to the other components in the device. The PEP should specify a nonzero value for this member if the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) requires a component ID to distinguish this component from other, similar components in the same device. This member is optional. If this member is not used, it must be set to all zeros.


### -field Flags

A set of component-power-state flags. No flags are currently defined for this member, which is always zero.


### -field DeepestWakeableIdleState

The index of the deepest F<i>x</i> state from which the component can wake. Specify 0 for F0, 1 for F1, and so on. This index must be less than <b>IdleStateCount</b>.


### -field IdleStateCount

The number of elements in the array that is pointed to by the <b>IdleStates</b> member. Additionally, this member specifies the number of F<i>x</i> power states that the component supports. A component must support at least one F<i>x</i> state (F0).


### -field IdleStates

A pointer to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/hh439581">PO_FX_COMPONENT_IDLE_STATE</a> structures. The length of this array is specified by the <b>IdleStateCount</b> member. Each array element specifies the attributes of an F<i>x</i> power state that is supported by the component. Element 0 describes F0, element 1 describes F1, and so on.


## -remarks



This structure 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439581">PO_FX_COMPONENT_IDLE_STATE</a>
 

 

