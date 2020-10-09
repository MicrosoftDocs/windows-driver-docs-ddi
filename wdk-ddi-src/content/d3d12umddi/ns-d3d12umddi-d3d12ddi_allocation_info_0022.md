---
UID: NS:d3d12umddi.D3D12DDI_ALLOCATION_INFO_0022
title: D3D12DDI_ALLOCATION_INFO_0022 (d3d12umddi.h)
description: Specifies allocation information.
old-location: display\d3d12ddi_allocation_info_0022.htm
ms.assetid: A600C402-EB77-4C44-8349-96DAF11B807C
ms.date: 05/10/2018
keywords: ["D3D12DDI_ALLOCATION_INFO_0022 structure"]
ms.keywords: D3D12DDI_ALLOCATION_INFO_0022, D3D12DDI_ALLOCATION_INFO_0022 structure [Display Devices], d3d12umddi/D3D12DDI_ALLOCATION_INFO_0022, display.d3d12ddi_allocation_info_0022
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
req.typenames: D3D12DDI_ALLOCATION_INFO_0022
f1_keywords:
 - D3D12DDI_ALLOCATION_INFO_0022
 - d3d12umddi/D3D12DDI_ALLOCATION_INFO_0022
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d12umddi.h
api_name:
 - D3D12DDI_ALLOCATION_INFO_0022
---

# D3D12DDI_ALLOCATION_INFO_0022 structure


## -description

Specifies allocation information.

## -struct-fields

### -field hAllocation

The handle of an allocation.

### -field pSystemMem

Pointer to a system memory location that is preallocated. If the allocation uses video memory, specify null.

### -field pPrivateDriverData

Pointer to a buffer that contains optional private driver data.

### -field PrivateDriverDataSize

Size of the private driver data buffer.

### -field VidPnSourceId

A zero-based ID of the video present source in a path of a video present network topology.

### -field Flags

Flags that identify the type of the allocation information as a <a href="/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddi_allocation_info_flags_0022">D3D12DDI_ALLOCATION_INFO_FLAGS_0022</a> value.

### -field GpuVirtualAddress

A virtual address in the GPU.

### -field Priority

A priority for the allocation.

### -field Reserved

Reserved.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddi_allocation_info_flags_0022">D3D12DDI_ALLOCATION_INFO_FLAGS_0022</a>