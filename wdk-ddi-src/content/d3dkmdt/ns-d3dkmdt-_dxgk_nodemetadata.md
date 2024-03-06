---
UID: NS:d3dkmdt._DXGK_NODEMETADATA
title: DXGK_NODEMETADATA
description: Learn more about the DXGK_NODEMETADATA structure.
tech.root: display
ms.date: 05/22/2023
keywords: ["DXGK_NODEMETADATA structure"]
ms.keywords: _DXGK_NODEMETADATA, DXGK_NODEMETADATA, DXGKARG_GETNODEMETADATA
req.header: d3dkmdt.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGK_NODEMETADATA
targetos: Windows
f1_keywords:
 - _DXGK_NODEMETADATA
 - d3dkmdt/_DXGK_NODEMETADATA
 - DXGK_NODEMETADATA
 - d3dkmdt/DXGK_NODEMETADATA
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _DXGK_NODEMETADATA
 - DXGK_NODEMETADATA
---

# DXGK_NODEMETADATA structure

## -description

The **DXGK_NODEMETADATA** structure describes an engine on a GPU node.

## -struct-fields

### -field EngineType

A [**DXGK_ENGINE_TYPE**](ne-d3dkmdt-dxgk_engine_type.md) enumeration value that indicates the engine type.

### -field FriendlyName

A NULL-terminated string that represents a descriptive friendly name for a particular engine.

The display miniport driver (KMD) must provide a value for this member if **EngineType** is **DXGK_ENGINE_TYPE_OTHER**. Otherwise, KMD should set this value to be an empty, NULL-terminated string.

This member doesn't need to be localized and can be represented with an EN-US string value.

### -field Flags

A bit field of [**DXGK_NODEMETADATA_FLAGS**](ns-d3dkmdt-_dxgk_nodemetadata_flags.md) values that describe the engine's metadata. This member is available starting in WDDM 2.2.

### -field Reserved

Reserved for system use.

### -field GpuMmuSupported

A Boolean value that indicates whether the graphics engines of the node support the [GpuMmu model](/windows-hardware/drivers/display/gpummu-model). Available starting in WDDM 2.0.

### -field IoMmuSupported

A Boolean value that indicates whether the graphics engines of the node support the [IoMmu model](/windows-hardware/drivers/display/iommu-model). Available starting in WDDM 2.0.

## -remarks

This structure is used to define the structure **DXGKARG_GETNODEMETADATA**, in the call to KMD's [**DXGKDDI_GETNODEMETADATA**](../d3dkmddi/nc-d3dkmddi-dxgkddi_getnodemetadata.md).

For more information on how to use this structure, see [Enumerating GPU engine capabilities](/windows-hardware/drivers/display/enumerating-gpu-nodes).

## -see-also

[**DXGK_ENGINE_TYPE**](ne-d3dkmdt-dxgk_engine_type.md)

[**DXGK_NODEMETADATA_FLAGS**](ns-d3dkmdt-_dxgk_nodemetadata_flags.md)

[**DXGKDDI_GETNODEMETADATA**](../d3dkmddi/nc-d3dkmddi-dxgkddi_getnodemetadata.md)
