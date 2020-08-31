---
UID: NS:pepfx._PEP_PPM_QUERY_DISCRETE_PERF_STATES
title: _PEP_PPM_QUERY_DISCRETE_PERF_STATES (pepfx.h)
description: Used in the PEP_NOTIFY_PPM_QUERY_DISCRETE_PERF_STATES notification that stores the list of discrete performance states that PEP supports, if the PEP_NOTIFY_PPM_QUERY_CAPABILITIES notification indicates support for discrete performance states. .
old-location: kernel\pep_ppm_query_discrete_perf_states.htm
tech.root: kernel
ms.assetid: 506b3d8e-4aba-4e70-a6db-52a52d717c6b
ms.date: 04/30/2018
keywords: ["PEP_PPM_QUERY_DISCRETE_PERF_STATES structure"]
ms.keywords: "*PPEP_PPM_QUERY_DISCRETE_PERF_STATES, PEP_PPM_QUERY_DISCRETE_PERF_STATES, PEP_PPM_QUERY_DISCRETE_PERF_STATES structure [Kernel-Mode Driver Architecture], PPEP_PPM_QUERY_DISCRETE_PERF_STATES, PPEP_PPM_QUERY_DISCRETE_PERF_STATES structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_QUERY_DISCRETE_PERF_STATES, kernel.pep_ppm_query_discrete_perf_states, pepfx/PEP_PPM_QUERY_DISCRETE_PERF_STATES, pepfx/PPEP_PPM_QUERY_DISCRETE_PERF_STATES"
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
req.typenames: PEP_PPM_QUERY_DISCRETE_PERF_STATES, *PPEP_PPM_QUERY_DISCRETE_PERF_STATES
f1_keywords:
 - _PEP_PPM_QUERY_DISCRETE_PERF_STATES
 - pepfx/_PEP_PPM_QUERY_DISCRETE_PERF_STATES
 - PPEP_PPM_QUERY_DISCRETE_PERF_STATES
 - pepfx/PPEP_PPM_QUERY_DISCRETE_PERF_STATES
 - PEP_PPM_QUERY_DISCRETE_PERF_STATES
 - pepfx/PEP_PPM_QUERY_DISCRETE_PERF_STATES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Pepfx.h
api_name:
 - PEP_PPM_QUERY_DISCRETE_PERF_STATES
---

# _PEP_PPM_QUERY_DISCRETE_PERF_STATES structure


## -description

Used in the <b>PEP_NOTIFY_PPM_QUERY_DISCRETE_PERF_STATES</b> notification that stores the list of discrete performance states that PEP supports, if the <b>PEP_NOTIFY_PPM_QUERY_CAPABILITIES</b> notification indicates support for discrete performance states.

## -struct-fields

### -field Count

On input, the size of the array pointed to by <i>States</i>.

### -field States

On output, an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_processor_perf_state">PEP_PROCESSOR_PERF_STATE</a> structures that indicates performance states that is filled by  PEP.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_capabilities">PEP_PPM_QUERY_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Processor power management (PPM) notifications</a>

