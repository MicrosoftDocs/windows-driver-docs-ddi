---
UID: NF:acxmanager.AcxCompositeTemplateSetCoreCircuit
tech.root: audio
title: AcxCompositeTemplateSetCoreCircuit
ms.date: 09/08/2022
targetos: Windows
description: The AcxCompositeTemplateSetCoreCircuit function sets the core circuit template for the specified composite template.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxmanager.h
req.idl: 
req.include-header: 
req.irql: 
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

The circuit template to set as the core on the specified *CompositeTemplate*.

## -remarks

The core circuit gives the identity to the composite endpoint. If this circuit is not present, ACX manager doesn't start the endpoint building process.

## -see-also

- [acxmanager.h header](index.md)
