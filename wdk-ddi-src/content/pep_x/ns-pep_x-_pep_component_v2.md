---
UID: NS:pep_x._PEP_COMPONENT_V2
title: "_PEP_COMPONENT_V2"
author: windows-driver-content
description: The PEP_COMPONENT_V2 structure specifies the power state attributes of a component in the device.
old-location: kernel\pep_component_v2.htm
old-project: kernel
ms.assetid: 6C7AB917-1A98-471C-BA6C-B7C6BFF1AC3F
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PPEP_COMPONENT, *PPEP_COMPONENT_V2, PEP_COMPONENT, PEP_COMPONENT_V2, PEP_COMPONENT_V2 structure [Kernel-Mode Driver Architecture], PPEP_COMPONENT_V2, PPEP_COMPONENT_V2 structure pointer [Kernel-Mode Driver Architecture], _PEP_COMPONENT_V2, kernel.pep_component_v2, pepfx/PEP_COMPONENT_V2, pepfx/PPEP_COMPONENT_V2"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_COMPONENT_V2
product: Windows
targetos: Windows
req.typenames: PEP_COMPONENT_V2, *PPEP_COMPONENT_V2, PEP_COMPONENT_V2, *PPEP_COMPONENT_V2
---

# _PEP_COMPONENT_V2 structure


## -description


The <b>PEP_COMPONENT_V2</b> structure specifies the power state attributes of a component in the device.


## -syntax


````
typedef struct _PEP_COMPONENT_V2 {
  GUID                        Id;
  ULONGLONG                   Flags;
  ULONG                       DeepestWakeableIdleState;
  ULONG                       IdleStateCount;
  PPO_FX_COMPONENT_IDLE_STATE IdleStates;
} PEP_COMPONENT_V2, *PPEP_COMPONENT_V2;
````


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

A pointer to an array of <a href="..\wudfwdm\ns-wudfwdm-_po_fx_component_idle_state.md">PO_FX_COMPONENT_IDLE_STATE</a> structures. The length of this array is specified by the <b>IdleStateCount</b> member. Each array element specifies the attributes of an F<i>x</i> power state that is supported by the component. Element 0 describes F0, element 1 describes F1, and so on.


## -remarks



This structure 




## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_po_fx_component_idle_state.md">PO_FX_COMPONENT_IDLE_STATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_COMPONENT_V2 structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

