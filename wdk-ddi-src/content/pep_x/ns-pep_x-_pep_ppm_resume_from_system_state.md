---
UID: NS:pep_x._PEP_PPM_RESUME_FROM_SYSTEM_STATE
title: _PEP_PPM_RESUME_FROM_SYSTEM_STATE (pep_x.h)
description: Learn how this method is used by the PEP_NOTIFY_PPM_RESUME_FROM_SYSTEM_STATE notification that notifies the PEP that the system has just resumed from a system power state.
old-location: kernel\pep_ppm_resume_from_system_state.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PEP_PPM_RESUME_FROM_SYSTEM_STATE structure"]
ms.keywords: "*PPEP_PPM_RESUME_FROM_SYSTEM_STATE, PEP_PPM_RESUME_FROM_SYSTEM_STATE, PEP_PPM_RESUME_FROM_SYSTEM_STATE structure [Kernel-Mode Driver Architecture], _PEP_PPM_RESUME_FROM_SYSTEM_STATE, kernel.pep_ppm_resume_from_system_state, pepfx/PEP_PPM_RESUME_FROM_SYSTEM_STATE"
req.header: pep_x.h
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
req.typenames: PEP_PPM_RESUME_FROM_SYSTEM_STATE, *PPEP_PPM_RESUME_FROM_SYSTEM_STATE
f1_keywords:
 - _PEP_PPM_RESUME_FROM_SYSTEM_STATE
 - pep_x/_PEP_PPM_RESUME_FROM_SYSTEM_STATE
 - PPEP_PPM_RESUME_FROM_SYSTEM_STATE
 - pep_x/PPEP_PPM_RESUME_FROM_SYSTEM_STATE
 - PEP_PPM_RESUME_FROM_SYSTEM_STATE
 - pep_x/PEP_PPM_RESUME_FROM_SYSTEM_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Pepfx.h
api_name:
 - _PEP_PPM_RESUME_FROM_SYSTEM_STATE
 - PPEP_PPM_RESUME_FROM_SYSTEM_STATE
 - PEP_PPM_RESUME_FROM_SYSTEM_STATE
---

# _PEP_PPM_RESUME_FROM_SYSTEM_STATE structure (pep_x.h)


## -description

Used by the <b>PEP_NOTIFY_PPM_RESUME_FROM_SYSTEM_STATE</b> notification that notifies the PEP that the system has just resumed from a system power state.

## -struct-fields

### -field TargetState

On input, a <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_system_power_state">SYSTEM_POWER_STATE</a>-type value that indicates the power state that the system is entering.

## -see-also

<a href="/windows-hardware/drivers/ddi/index">Processor power management (PPM) notifications</a>

