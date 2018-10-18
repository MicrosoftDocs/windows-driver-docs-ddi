---
UID: NE:wdm._PO_FX_PERF_STATE_TYPE
title: "_PO_FX_PERF_STATE_TYPE"
author: windows-driver-content
description: The PO_FX_PERF_STATE_TYPE enumeration contains values that describe the type of performance states in a PO_FX_COMPONENT_PERF_SET.
old-location: kernel\po_fx_perf_state_type.htm
tech.root: kernel
ms.assetid: E3BFBF03-8130-4EFF-95F4-030107AF4D75
ms.date: 04/30/2018
ms.keywords: "*PPO_FX_PERF_STATE_TYPE, PO_FX_PERF_STATE_TYPE, PO_FX_PERF_STATE_TYPE enumeration [Kernel-Mode Driver Architecture], PPO_FX_PERF_STATE_TYPE, PPO_FX_PERF_STATE_TYPE enumeration pointer [Kernel-Mode Driver Architecture], PoFxPerfStateTypeDiscrete, PoFxPerfStateTypeMaximum, PoFxPerfStateTypeRange, _PO_FX_PERF_STATE_TYPE, kernel.po_fx_perf_state_type, wdm/PO_FX_PERF_STATE_TYPE, wdm/PPO_FX_PERF_STATE_TYPE, wdm/PoFxPerfStateTypeDiscrete, wdm/PoFxPerfStateTypeMaximum, wdm/PoFxPerfStateTypeRange"
ms.topic: enum
req.header: wdm.h
req.include-header: Wudfwdm.h
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
-	Wdm.h
api_name:
-	PO_FX_PERF_STATE_TYPE
product:
- Windows
targetos: Windows
req.typenames: PO_FX_PERF_STATE_TYPE, *PPO_FX_PERF_STATE_TYPE
---

# _PO_FX_PERF_STATE_TYPE enumeration


## -description


The <b>PO_FX_PERF_STATE_TYPE</b> enumeration contains values that describe the type of performance states in a <a href="https://msdn.microsoft.com/library/windows/hardware/dn939833">PO_FX_COMPONENT_PERF_SET</a>.


## -enum-fields




### -field PoFxPerfStateTypeDiscrete

Indicates that the performance state set contains a discrete number of states.


### -field PoFxPerfStateTypeRange

Indicates that the performance state set contains a continuous distribution of  states between a minimum and maximum value.


### -field PoFxPerfStateTypeMaximum

This value is reserved for system use.


## -remarks



The <b>Type</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939833">PO_FX_COMPONENT_PERF_SET</a> structure is a value from the <b>PO_FX_PERF_STATE_TYPE</b> enumeration.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn939833">PO_FX_COMPONENT_PERF_SET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn939778">PoFxRegisterComponentPerfStates</a>
 

 

