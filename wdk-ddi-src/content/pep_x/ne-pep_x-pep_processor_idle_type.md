---
UID: NE:pep_x.__unnamed_enum_0
title: PEP_PROCESSOR_IDLE_TYPE (pep_x.h)
description: The PEP_PROCESSOR_IDLE_TYPE enumeration indicates whether idle constraints apply to just the current processor or to all processors in the hardware platform.
old-location: kernel\pep_processor_idle_type.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PEP_PROCESSOR_IDLE_TYPE enumeration"]
ms.keywords: "*PPEP_PROCESSOR_IDLE_TYPE, PEP_PROCESSOR_IDLE_TYPE, PEP_PROCESSOR_IDLE_TYPE enumeration [Kernel-Mode Driver Architecture], PepIdleTypeMax, PepIdleTypePlatform, PepIdleTypeProcessor, kernel.pep_processor_idle_type, pep_x/PEP_PROCESSOR_IDLE_TYPE, pep_x/PepIdleTypeMax, pep_x/PepIdleTypePlatform, pep_x/PepIdleTypeProcessor"
req.header: pep_x.h
req.include-header: Pepfx.h
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
req.typenames: PEP_PROCESSOR_IDLE_TYPE, *PPEP_PROCESSOR_IDLE_TYPE
f1_keywords:
 - PPEP_PROCESSOR_IDLE_TYPE
 - pep_x/PPEP_PROCESSOR_IDLE_TYPE
 - PEP_PROCESSOR_IDLE_TYPE
 - pep_x/PEP_PROCESSOR_IDLE_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pep_x.h
api_name:
 - PEP_PROCESSOR_IDLE_TYPE
---

# PEP_PROCESSOR_IDLE_TYPE enumeration


## -description

The <b>PEP_PROCESSOR_IDLE_TYPE</b> enumeration indicates whether idle constraints apply to just the current processor or to all processors in the hardware platform.

## -enum-fields

### -field PepIdleTypeProcessor

Apply to current processor.

### -field PepIdleTypePlatform

Apply to all processors.

### -field PepIdleTypeMax

Reserved for use by operating system.

## -remarks

The <b>Type</b> member of the <a href="/windows-hardware/drivers/ddi/pep_x/ns-pep_x-_pep_processor_idle_constraints">PEP_PROCESSOR_IDLE_CONSTRAINTS</a> structure is a <b>PEP_PROCESSOR_IDLE_TYPE</b> enumeration value.

## -see-also

<a href="/windows-hardware/drivers/ddi/pep_x/ns-pep_x-_pep_processor_idle_constraints">PEP_PROCESSOR_IDLE_CONSTRAINTS</a>
