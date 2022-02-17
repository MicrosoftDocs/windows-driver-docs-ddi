---
UID: NF:acxpin.AcxMicArrayGeometryCreate
tech.root: audio
title: AcxMicArrayGeometryCreate
ms.date: 02/17/2022
targetos: Windows
description: The AcxMicArrayGeometryCreate function creates and initializes a new ACXMICARRAYGEOMETRY structure.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxpin.h
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
 - acxpin.h
api_name:
 - AcxMicArrayGeometryCreate
f1_keywords:
 - AcxMicArrayGeometryCreate
 - acxpin/AcxMicArrayGeometryCreate
dev_langs:
 - c++
---

## -description

The **AcxMicArrayGeometryCreate** function creates and initializes a new [ACXMICARRAYGEOMETRY](ns-acxpin-acx_mic_array_geometry.md) structure.

## -parameters

### -param AcxCircuit [in]

The ACXCIRCUIT object to which the mic array geometry will be added.

### -param Attributes [in]

Pointer to a [WDF_OBJECT_ATTRIBUTES](../wdfobject/ns-wdfobject-_wdf_object_attributes.md) structure to use when initializing the new **ACXMICARRAYGEOMETRY** structure.

### -param Config [in]

Pointer to an [ACX_MICARRAYGEOMETRY_CONFIG](ns-acxpin-acx_micarraygeometry_config.md) structure to use when initializing the new **ACXMICARRAYGEOMETRY** structure.

### -param MicArrayGeometry [out]

Pointer to the newly created **ACXMICARRAYGEOMETRY** structure.

## -returns

The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) error code.

## -remarks

Call the [ACX_MICARRAYGEOMETRY_CONFIG_INIT](nf-acxpin-acx_micarraygeometry_config_init.md) function to initialize the **ACX_MICARRAYGEOMETRY_CONFIG** structure before using it to call **AcxMicArrayGeometryCreate**.

## -see-also

- [ACXMICARRAYGEOMETRY](ns-acxpin-acx_mic_array_geometry.md)
- [WDF_OBJECT_ATTRIBUTES](../wdfobject/ns-wdfobject-_wdf_object_attributes.md)
- [ACX_MICARRAYGEOMETRY_CONFIG](ns-acxpin-acx_micarraygeometry_config.md)
- [ACX_MICARRAYGEOMETRY_CONFIG_INIT](nf-acxpin-acx_micarraygeometry_config_init.md)

TBD - Please review this topic
