---
UID: NS:pep_x._PEP_COMPONENT_PERF_STATE_REQUEST
title: _PEP_COMPONENT_PERF_STATE_REQUEST (pep_x.h)
description: Learn how the PEP_COMPONENT_PERF_STATE_REQUEST structure specifies a performance state (P-state) set and a new performance level to assign to this set.
old-location: kernel\pep_component_perf_state_request.htm
tech.root: kernel
ms.date: 08/05/2022
keywords: ["PEP_COMPONENT_PERF_STATE_REQUEST structure"]
ms.keywords: "*PPEP_COMPONENT_PERF_STATE_REQUEST, PEP_COMPONENT_PERF_STATE_REQUEST, PEP_COMPONENT_PERF_STATE_REQUEST structure [Kernel-Mode Driver Architecture], PPEP_COMPONENT_PERF_STATE_REQUEST, PPEP_COMPONENT_PERF_STATE_REQUEST structure pointer [Kernel-Mode Driver Architecture], _PEP_COMPONENT_PERF_STATE_REQUEST, kernel.pep_component_perf_state_request, pepfx/PEP_COMPONENT_PERF_STATE_REQUEST, pepfx/PPEP_COMPONENT_PERF_STATE_REQUEST"
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
req.typenames: PEP_COMPONENT_PERF_STATE_REQUEST, *PPEP_COMPONENT_PERF_STATE_REQUEST
f1_keywords:
 - _PEP_COMPONENT_PERF_STATE_REQUEST
 - pep_x/_PEP_COMPONENT_PERF_STATE_REQUEST
 - PPEP_COMPONENT_PERF_STATE_REQUEST
 - pep_x/PPEP_COMPONENT_PERF_STATE_REQUEST
 - PEP_COMPONENT_PERF_STATE_REQUEST
 - pep_x/PEP_COMPONENT_PERF_STATE_REQUEST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - _PEP_COMPONENT_PERF_STATE_REQUEST
 - PPEP_COMPONENT_PERF_STATE_REQUEST
 - PEP_COMPONENT_PERF_STATE_REQUEST
---

# _PEP_COMPONENT_PERF_STATE_REQUEST structure (pep_x.h)

## -description

The **PEP_COMPONENT_PERF_STATE_REQUEST** structure specifies a performance state (P-state) set and a new performance level to assign to this set.

## -struct-fields

### -field Set

The index of the P-state set to which to assign the new performance level. If N is the number of P-state sets specified for this component, P-state set indexes range from 0 to N–1. The PEP previously specified the number of P-state sets in response to a [PEP_DPM_QUERY_COMPONENT_PERF_CAPABILITIES](../pepfx/ns-pepfx-_pep_query_component_perf_capabilities.md) notification.

### -field StateIndex

The index of the discrete value to use as the new performance level. This member is used if the performance level for this P-state set is expressed as an index into an array of discrete values. The PEP previously supplied this array of discrete values in response to a [PEP_DPM_QUERY_COMPONENT_PERF_STATES](../pepfx/ns-pepfx-_pep_query_component_perf_states.md) notification.

### -field StateValue

The value to use as the new performance level. This member is used if the performance level for this P-state set is expressed as a value in a continuous range of possible values. The PEP previously supplied this range in response to a [PEP_DPM_QUERY_COMPONENT_PERF_SET](../pepfx/ns-pepfx-_pep_query_component_perf_set.md) notification.

## -remarks

The unnamed union contains a value that indicates the new performance level that has been selected for this P-state set.

The **PerfRequests** member of the [PEP_REQUEST_COMPONENT_PERF_STATE](../pepfx/ns-pepfx-_pep_request_component_perf_state.md) structure is a pointer to an array of **PEP_COMPONENT_PERF_STATE_REQUEST** structures.

## -see-also

- [PEP_REQUEST_COMPONENT_PERF_STATE](../pepfx/ns-pepfx-_pep_request_component_perf_state.md)
