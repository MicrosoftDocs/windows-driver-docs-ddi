---
UID: NS:d3dkmddi._DXGKARGCB_MAPCONTEXTALLOCATION
title: DXGKARGCB_MAPCONTEXTALLOCATION (d3dkmddi.h)
description: DXGKARGCB_MAPCONTEXTALLOCATION is used with DxgkCbMapContextAllocation to map a graphics processing unit (GPU) virtual address to the specified context allocation.
old-location: display\dxgkargcb_mapcontextallocation.htm
ms.date: 10/13/2021
keywords: ["DXGKARGCB_MAPCONTEXTALLOCATION structure"]
ms.keywords: DXGKARGCB_MAPCONTEXTALLOCATION, DXGKARGCB_MAPCONTEXTALLOCATION structure [Display Devices], _DXGKARGCB_MAPCONTEXTALLOCATION, d3dkmddi/DXGKARGCB_MAPCONTEXTALLOCATION, display.dxgkargcb_mapcontextallocation
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10 (WDDM 2.0)
req.target-min-winversvr: Windows Server 2016
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
req.typenames: DXGKARGCB_MAPCONTEXTALLOCATION
f1_keywords:
 - _DXGKARGCB_MAPCONTEXTALLOCATION
 - d3dkmddi/_DXGKARGCB_MAPCONTEXTALLOCATION
 - DXGKARGCB_MAPCONTEXTALLOCATION
 - d3dkmddi/DXGKARGCB_MAPCONTEXTALLOCATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_MAPCONTEXTALLOCATION
 - DXGKARGCB_MAPCONTEXTALLOCATION
---

# DXGKARGCB_MAPCONTEXTALLOCATION structure

## -description

The **DXGKARGCB_MAPCONTEXTALLOCATION** structure contains the arguments used in the [**DXGKCB_MAPCONTEXTALLOCATION**](nc-d3dkmddi-dxgkcb_mapcontextallocation.md) callback function, to map a graphics processing unit (GPU) virtual address to the specified context allocation.

## -struct-fields

### -field BaseAddress [in]

(optional) If non-NULL, the video memory manager will attempt to use this address as the base address for the mapping. If the range from **BaseAddress** to **BaseAddress**+**Size** isn’t free, the call will fail. When this parameter is non-NULL, **MinimumAddress** and **MaximumAddress** are ignored.

If NULL is specified, the video memory manager will pick the base address for the allocation within the specified **MinimumAddress** and **MaximumAddress**.

### -field MinimumAddress [in]

(optional) The minimum GPU virtual address to consider for the mapped range. This parameter is ignored when **BaseAddress** != **NULL**.

### -field MaximumAddress [in]

The maximum GPU virtual address to consider for the mapped range. The video memory manager will guarantee that **BaseAddress**+**Size** <= **MaximumAddress**. If this is set to **NULL** the video memory manager will not apply any limit. This parameter is ignored when **BaseAddress** != **NULL**.

### -field hAllocation [in]

Handle to the allocation being mapped into the GPU virtual address space. This is a DirectX graphics kernel  handle, returned by [**DXGKCB_CREATECONTEXTALLOCATION**](nc-d3dkmddi-dxgkcb_createcontextallocation.md).

### -field OffsetInPages [in]

The offset, in 4KB pages, to the starting page within the specified allocation that must be mapped.

### -field SizeInPages [in]

The size of the range to map in number of 4KB pages.

### -field Protection [in]

The protection on the GPU virtual address that is mapped.

### -field DriverProtection [in]

The driver protection parameters.

## -see-also

[**DXGKCB_CREATECONTEXTALLOCATION**](nc-d3dkmddi-dxgkcb_createcontextallocation.md)

[**DXGKCB_MAPCONTEXTALLOCATION**](nc-d3dkmddi-dxgkcb_mapcontextallocation.md)
