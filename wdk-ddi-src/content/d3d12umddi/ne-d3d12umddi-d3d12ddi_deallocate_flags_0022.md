---
UID: NE:d3d12umddi.D3D12DDI_DEALLOCATE_FLAGS_0022
title: D3D12DDI_DEALLOCATE_FLAGS_0022 (d3d12umddi.h)
description: Learn more about the D3D12DDI_DEALLOCATE_FLAGS_0022 enumeration.
ms.date: 05/22/2024
keywords: ["D3D12DDI_DEALLOCATE_FLAGS_0022 enumeration"]
ms.keywords: D3D12DDI_DEALLOCATE_FLAGS_0022, D3D12DDI_DEALLOCATE_FLAGS_0022 enumeration [Display Devices], D3D12DDI_DEALLOCATE_FLAGS_0022_ASSUME_NOT_IN_USE, D3D12DDI_DEALLOCATE_FLAGS_0022_NONE, D3D12DDI_DEALLOCATE_FLAGS_0022_SYNCHRONOUS_DESTROY, d3d12umddi/D3D12DDI_DEALLOCATE_FLAGS_0022, d3d12umddi/D3D12DDI_DEALLOCATE_FLAGS_0022_ASSUME_NOT_IN_USE, d3d12umddi/D3D12DDI_DEALLOCATE_FLAGS_0022_NONE, d3d12umddi/D3D12DDI_DEALLOCATE_FLAGS_0022_SYNCHRONOUS_DESTROY, display.d3d12ddi_deallocate_flags_0022
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_DEALLOCATE_FLAGS_0022
f1_keywords:
 - D3D12DDI_DEALLOCATE_FLAGS_0022
 - d3d12umddi/D3D12DDI_DEALLOCATE_FLAGS_0022
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d12umddi.h
api_name:
 - D3D12DDI_DEALLOCATE_FLAGS_0022
---

# D3D12DDI_DEALLOCATE_FLAGS_0022 enumeration

## -description

The **D3D12DDI_DEALLOCATE_FLAGS_0022** enumeration contains bit-wise flags for the runtime's [**pfnDeallocateCb**](nc-d3d12umddi-pfnd3d12ddi_deallocate_cb_0022.md) callback function.

## -enum-fields

### -field D3D12DDI_DEALLOCATE_FLAGS_0022_NONE:0x0

No flags are specified.

### -field D3D12DDI_DEALLOCATE_FLAGS_0022_ASSUME_NOT_IN_USE:0x1

Assume that the allocation is not in use.

### -field D3D12DDI_DEALLOCATE_FLAGS_0022_SYNCHRONOUS_DESTROY:0x2

Ensure that the resource is destroyed synchronously.

### -field D3D12DDI_DEALLOCATE_FLAGS_0022_VALID_MASK:0x3

A mask that defines all valid bits for the flags in this enumeration.

## -remarks

The UMD provides these flags when it calls the runtime's [**pfnDeallocateCb**](nc-d3d12umddi-pfnd3d12ddi_deallocate_cb_0022.md) callback to deallocate resources.

## -see-also

[**D3D12DDICB_DEALLOCATE_0022**](ns-d3d12umddi-d3d12ddicb_deallocate_0022.md)

[**pfnDeallocateCb**](nc-d3d12umddi-pfnd3d12ddi_deallocate_cb_0022.md)
