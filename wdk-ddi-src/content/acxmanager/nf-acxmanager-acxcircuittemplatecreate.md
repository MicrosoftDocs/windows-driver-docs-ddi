---
UID: NF:acxmanager.AcxCircuitTemplateCreate
tech.root: audio
title: AcxCircuitTemplateCreate
ms.date: 04/27/2022
targetos: Windows
description: The AcxCircuitTemplateCreate function is used to create a circuit template for use by the audio class extension (ACX) manager.
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
 - AcxCircuitTemplateCreate
f1_keywords:
 - AcxCircuitTemplateCreate
 - acxmanager/AcxCircuitTemplateCreate
dev_langs:
 - c++
---

## -description

The **AcxCircuitTemplateCreate** function is used to create a circuit template for use by the audio class extension (ACX) manager.

## -parameters

### -param Driver [in]

A **WDFDRIVER** object, described in [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects), that will be associated with the circuit template.

### -param Attributes [in]

A pointer to the [WDF_OBJECT_ATTRIBUTES](../wdfobject/ns-wdfobject-_wdf_object_attributes.md) structure to use when creating the circuit template.

### -param Config [in]

A pointer to an [ACX_CIRCUIT_TEMPLATE_CONFIG](ns-acxmanager-acx_circuit_template_config.md) structure to use when creating the circuit template.

### -param Template [out]

A pointer to the newly created circuit template object.

## -returns

The method returns **STATUS_SUCCESS** if the operation succeeds. Otherwise, this method might return an appropriate **[NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values)** error code.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)
- [WDF_OBJECT_ATTRIBUTES](../wdfobject/ns-wdfobject-_wdf_object_attributes.md)
- [ACX_CIRCUIT_TEMPLATE_CONFIG](ns-acxmanager-acx_circuit_template_config.md)
- [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values)
- [acxmanager.h header](index.md)

