---
UID: NF:acxmanager.AcxCompositeTemplateSetCoreCircuit
tech.root: audio
title: AcxCompositeTemplateSetCoreCircuit
ms.date: 12/16/2022
targetos: Windows
description: The AcxCompositeTemplateSetCoreCircuit function sets the core circuit template for the specified composite template.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxmanager.h
req.idl: 
req.include-header: 
req.irql: <= DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - acxmanager.h
api_name:
 - AcxCompositeTemplateSetCoreCircuit
f1_keywords:
 - AcxCompositeTemplateSetCoreCircuit
 - acxmanager/AcxCompositeTemplateSetCoreCircuit
dev_langs:
 - c++
---

## -description

The **AcxCompositeTemplateSetCoreCircuit** function sets the core circuit template for the specified composite template.

## -parameters

### -param CompositeTemplate [in]

The composite template on which to set the core circuit template.

### -param CircuitTemplates [in]

The circuit template to set as the core on the specified *CompositeTemplate*. This parameter is mistakenly named in the plural. It actually represents the single core circuit template.

## -remarks

The core circuit gives the identity to the composite endpoint. If this circuit is not present, ACX manager doesn't start the endpoint building process.

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxmanager.h header](index.md)
