---
UID: NC:d3d12umddi.PFND3D12DDI_CREATECOMMANDALLOCATOR
title: PFND3D12DDI_CREATECOMMANDALLOCATOR (d3d12umddi.h)
description: Creates a command allocator.
ms.date: 04/25/2025
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows Vista (WDDM 1.0)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - PFND3D12DDI_CREATECOMMANDALLOCATOR
 - d3d12umddi/PFND3D12DDI_CREATECOMMANDALLOCATOR
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATECOMMANDALLOCATOR
dev_langs:
 - c++
---

# PFND3D12DDI_CREATECOMMANDALLOCATOR callback function

## -description

The user-mode display driver's (UMD) **pfnCreateCommandAllocator** function creates a command allocator.

## -parameters

### -param unnamedParam1

[in] A handle to the display device (graphics context).

### -param unnamedParam2

[in] Pointer to a [**D3D12DDIARG_CREATECOMMANDALLOCATOR**](ns-d3d12umddi-d3d12ddiarg_createcommandallocator.md) structure that describes the command allocator to create.

## -returns

**pfnCreateCommandAllocator** returns an HRESULT value.

## -remarks

The command allocator corresponds to the underlying allocations in which GPU command lists are stored. It applies to both direct and bundle command lists.

## -see-also

[**D3D12DDIARG_CREATECOMMANDALLOCATOR**](ns-d3d12umddi-d3d12ddiarg_createcommandallocator.md)

[**pfnCalcPrivateCommandAllocatorSize**](nc-d3d12umddi-pfnd3d12ddi_calcprivatecommandallocatorsize.md)

[**pfnDestroyCommandAllocator**](nc-d3d12umddi-pfnd3d12ddi_destroycommandallocator.md)

[**pfnResetCommandAllocator**](nc-d3d12umddi-pfnd3d12ddi_resetcommandallocator.md)
