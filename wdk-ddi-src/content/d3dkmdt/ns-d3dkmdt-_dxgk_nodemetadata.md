---
UID: NS:d3dkmdt._DXGK_NODEMETADATA
title: _DXGK_NODEMETADATA
description: Contains the engine type and friendly name of an engine on a GPU node.
tech.root: display
ms.assetid: eddf63a3-ba27-4a75-b093-cc0de866eb3c
ms.author: windowsdriverdev
ms.date: 02/01/2019
keywords: ["DXGK_NODEMETADATA structure"]
ms.prod: windows-hardware
ms.technology: windows-devices
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
product:
 - Windows
---

# _DXGK_NODEMETADATA structure


## -description

Contains the engine type and friendly name of an engine on a GPU node

## -struct-fields

### -field EngineType

The engine type, specified as a value in the [DXGK_ENGINE_TYPE](ne-d3dkmdt-dxgk_engine_type.md) enumeration.

### -field FriendlyName

A NULL-terminated string that represents a descriptive friendly name for a particular engine.

The display miniport driver must provide a value for this member if the engine type is **DXGK_ENGINE_TYPE_OTHER**. Otherwise, this value should not be set and should be an empty, NULL-terminated string.

This member does not need to be localized and can be represented with an EN-US string value.

### -field Flags

Supported starting in WDDM 2.2. A [DXGK_NODEMETADATA_FLAGS](ns-d3dkmdt-_dxgk_nodemetadata_flags.md) enumeration value.

### -field Reserved

Reserved for system use and must have a value of 0.

### -field GpuMmuSupported

Indicates whether the graphics engines of the node support the GpuMmu model

### -field IoMmuSupported

 
Indicates whether the graphics engines of the node support the IoMmu model.

## -remarks

This structure is also used to define the structure DXGKARG_GETNODEMETADATA, in the call to [DXGKDDI_GETNODEMETADATA](../d3dkmddi/nc-d3dkmddi-dxgkddi_getnodemetadata.md).

For more information on how to use this structure, see [Enumerating GPU engine capabilities](https://docs.microsoft.com/windows-hardware/drivers/display/enumerating-gpu-nodes).

## -see-also

[DXGK_ENGINE_TYPE](ne-d3dkmdt-dxgk_engine_type.md) 

[DXGK_NODEMETADATA_FLAGS](ns-d3dkmdt-_dxgk_nodemetadata_flags.md) 

[DXGKDDI_GETNODEMETADATA](../d3dkmddi/nc-d3dkmddi-dxgkddi_getnodemetadata.md)

