---
UID: NS:pep_x._PEP_COMPONENT_PERF_INFO
title: _PEP_COMPONENT_PERF_INFO (pep_x.h)
description: Learn how the PEP_COMPONENT_PERF_INFO structure describes the performance states (P-states) of a component.
old-location: kernel\pep_component_perf_info.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PEP_COMPONENT_PERF_INFO structure"]
ms.keywords: "*PPEP_COMPONENT_PERF_INFO, PEP_COMPONENT_PERF_INFO, PEP_COMPONENT_PERF_INFO structure [Kernel-Mode Driver Architecture], PPEP_COMPONENT_PERF_INFO, PPEP_COMPONENT_PERF_INFO structure pointer [Kernel-Mode Driver Architecture], _PEP_COMPONENT_PERF_INFO, kernel.pep_component_perf_info, pepfx/PEP_COMPONENT_PERF_INFO, pepfx/PPEP_COMPONENT_PERF_INFO"
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
targetos: Windows
req.typenames: PEP_COMPONENT_PERF_INFO, *PPEP_COMPONENT_PERF_INFO
f1_keywords:
 - _PEP_COMPONENT_PERF_INFO
 - pep_x/_PEP_COMPONENT_PERF_INFO
 - PPEP_COMPONENT_PERF_INFO
 - pep_x/PPEP_COMPONENT_PERF_INFO
 - PEP_COMPONENT_PERF_INFO
 - pep_x/PEP_COMPONENT_PERF_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - _PEP_COMPONENT_PERF_INFO
 - PPEP_COMPONENT_PERF_INFO
 - PEP_COMPONENT_PERF_INFO
---

# _PEP_COMPONENT_PERF_INFO structure (pep_x.h)


## -description

The <b>PEP_COMPONENT_PERF_INFO</b> structure describes the performance states (P-states) of a component.

## -struct-fields

### -field SetCount

The number of elements in the <b>PerfStateSets</b> array.

### -field PerfStateSets

The first element in an array of <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_component_perf_set">PEP_COMPONENT_PERF_SET</a> structures. Each array element describes a P-state of the component. If the array contains more than one element, the additional elements immediately follow the end of the <b>PEP_COMPONENT_PERF_INFO</b> structure.

## -remarks

This structure is used in conjunction with the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_component_perf_states">PEP_DPM_REGISTER_COMPONENT_PERF_STATES</a> notification. The <b>PerfStateSets</b> member of the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_component_perf_states">PEP_REGISTER_COMPONENT_PERF_STATES</a> structure is a <b>PEP_COMPONENT_PERF_INFO</b> structure.

The <b>PEP_COMPONENT_PERF_INFO</b> structure contains input values that are supplied by the Windows <a href="/windows-hardware/drivers/ddi/_kernel/#device-power-management">power management framework</a> (PoFx). The platform extension plug-in (PEP) must not write to this structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_component_perf_info">PEP_COMPONENT_PERF_INFO</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_component_perf_set">PEP_COMPONENT_PERF_SET</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_component_perf_states">PEP_DPM_REGISTER_COMPONENT_PERF_STATES</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_component_perf_states">PEP_REGISTER_COMPONENT_PERF_STATES</a>

