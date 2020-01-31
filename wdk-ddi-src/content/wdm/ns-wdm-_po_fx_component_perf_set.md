---
UID: NS:wdm._PO_FX_COMPONENT_PERF_SET
title: _PO_FX_COMPONENT_PERF_SET (wdm.h)
description: The PO_FX_COMPONENT_PERF_SET structure represents a set of performance states for a single component within a device.
old-location: kernel\po_fx_component_perf_set.htm
tech.root: kernel
ms.assetid: 2305BE73-8363-4534-A64D-06C91F636E2F
ms.date: 04/30/2018
ms.keywords: "*PPO_FX_COMPONENT_PERF_SET, PO_FX_COMPONENT_PERF_SET, PO_FX_COMPONENT_PERF_SET structure [Kernel-Mode Driver Architecture], PPO_FX_COMPONENT_PERF_SET, PPO_FX_COMPONENT_PERF_SET structure pointer [Kernel-Mode Driver Architecture], _PO_FX_COMPONENT_PERF_SET, kernel.po_fx_component_perf_set, wdm/PO_FX_COMPONENT_PERF_SET, wdm/PPO_FX_COMPONENT_PERF_SET"
f1_keywords:
 - "wdm/PO_FX_COMPONENT_PERF_SET"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- PO_FX_COMPONENT_PERF_SET
product:
- Windows
targetos: Windows
req.typenames: PO_FX_COMPONENT_PERF_SET, *PPO_FX_COMPONENT_PERF_SET
---

# _PO_FX_COMPONENT_PERF_SET structure


## -description


The <b>PO_FX_COMPONENT_PERF_SET</b> structure represents a set of performance states for a single component within a device.


## -struct-fields




### -field Name

An optional character string used to describe the component property controlled by the performance state set. For example, "Clock frequency" or "Memory bandwidth".


### -field Flags

Set to 0. Currently, no flags are defined for this member.


### -field Unit

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_po_fx_perf_state_unit">PO_FX_PERF_STATE_UNIT</a> value that specifies the type of unit that is controlled by the performance state set. 


### -field Type

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_po_fx_perf_state_type">PO_FX_PERF_STATE_TYPE</a> value that specifies the type of performance states in the set (a discrete number of states or a continuous distribution of states between a minimum and maximum value). 


### -field Discrete

For sets that represent a discrete number of performance states (that is, where the <b>Type</b> member is <b>PoFxPerfStateTypeDiscrete</b>), this nested structure describes the  states.


### -field Discrete.Count

The number of performance states in the set.


### -field Discrete.States

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_perf_state">PO_FX_PERF_STATE</a> array. The length of this array is specified by the <b>Count</b> member. Each array element describes one power state in the set.


### -field Range

For sets that represent a continuous distribution of performance states (that is, where the <b>Type</b> member is <b>PoFxPerfStateTypeRange</b>), this nested structure describes the minimum and maximum value of the range of performance states.


### -field Range.Minimum

The minimum performance state value.


### -field Range.Maximum

The maximum performance state value.


## -remarks



When a device driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregistercomponentperfstates">PoFxRegisterComponentPerfStates</a> routine to register a component for performance state support with the power management framework (PoFx),  the driver can supply a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_component_perf_info">PO_FX_COMPONENT_PERF_INFO</a> structure that  describes the sets of the performance states supported by the component. The <b>PerfStateSets</b> member of the <b>PO_FX_COMPONENT_PERF_INFO</b> structure contains an array of <b>PO_FX_COMPONENT_PERF_SET</b> structures that represent the supported performance states.

Most drivers are expected to define a single set of performance states per component. For example, a driver might define one set of performance states to control the clock frequency for a component. However, some drivers may need to define more than one performance state set to control multiple dimensions of performance states for a component. For example, a driver might define two sets of performance states to control the clock frequency and bus bandwidth.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/component-level-performance-management">Device Performance State Management</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_component_perf_info">PO_FX_COMPONENT_PERF_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregistercomponentperfstates">PoFxRegisterComponentPerfStates</a>
 

 

