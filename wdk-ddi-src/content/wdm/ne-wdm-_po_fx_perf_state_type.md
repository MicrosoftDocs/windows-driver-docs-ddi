---
UID: NE:wdm._PO_FX_PERF_STATE_TYPE
title: "_PO_FX_PERF_STATE_TYPE"
author: windows-driver-content
description: The PO_FX_PERF_STATE_TYPE enumeration contains values that describe the type of performance states in a PO_FX_COMPONENT_PERF_SET.
old-location: kernel\po_fx_perf_state_type.htm
old-project: kernel
ms.assetid: E3BFBF03-8130-4EFF-95F4-030107AF4D75
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: "*PPO_FX_PERF_STATE_TYPE, wdm/PoFxPerfStateTypeMaximum, PoFxPerfStateTypeDiscrete, wdm/PoFxPerfStateTypeDiscrete, PoFxPerfStateTypeRange, wdm/PoFxPerfStateTypeRange, _PO_FX_PERF_STATE_TYPE, wdm/PO_FX_PERF_STATE_TYPE, PoFxPerfStateTypeMaximum, PO_FX_PERF_STATE_TYPE enumeration [Kernel-Mode Driver Architecture], wdm/PPO_FX_PERF_STATE_TYPE, PPO_FX_PERF_STATE_TYPE enumeration pointer [Kernel-Mode Driver Architecture], PO_FX_PERF_STATE_TYPE, PPO_FX_PERF_STATE_TYPE, kernel.po_fx_perf_state_type"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: 
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
req.irql: Called at PASSIVE_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	PO_FX_PERF_STATE_TYPE
product: Windows
targetos: Windows
req.typenames: "*PPO_FX_PERF_STATE_TYPE, PO_FX_PERF_STATE_TYPE"
req.product: Windows 10 or later.
---

# _PO_FX_PERF_STATE_TYPE enumeration


## -description


The <b>PO_FX_PERF_STATE_TYPE</b> enumeration contains values that describe the type of performance states in a <a href="..\wdm\ns-wdm-_po_fx_component_perf_set.md">PO_FX_COMPONENT_PERF_SET</a>.


## -syntax


````
typedef enum _PO_FX_PERF_STATE_TYPE { 
  PoFxPerfStateTypeDiscrete,
  PoFxPerfStateTypeRange,
  PoFxPerfStateTypeMaximum
} PO_FX_PERF_STATE_TYPE, *PPO_FX_PERF_STATE_TYPE;
````


## -enum-fields




### -field PoFxPerfStateTypeDiscrete

Indicates that the performance state set contains a discrete number of states.


### -field PoFxPerfStateTypeRange

Indicates that the performance state set contains a continuous distribution of  states between a minimum and maximum value.


### -field PoFxPerfStateTypeMaximum

This value is reserved for system use.


## -remarks



The <b>Type</b> member of the <a href="..\wdm\ns-wdm-_po_fx_component_perf_set.md">PO_FX_COMPONENT_PERF_SET</a> structure is a value from the <b>PO_FX_PERF_STATE_TYPE</b> enumeration.




## -see-also

<a href="..\wdm\nf-wdm-pofxregistercomponentperfstates.md">PoFxRegisterComponentPerfStates</a>



<a href="..\wdm\ns-wdm-_po_fx_component_perf_set.md">PO_FX_COMPONENT_PERF_SET</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PO_FX_PERF_STATE_TYPE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

