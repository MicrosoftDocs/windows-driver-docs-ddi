---
UID: NS:pep_x._PEP_PPM_PLATFORM_STATE_RESIDENCY
title: _PEP_PPM_PLATFORM_STATE_RESIDENCY (pep_x.h)
description: Learn how the PEP_PPM_PLATFORM_STATE_RESIDENCY structure specifies the accumulated residency time and transition count for a particular platform idle state.
old-location: kernel\pep_ppm_platform_state_residency.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PEP_PPM_PLATFORM_STATE_RESIDENCY structure"]
ms.keywords: "*PPEP_PPM_PLATFORM_STATE_RESIDENCY, PEP_PPM_PLATFORM_STATE_RESIDENCY, PEP_PPM_PLATFORM_STATE_RESIDENCY structure [Kernel-Mode Driver Architecture], PPEP_PPM_PLATFORM_STATE_RESIDENCY, PPEP_PPM_PLATFORM_STATE_RESIDENCY structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_PLATFORM_STATE_RESIDENCY, kernel.pep_ppm_platform_state_residency, pepfx/PEP_PPM_PLATFORM_STATE_RESIDENCY, pepfx/PPEP_PPM_PLATFORM_STATE_RESIDENCY"
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
req.typenames: PEP_PPM_PLATFORM_STATE_RESIDENCY, *PPEP_PPM_PLATFORM_STATE_RESIDENCY
f1_keywords:
 - _PEP_PPM_PLATFORM_STATE_RESIDENCY
 - pep_x/_PEP_PPM_PLATFORM_STATE_RESIDENCY
 - PPEP_PPM_PLATFORM_STATE_RESIDENCY
 - pep_x/PPEP_PPM_PLATFORM_STATE_RESIDENCY
 - PEP_PPM_PLATFORM_STATE_RESIDENCY
 - pep_x/PEP_PPM_PLATFORM_STATE_RESIDENCY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - _PEP_PPM_PLATFORM_STATE_RESIDENCY
 - PPEP_PPM_PLATFORM_STATE_RESIDENCY
 - PEP_PPM_PLATFORM_STATE_RESIDENCY
---

# _PEP_PPM_PLATFORM_STATE_RESIDENCY structure (pep_x.h)


## -description

The <b>PEP_PPM_PLATFORM_STATE_RESIDENCY</b> structure specifies the accumulated residency time and transition count for a particular platform idle state.

## -struct-fields

### -field Residency

The accumulated residency time, in 100-nanosecond units. This is the total amount of time that the hardware platform has spent in this idle state since system startup.

### -field TransitionCount

The total number of times that the platform has entered this idle state since system startup.

## -remarks

The <b>States</b> member of the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_platform_state_residencies">PEP_PPM_PLATFORM_STATE_RESIDENCIES</a> structure is a pointer to an array of <b>PEP_PPM_PLATFORM_STATE_RESIDENCY</b> structures.

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_platform_state_residencies">PEP_PPM_PLATFORM_STATE_RESIDENCIES</a>

