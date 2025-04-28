---
UID: NE:d3d12umddi.D3D12DDI_COMMAND_LIST_TYPE
tech.root: display
title: D3D12DDI_COMMAND_LIST_TYPE
ms.date: 04/25/2025
targetos: Windows
description: Learn more about the D3D12DDI_COMMAND_LIST_TYPE enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_COMMAND_LIST_TYPE
f1_keywords:
 - D3D12DDI_COMMAND_LIST_TYPE
 - d3d12umddi/D3D12DDI_COMMAND_LIST_TYPE
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_COMMAND_LIST_TYPE
---

## -description

The **D3D12DDI_COMMAND_LIST_TYPE** enumeration specifies the type of a command list.

## -enum-fields

### -field D3D12DDI_COMMAND_LIST_TYPE_DIRECT:0

Specifies a command buffer that the GPU can execute directly. A direct command list doesn't inherit any GPU state, so all required state must be explicitly set within the command list.

### -field D3D12DDI_COMMAND_LIST_TYPE_BUNDLE:1

Specifies a command buffer that can only be executed directly via a direct command list. A bundle command list inherits the GPU state from the direct command list that executes it, except for the pipeline state object and primitive topology, which must be explicitly set within the bundle.

## -see-also

[**pfnCreateCommandAllocator**](nc-d3d12umddi-pfnd3d12ddi_createcommandallocator.md)

[**pfnCreateCommandList**](nc-d3d12umddi-pfnd3d12ddi_create_command_list_0040.md)
