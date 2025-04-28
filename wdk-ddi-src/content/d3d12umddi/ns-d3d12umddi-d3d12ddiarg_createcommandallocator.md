---
UID: NS:d3d12umddi.D3D12DDIARG_CREATECOMMANDALLOCATOR
tech.root: display
title: D3D12DDIARG_CREATECOMMANDALLOCATOR
ms.date: 04/25/2025
targetos: Windows
description: Learn more about the D3D12DDIARG_CREATECOMMANDALLOCATOR structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows Vista (WDDM 1.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDIARG_CREATECOMMANDALLOCATOR
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDIARG_CREATECOMMANDALLOCATOR
f1_keywords:
 - D3D12DDIARG_CREATECOMMANDALLOCATOR
 - d3d12umddi/D3D12DDIARG_CREATECOMMANDALLOCATOR
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDIARG_CREATECOMMANDALLOCATOR
---

## -description

The **D3D12DDIARG_CREATECOMMANDALLOCATOR** structure describes a [command allocator to create](nc-d3d12umddi-pfnd3d12ddi_createcommandallocator.md).

## -struct-fields

### -field hDrvCommandAllocator

Handle to associate with the command allocator. The driver must use this handle to identify the command allocator in subsequent calls to the driver.

### -field Type

A [**D3D12DDI_COMMAND_LIST_TYPE**](ne-d3d12umddi-d3d12ddi_command_list_type.md) value that specifies the type of command list associated with the command allocator.

### -field QueueFlags

A [**D3D12DDI_COMMAND_QUEUE_FLAGS**](ne-d3d12umddi-d3d12ddi_command_queue_flags.md) value that specifies the command queue flags associated with the command allocator.

## -remarks

This structure is passed to the [**pfnCreateCommandAllocator**](nc-d3d12umddi-pfnd3d12ddi_createcommandallocator.md) function.

## -see-also

[**D3D12DDI_COMMAND_LIST_TYPE**](ne-d3d12umddi-d3d12ddi_command_list_type.md)

[**D3D12DDI_COMMAND_QUEUE_FLAGS**](ne-d3d12umddi-d3d12ddi_command_queue_flags.md)

[**pfnCreateCommandAllocator**](nc-d3d12umddi-pfnd3d12ddi_createcommandallocator.md)
