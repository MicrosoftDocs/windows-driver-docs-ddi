---
UID: NS:wdm._PO_FX_PERF_STATE
title: PO_FX_PERF_STATE (wdm.h)
description: The PO_FX_PERF_STATE structure represents a performance state for a single component within a device.
tech.root: kernel
ms.date: 12/16/2022
keywords: ["PO_FX_PERF_STATE structure"]
ms.keywords: "*PPO_FX_PERF_STATE, PO_FX_PERF_STATE, PO_FX_PERF_STATE structure [Kernel-Mode Driver Architecture], PPO_FX_PERF_STATE, PPO_FX_PERF_STATE structure pointer [Kernel-Mode Driver Architecture], _PO_FX_PERF_STATE, kernel.po_fx_perf_state, wdm/PO_FX_PERF_STATE, wdm/PPO_FX_PERF_STATE"
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
targetos: Windows
req.typenames: PO_FX_PERF_STATE, *PPO_FX_PERF_STATE
f1_keywords:
 - _PO_FX_PERF_STATE
 - wdm/_PO_FX_PERF_STATE
 - PPO_FX_PERF_STATE
 - wdm/PPO_FX_PERF_STATE
 - PO_FX_PERF_STATE
 - wdm/PO_FX_PERF_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _PO_FX_PERF_STATE
 - PPO_FX_PERF_STATE
 - PO_FX_PERF_STATE
---

## -description

The **PO_FX_PERF_STATE** structure represents a performance state for a single component within a device.

## -struct-fields

### -field Value

The value of this performance state. The units are specified by the **Unit** member of the [**PO_FX_COMPONENT_PERF_SET**](./ns-wdm-_po_fx_component_perf_set.md) that contains this performance state. For example, if **Value** is 100000000 and the **Unit** member of the  **PO_FX_COMPONENT_PERF_SET** is **PoFxPerfStateUnitFrequency**, this performance state represents 100 MHz.

### -field Context

A pointer to additional context for the performance state that cannot be presented by the **Value** member. This data can be shared between the driver and the platform extension plug-in (PEP).

Using the **Context** member can hinder the visualization of performance states in Windows Performance Analyzer.

## -remarks

The **States** member of the [**PO_FX_COMPONENT_PERF_SET**](./ns-wdm-_po_fx_component_perf_set.md) structure contains an array of **PO_FX_PERF_STATE** elements.

## -see-also

[Device Performance State Management](/windows-hardware/drivers/kernel/component-level-performance-management)

[**PO_FX_COMPONENT_PERF_SET**](./ns-wdm-_po_fx_component_perf_set.md)

[PO_FX_PERF_STATE_UNIT](./ne-wdm-_po_fx_perf_state_unit.md)

[PoFxRegisterComponentPerfStates](./nf-wdm-pofxregistercomponentperfstates.md)