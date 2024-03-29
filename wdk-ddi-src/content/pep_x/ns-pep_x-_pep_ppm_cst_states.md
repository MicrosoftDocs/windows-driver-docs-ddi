---
UID: NS:pep_x._PEP_PPM_CST_STATES
title: _PEP_PPM_CST_STATES (pep_x.h)
description: Learn how the PEP_PPM_CST_STATES structure specifies the properties of the C states (ACPI processor power states) that are supported for a processor.
old-location: kernel\pep_ppm_cst_states.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PEP_PPM_CST_STATES structure"]
ms.keywords: "*PPEP_PPM_CST_STATES, PEP_PPM_CST_STATES, PEP_PPM_CST_STATES structure [Kernel-Mode Driver Architecture], PPEP_PPM_CST_STATES, PPEP_PPM_CST_STATES structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_CST_STATES, kernel.pep_ppm_cst_states, pepfx/PEP_PPM_CST_STATES, pepfx/PPEP_PPM_CST_STATES"
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
req.typenames: PEP_PPM_CST_STATES, *PPEP_PPM_CST_STATES
f1_keywords:
 - _PEP_PPM_CST_STATES
 - pep_x/_PEP_PPM_CST_STATES
 - PPEP_PPM_CST_STATES
 - pep_x/PPEP_PPM_CST_STATES
 - PEP_PPM_CST_STATES
 - pep_x/PEP_PPM_CST_STATES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - _PEP_PPM_CST_STATES
 - PPEP_PPM_CST_STATES
 - PEP_PPM_CST_STATES
---

# _PEP_PPM_CST_STATES structure (pep_x.h)


## -description

The <b>PEP_PPM_CST_STATES</b> structure specifies the properties of the C states (ACPI processor power states) that are supported for a processor.

## -struct-fields

### -field Count

The number of elements in the <b>IdleStates</b> array.

### -field IdleStates

A pointer to an array of <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_cst_state">PEP_PPM_CST_STATE</a> structures.

## -remarks

This structure is used by the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_cst_states">PEP_NOTIFY_PPM_CST_STATES</a> notification. The contents of this structure are obtained from the _CST object that is located in the ACPI namespace for the processor.

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_cst_states">PEP_NOTIFY_PPM_CST_STATES</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_cst_state">PEP_PPM_CST_STATE</a>

