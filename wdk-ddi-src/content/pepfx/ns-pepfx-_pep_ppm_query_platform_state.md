---
UID: NS:pepfx._PEP_PPM_QUERY_PLATFORM_STATE
title: _PEP_PPM_QUERY_PLATFORM_STATE (pepfx.h)
description: The PEP_PPM_QUERY_PLATFORM_STATE structure contains information about a platform idle state.
old-location: kernel\pep_ppm_query_platform_state.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PEP_PPM_QUERY_PLATFORM_STATE structure"]
ms.keywords: "*PPEP_PPM_QUERY_PLATFORM_STATE, PEP_PPM_QUERY_PLATFORM_STATE, PEP_PPM_QUERY_PLATFORM_STATE structure [Kernel-Mode Driver Architecture], PPEP_PPM_QUERY_PLATFORM_STATE, PPEP_PPM_QUERY_PLATFORM_STATE structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_QUERY_PLATFORM_STATE, kernel.pep_ppm_query_platform_state, pepfx/PEP_PPM_QUERY_PLATFORM_STATE, pepfx/PPEP_PPM_QUERY_PLATFORM_STATE"
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
req.typenames: PEP_PPM_QUERY_PLATFORM_STATE, *PPEP_PPM_QUERY_PLATFORM_STATE
f1_keywords:
 - _PEP_PPM_QUERY_PLATFORM_STATE
 - pepfx/_PEP_PPM_QUERY_PLATFORM_STATE
 - PPEP_PPM_QUERY_PLATFORM_STATE
 - pepfx/PPEP_PPM_QUERY_PLATFORM_STATE
 - PEP_PPM_QUERY_PLATFORM_STATE
 - pepfx/PEP_PPM_QUERY_PLATFORM_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_PPM_QUERY_PLATFORM_STATE
---

# _PEP_PPM_QUERY_PLATFORM_STATE structure (pepfx.h)


## -description

The <b>PEP_PPM_QUERY_PLATFORM_STATE</b> structure contains information about a platform idle state.

## -struct-fields

### -field StateIndex

[in] The index of this platform idle state. If the hardware platform supports N platform idle states, the states are numbered 0 to N-1. The Windows <a href="/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx) previously sent a <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_platform_states">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a> notification to the platform extension plug-in (PEP) to determine the number of supported platform idle states.

### -field State

[out] A <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_platform_idle_state">PEP_PLATFORM_IDLE_STATE</a> structure that describes the platform idle state.

## -remarks

This structure is used by the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_platform_state">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATE</a> notification. The <b>StateIndex</b> member of the <b>PEP_PPM_QUERY_PLATFORM_STATE</b> structure contains an input value that is supplied by the Windows <a href="/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx) when this notification is sent to the PEP. The <b>State</b> member contains an output value that the PEP writes to the structure in response to the notification.

The buffer that PoFx allocates to hold the <b>PEP_PPM_QUERY_PLATFORM_STATE</b> structure is guaranteed to be large enough to contain this structure plus any elements of the <b>State.DependencyArray</b> array that follow this structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_platform_state">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATE</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_platform_states">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_platform_idle_state">PEP_PLATFORM_IDLE_STATE</a>
