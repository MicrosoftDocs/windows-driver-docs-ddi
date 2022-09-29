---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEHEAPANDRESOURCE_0088
tech.root: display
title: PFND3D12DDI_CREATEHEAPANDRESOURCE_0088
ms.date: 09/29/2022
targetos: Windows
description: Learn more about the PFND3D12DDI_CREATEHEAPANDRESOURCE_0088 callback function.
prerelease: true
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
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
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
 - PFND3D12DDI_CREATEHEAPANDRESOURCE_0088
f1_keywords:
 - PFND3D12DDI_CREATEHEAPANDRESOURCE_0088
 - d3d12umddi/PFND3D12DDI_CREATEHEAPANDRESOURCE_0088
dev_langs:
 - c++
helpviewer_keywords:
 - PFND3D12DDI_CREATEHEAPANDRESOURCE_0088
---

## -description

**PFND3D12DDI_CREATEHEAPANDRESOURCE_0088** is used to simultaneously create a heap and resource.

## -parameters

### -param unnamedParam1

A **D3D12DDI_HDEVICE** handle to the display device (graphics context).

### -param unnamedParam2 [in, optional]

A [**D3D12DDIARG_CREATEHEAP_0001**](ns-d3d12umddi-d3d12ddiarg_createheap_0001.md) structure with arguments used to create a heap.

### -param unnamedParam3

The **D3D12DDI_HHEAP** handle to a heap.

### -param unnamedParam4

The **D3D12DDI_HRTRESOURCE** handle of the resource for the driver to use when it calls back into the runtime.

### -param unnamedParam5 [in, optional]

Pointer to a [**D3D12DDIARG_CREATERESOURCE_0088**](ns-d3d12umddi-d3d12ddiarg_createresource_0088.md) structure with arguments used to create a resource.

### -param unnamedParam6 [in, optional]

Pointer to a [**D3D12DDI_CLEAR_VALUES**](ns-d3d12umddi-d3d12ddi_clear_values.md) structure with values used to optimize clear operations for the resource.

### -param unnamedParam7

A **D3D12DDI_HPROTECTEDRESOURCESESSION_0030** handle to the protected resource session to use for the resource being created. Zero indicates unprotected resources. See the [Protected Resources Specification](https://microsoft.github.io/DirectX-Specs/d3d/ProtectedResources.html) for more information.

### -param unnamedParam8

The **D3D12DDI_HRESOURCE** handle to the hardware resource.

## -returns

If this callback function succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

[**D3D12DDIARG_CREATERESOURCE_0088**](ns-d3d12umddi-d3d12ddiarg_createresource_0088.md)

[**D3D12DDI_CLEAR_VALUES**](ns-d3d12umddi-d3d12ddi_clear_values.md)

[**PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0088**](nc-d3d12umddi-pfnd3d12ddi_calcprivateheapandresourcesizes_0088.md)
