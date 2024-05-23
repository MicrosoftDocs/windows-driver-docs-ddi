---
UID: NS:d3d12umddi.D3D12DDICB_DEALLOCATE_0022
title: D3D12DDICB_DEALLOCATE_0022 (d3d12umddi.h)
description: Learn more about the D3D12DDICB_DEALLOCATE_0022 structure.
ms.date: 05/22/2024
keywords: ["D3D12DDICB_DEALLOCATE_0022 structure"]
ms.keywords: D3D12DDICB_DEALLOCATE_0022, D3D12DDICB_DEALLOCATE_0022 structure [Display Devices], d3d12umddi/D3D12DDICB_DEALLOCATE_0022, display.d3d12ddicb_deallocate_0022
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
req.typenames: D3D12DDICB_DEALLOCATE_0022
f1_keywords:
 - D3D12DDICB_DEALLOCATE_0022
 - d3d12umddi/D3D12DDICB_DEALLOCATE_0022
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d12umddi.h
api_name:
 - D3D12DDICB_DEALLOCATE_0022
---

# D3D12DDICB_DEALLOCATE_0022 structure

## -description

The **D3D12DDICB_DEALLOCATE_0022** structure contains information needed by the runtime's [**pfnDeallocateCb**](nc-d3d12umddi-pfnd3d12ddi_deallocate_cb_0022.md) callback function to deallocate resources.

## -struct-fields

### -field hResource

[in] The handle of the resource to be deallocated.

### -field NumAllocations

[in] The number of allocations in the **HandleList** array to be deallocated.

### -field HandleList

[in] A pointer to an array of handles to be deallocated.

### -field Flags

A [**D3D12DDI_DEALLOCATE_FLAGS_0022**](ne-d3d12umddi-d3d12ddi_deallocate_flags_0022.md) enumeration that specifies flag(s) that the runtime should use when doing the deallocation.

## -see-also

[**D3D12DDI_DEALLOCATE_FLAGS_0022**](ne-d3d12umddi-d3d12ddi_deallocate_flags_0022.md)

[**pfnDeallocateCb**](nc-d3d12umddi-pfnd3d12ddi_deallocate_cb_0022.md)
