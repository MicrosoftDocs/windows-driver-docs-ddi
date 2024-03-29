---
UID: NE:pep_x._PEP_PERF_STATE_TYPE
title: _PEP_PERF_STATE_TYPE (pep_x.h)
description: Learn how the PEP_PERF_STATE_TYPE enumeration indicates the type of performance information that is specified for a performance state (P-state) of a component.
old-location: kernel\pep_perf_state_type.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PEP_PERF_STATE_TYPE enumeration"]
ms.keywords: "*PPEP_PERF_STATE_TYPE, PEP_PERF_STATE_TYPE, PEP_PERF_STATE_TYPE enumeration [Kernel-Mode Driver Architecture], PepPerfStateTypeDiscrete, PepPerfStateTypeMax, PepPerfStateTypeRange, _PEP_PERF_STATE_TYPE, kernel.pep_perf_state_type, pepfx/PEP_PERF_STATE_TYPE, pepfx/PepPerfStateTypeDiscrete, pepfx/PepPerfStateTypeMax, pepfx/PepPerfStateTypeRange"
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
req.typenames: PEP_PERF_STATE_TYPE, *PPEP_PERF_STATE_TYPE
f1_keywords:
 - _PEP_PERF_STATE_TYPE
 - pep_x/_PEP_PERF_STATE_TYPE
 - PPEP_PERF_STATE_TYPE
 - pep_x/PPEP_PERF_STATE_TYPE
 - PEP_PERF_STATE_TYPE
 - pep_x/PEP_PERF_STATE_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - _PEP_PERF_STATE_TYPE
 - PPEP_PERF_STATE_TYPE
 - PEP_PERF_STATE_TYPE
---

# _PEP_PERF_STATE_TYPE enumeration (pep_x.h)


## -description

The <b>PEP_PERF_STATE_TYPE</b> enumeration indicates the type of performance information that is specified for a performance state (P-state) of a component.

## -enum-fields

### -field PepPerfStateTypeDiscrete

The performance information is specified as a set of discrete values.

### -field PepPerfStateTypeRange

The performance information is specified as a range of values.

### -field PepPerfStateTypeMax

Reserved for use by operating system.

## -remarks

The <b>Type</b> member of the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_component_perf_set">PEP_COMPONENT_PERF_SET</a> structure is a <b>PEP_PERF_STATE_TYPE</b> enumeration value.

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_component_perf_set">PEP_COMPONENT_PERF_SET</a>

