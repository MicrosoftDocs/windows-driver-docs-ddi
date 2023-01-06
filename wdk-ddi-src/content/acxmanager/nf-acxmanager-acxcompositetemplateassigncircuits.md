---
UID: NF:acxmanager.AcxCompositeTemplateAssignCircuits
tech.root: audio
title: AcxCompositeTemplateAssignCircuits
ms.date: 04/27/2022
targetos: Windows
description: The AcxCompositeTemplateAssignCircuits function adds an array of circuit templates to the specified composite template.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxmanager.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
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
 - AcxCompositeTemplateAssignCircuits
f1_keywords:
 - AcxCompositeTemplateAssignCircuits
 - acxmanager/AcxCompositeTemplateAssignCircuits
dev_langs:
 - c++
---

## -description

The **AcxCompositeTemplateAssignCircuits** function adds an array of circuit templates to the specified composite template.

## -parameters

### -param CompositeTemplate [in]

The composite template to which the circuit templates are added.

### -param CircuitTemplates [in, reads(CircuitTemplatesCount)]

A pointer to an array of **ACXCIRCUITTEMPLATE** objects to add to the specified *CompositeTemplate*.

### -param CircuitTemplatesCount [in]

The number of **ACXCIRCUITTEMPLATE** objects in the *CircuitTemplates* array.

## -returns

The method returns **STATUS_SUCCESS** if the operation succeeds. Otherwise, this method might return an appropriate **[NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values)** error code.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [AcxCircuitTemplateCreate](nf-acxmanager-acxcircuittemplatecreate.md)
- [AcxCompositeTemplateCreate](nf-acxmanager-acxcompositetemplatecreate.md)
- [acxmanager.h header](index.md)
