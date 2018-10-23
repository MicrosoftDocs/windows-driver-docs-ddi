---
UID: NS:wdm._PO_FX_PERF_STATE_CHANGE
title: "_PO_FX_PERF_STATE_CHANGE"
author: windows-driver-content
description: The PO_FX_PERF_STATE_CHANGE structure contains information about a change to a performance state that is being requested by calling the PoFxIssueComponentPerfStateChange or PoFxIssueComponentPerfStateChangeMultiple routine.
old-location: kernel\po_fx_perf_state_change.htm
tech.root: kernel
ms.assetid: AE7A79DE-0202-4816-A36C-5A15C4539392
ms.date: 04/30/2018
ms.keywords: "*PPO_FX_PERF_STATE_CHANGE, PO_FX_PERF_STATE_CHANGE, PO_FX_PERF_STATE_CHANGE structure [Kernel-Mode Driver Architecture], PPO_FX_PERF_STATE_CHANGE, PPO_FX_PERF_STATE_CHANGE structure pointer [Kernel-Mode Driver Architecture], _PO_FX_PERF_STATE_CHANGE, kernel.po_fx_perf_state_change, wdm/PO_FX_PERF_STATE_CHANGE, wdm/PPO_FX_PERF_STATE_CHANGE"
ms.topic: struct
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
-	PO_FX_PERF_STATE_CHANGE
product:
- Windows
targetos: Windows
req.typenames: PO_FX_PERF_STATE_CHANGE, *PPO_FX_PERF_STATE_CHANGE
---

# _PO_FX_PERF_STATE_CHANGE structure


## -description


The <b>PO_FX_PERF_STATE_CHANGE</b> structure contains information about a change to a performance state that is being requested by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939769">PoFxIssueComponentPerfStateChange</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/dn939772">PoFxIssueComponentPerfStateChangeMultiple</a> routine.


## -struct-fields




### -field Set

The index of the performance state set that is being changed within the collection of performance state sets for the component.


### -field StateIndex

For sets that represent a discrete number of performance states (that is, where the <b>Type</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939833">PO_FX_COMPONENT_PERF_SET</a> is <b>PoFxPerfStateTypeDiscrete</b>), this member is the index of the performance state to use for the new performance level.


### -field StateValue

For sets that represent a continuous distribution of performance states (that is, where the <b>Type</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939833">PO_FX_COMPONENT_PERF_SET</a> is <b>PoFxPerfStateTypeRange</b>), this member is the value of the performance state to use for the new performance level.


## -remarks



The <b>PO_FX_PERF_STATE_CHANGE</b> structure is used for the <i>PerfChange</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939769">PoFxIssueComponentPerfStateChange</a> routine and the  <i>PerfChanges</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939772">PoFxIssueComponentPerfStateChangeMultiple</a> routine. 




## -see-also




<a href="https://msdn.microsoft.com/D5341D6D-7C71-43CB-9C70-7E939B32C33F">Device Performance State Management</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn939769">PoFxIssueComponentPerfStateChange</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn939772">PoFxIssueComponentPerfStateChangeMultiple</a>
 

 

