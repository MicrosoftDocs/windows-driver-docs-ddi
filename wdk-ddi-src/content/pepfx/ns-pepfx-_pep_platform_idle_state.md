---
UID: NS:pepfx._PEP_PLATFORM_IDLE_STATE
title: _PEP_PLATFORM_IDLE_STATE (pepfx.h)
description: The PEP_PLATFORM_IDLE_STATE structure specifies the properties of a platform idle state.
old-location: kernel\pep_platform_idle_state.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PEP_PLATFORM_IDLE_STATE structure"]
ms.keywords: "*PPEP_PLATFORM_IDLE_STATE, PEP_PLATFORM_IDLE_STATE, PEP_PLATFORM_IDLE_STATE structure [Kernel-Mode Driver Architecture], PPEP_PLATFORM_IDLE_STATE, PPEP_PLATFORM_IDLE_STATE structure pointer [Kernel-Mode Driver Architecture], _PEP_PLATFORM_IDLE_STATE, kernel.pep_platform_idle_state, pepfx/PEP_PLATFORM_IDLE_STATE, pepfx/PPEP_PLATFORM_IDLE_STATE"
req.header: pepfx.h
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
req.typenames: PEP_PLATFORM_IDLE_STATE, *PPEP_PLATFORM_IDLE_STATE
f1_keywords:
 - _PEP_PLATFORM_IDLE_STATE
 - pepfx/_PEP_PLATFORM_IDLE_STATE
 - PPEP_PLATFORM_IDLE_STATE
 - pepfx/PPEP_PLATFORM_IDLE_STATE
 - PEP_PLATFORM_IDLE_STATE
 - pepfx/PEP_PLATFORM_IDLE_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_PLATFORM_IDLE_STATE
---

# _PEP_PLATFORM_IDLE_STATE structure (pepfx.h)


## -description

The <b>PEP_PLATFORM_IDLE_STATE</b> structure specifies the properties of a platform idle state.

## -struct-fields

### -field InitiatingProcessor

A <b>POHANDLE</b> value that identifies the processor that initiates the transition to this platform idle state, or <b>NULL</b> if any processor can initiate the transition. If non-NULL, this handle represents the registration of the processor (as a device) with the Windows <a href="/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx).

### -field InitiatingState

The index of the processor idle state that the processor enters to initiate the platform's entry to the specified platform idle state. If the <b>IdleStates</b> array in the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_idle_states_v2">PEP_PPM_QUERY_IDLE_STATES_V2</a> structure contains N elements, the idle states are numbered 0 to N-1 in the order in which they appear in the array.

### -field Latency

The worst-case latency, in 100-nanosecond units, that the platform requires to wake from this idle state in response to a wake event.

### -field BreakEvenDuration

The minimum amount of time, specified in 100-nanosecond units, that the platform must spend in this idle state to make a transition to this state worthwhile. PoFx uses this member value as a hint to avoid switching the platform to an idle state unless the platform is likely to remain in this state for at least the amount of time specified by <b>BreakEvenDuration</b>.

### -field DependencyArrayUsed

The number of items in <b>DependencyArray</b> which were filled in by the PEP.

### -field DependencyArrayCount

The number of elements in the <b>DependencyArray</b> array. The array contains one element for each processor in the hardware platform.

### -field DependencyArray

The first element in an array of <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_processor_idle_dependency">PEP_PROCESSOR_IDLE_DEPENDENCY</a> structures. This array specifies the set of dependencies that the platform idle state has on each processor. If the platform contains N processors, the array contains N elements, and processors are numbered 0 to N-1 in the order in which they are represented in the array.

## -remarks

This structure is used in conjunction with the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_platform_state">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATE</a> notification. The <b>State</b> member of a <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_platform_state">PEP_PPM_QUERY_PLATFORM_STATE</a> structure is a <b>PEP_PLATFORM_IDLE_STATE</b> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_platform_state">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATE</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_idle_states_v2">PEP_PPM_QUERY_IDLE_STATES_V2</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_platform_state">PEP_PPM_QUERY_PLATFORM_STATE</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_processor_idle_dependency">PEP_PROCESSOR_IDLE_DEPENDENCY</a>
