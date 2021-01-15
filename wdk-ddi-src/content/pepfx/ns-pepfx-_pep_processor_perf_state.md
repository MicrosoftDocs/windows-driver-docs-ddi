---
UID: NS:pepfx._PEP_PROCESSOR_PERF_STATE
title: _PEP_PROCESSOR_PERF_STATE (pepfx.h)
description: Use in the PEP_NOTIFY_PPM_QUERY_DISCRETE_PERF_STATES  notification. This structure describes the properties of a single performance state.  .
old-location: kernel\pep_processor_perf_state.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PEP_PROCESSOR_PERF_STATE structure"]
ms.keywords: "*PPEP_PROCESSOR_PERF_STATE, PEP_PROCESSOR_PERF_STATE, PEP_PROCESSOR_PERF_STATE structure [Kernel-Mode Driver Architecture], _PEP_PROCESSOR_PERF_STATE, kernel.pep_processor_perf_state, pepfx/PEP_PROCESSOR_PERF_STATE"
req.header: pepfx.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
req.typenames: PEP_PROCESSOR_PERF_STATE, *PPEP_PROCESSOR_PERF_STATE
f1_keywords:
 - _PEP_PROCESSOR_PERF_STATE
 - pepfx/_PEP_PROCESSOR_PERF_STATE
 - PPEP_PROCESSOR_PERF_STATE
 - pepfx/PPEP_PROCESSOR_PERF_STATE
 - PEP_PROCESSOR_PERF_STATE
 - pepfx/PEP_PROCESSOR_PERF_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Pepfx.h
api_name:
 - _PEP_PROCESSOR_PERF_STATE
 - PPEP_PROCESSOR_PERF_STATE
 - PEP_PROCESSOR_PERF_STATE
---

# _PEP_PROCESSOR_PERF_STATE structure (pepfx.h)


## -description

Use in the <b>PEP_NOTIFY_PPM_QUERY_DISCRETE_PERF_STATES</b>  notification. This structure describes the properties of a single performance state.

## -struct-fields

### -field Performance

On output, the performance level (on the scale returned by the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_query_component_perf_capabilities">PEP_QUERY_COMPONENT_PERF_CAPABILITIES</a> notification) of this performance state.

### -field Frequency

On output, the frequency (in MHz) of this performance state.

### -field Reserved

Reserved.

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_discrete_perf_states">PEP_PPM_QUERY_DISCRETE_PERF_STATES</a>



<a href="/windows-hardware/drivers/ddi/index">Processor power management (PPM) notifications</a>

