---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_SHADER_0026
tech.root: display
title: PFND3D12DDI_CREATE_SHADER_0026
ms.date: 06/28/2024
targetos: Windows
description: Learn about the PFND3D12DDI_CREATE_SHADER_0026 callback function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
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
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATE_SHADER_0026
f1_keywords:
 - PFND3D12DDI_CREATE_SHADER_0026
 - d3d12umddi/PFND3D12DDI_CREATE_SHADER_0026
dev_langs:
 - c++
helpviewer_keywords:
 - PFND3D12DDI_CREATE_SHADER_0026
---

## -description

The user-mode display driver's **PFND3D12DDI_CREATE_SHADER_0026** callback function creates a shader.

## -parameters

### -param unnamedParam1

[in] A handle to the display device (graphics context) for which to create the shader.

### -param unnamedParam2

[in] Pointer to a [**D3D12DDIARG_CREATE_SHADER_0026**](ns-d3d12umddi-d3d12ddiarg_create_shader_0026.md) structure that describes the shader to create.

### -param unnamedParam3

[out] Handle to the shader that the driver created.

## -remarks

The [**D3D12DDI_DEVICE_FUNCS_CORE_*XXX***](ns-d3d12umddi-d3d12ddi_device_funcs_core_0109.md) structure contains pointers to **PFND3D12DDI_CREATE_SHADER_0026** callback functions for the various shader types that the driver supports.

## -see-also

[**D3D12DDIARG_CREATE_SHADER_0026**](ns-d3d12umddi-d3d12ddiarg_create_shader_0026.md)
