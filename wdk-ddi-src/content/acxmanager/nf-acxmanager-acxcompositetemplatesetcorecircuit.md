---
UID: NF:acxmanager.AcxCompositeTemplateSetCoreCircuit
tech.root: audio
title: AcxCompositeTemplateSetCoreCircuit
ms.date: 04/15/2022
targetos: Windows
description: The AcxCompositeTemplateSetCoreCircuit function set the core circuit template for the specified composite template.
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

The **AcxCompositeTemplateSetCoreCircuit** function set the core circuit template for the specified composite template.

## -parameters

### -param CompositeTemplate [in]

The composite template on which to set the core circuit template.

### -param CircuitTemplates [in]

The circuit template to set as the core on the specified *CompositeTemplate*.

TBD - It looks like the name of this parameter might contain a typo because the code only uses a single circuit template. Should this parameter be renamed **CircuitTemplate** (singular)?

## -remarks

## -see-also

- [acxmanager.h header](index.md)

TBD - Please review this topic
