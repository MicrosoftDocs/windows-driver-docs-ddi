---
UID: NS:pep_x._PEP_PROCESSOR_PARK_STATE
title: _PEP_PROCESSOR_PARK_STATE (pep_x.h)
description: The PEP_PROCESSOR_PARK_STATE structure describes the parking state for a single processor.
old-location: kernel\pep_processor_park_state.htm
tech.root: kernel
ms.assetid: 7F0BD23A-A375-43D5-B106-31E206DB6EC4
ms.date: 04/30/2018
keywords: ["PEP_PROCESSOR_PARK_STATE structure"]
ms.keywords: "*PPEP_PROCESSOR_PARK_STATE, PEP_PROCESSOR_PARK_STATE, PEP_PROCESSOR_PARK_STATE structure [Kernel-Mode Driver Architecture], PPEP_PROCESSOR_PARK_STATE, PPEP_PROCESSOR_PARK_STATE structure pointer [Kernel-Mode Driver Architecture], _PEP_PROCESSOR_PARK_STATE, kernel.pep_processor_park_state, pepfx/PEP_PROCESSOR_PARK_STATE, pepfx/PPEP_PROCESSOR_PARK_STATE"
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
req.typenames: PEP_PROCESSOR_PARK_STATE, *PPEP_PROCESSOR_PARK_STATE
f1_keywords:
 - _PEP_PROCESSOR_PARK_STATE
 - pep_x/_PEP_PROCESSOR_PARK_STATE
 - PPEP_PROCESSOR_PARK_STATE
 - pep_x/PPEP_PROCESSOR_PARK_STATE
 - PEP_PROCESSOR_PARK_STATE
 - pep_x/PEP_PROCESSOR_PARK_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_PROCESSOR_PARK_STATE
---

# _PEP_PROCESSOR_PARK_STATE structure (pep_x.h)


## -description

The <b>PEP_PROCESSOR_PARK_STATE</b> structure describes the parking state for a single processor.

## -struct-fields

### -field Processor

Specifies the <b>PEPHANDLE</b> associated with this processor.

### -field Parked

Specifies whether or not this processor is parked.

### -field Reserved

This member is reserved and should be set to zero.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">PEP_NOTIFY_PPM_PARK_MASK notification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_park_mask">PEP_PPM_PARK_MASK</a>

