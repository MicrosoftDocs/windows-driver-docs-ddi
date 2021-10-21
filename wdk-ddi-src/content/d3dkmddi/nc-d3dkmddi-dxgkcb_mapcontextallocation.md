---
UID: NC:d3dkmddi.DXGKCB_MAPCONTEXTALLOCATION
title: DXGKCB_MAPCONTEXTALLOCATION (d3dkmddi.h)
description: Maps a graphics processing unit (GPU) virtual address to the specified context allocation.
old-location: display\dxgkcbmapcontextallocation.htm
ms.date: 10/13/2021
keywords: ["DXGKCB_MAPCONTEXTALLOCATION callback function"]
ms.keywords: DXGKCB_MAPCONTEXTALLOCATION, DXGKCB_MAPCONTEXTALLOCATION callback, DxgkCbMapContextAllocation, DxgkCbMapContextAllocation callback function [Display Devices], d3dkmddi/DxgkCbMapContextAllocation, display.dxgkcbmapcontextallocation
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKCB_MAPCONTEXTALLOCATION
 - d3dkmddi/DXGKCB_MAPCONTEXTALLOCATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_MAPCONTEXTALLOCATION
product:
 - Windows
---

# DXGKCB_MAPCONTEXTALLOCATION callback function

## -description

A kernel-mode display miniport driver calls **DXGKCB_MAPCONTEXTALLOCATION** to map a graphics processing unit (GPU) virtual address to the specified context allocation.

## -parameters

### -param hAdapter [in]

A handle to the display adapter.

### -param pArgs [in]

Pointer to a [**DXGKARGCB_MAPCONTEXTALLOCATION**](ns-d3dkmddi-_dxgkargcb_mapcontextallocation.md) structure that describes the operation.

## -returns

**DXGKCB_MAPCONTEXTALLOCATION** returns a **D3DGPU_VIRTUAL_ADDRESS** if successful, NULL otherwise.

## -remarks

This device driver interface (DDI) behaves like its user-mode counterpart; see [**pfnMapGpuVirtualAddressCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_mapgpuvirtualaddresscb.md) for more details.

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, set the members of [**DXGKARGCB_MAPCONTEXTALLOCATION**](ns-d3dkmddi-_dxgkargcb_mapcontextallocation.md) and then call **DxgkCbMapContextAllocation** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

## -see-also

[**DXGKARGCB_MAPCONTEXTALLOCATION**](ns-d3dkmddi-_dxgkargcb_mapcontextallocation.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)

[**pfnMapGpuVirtualAddressCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_mapgpuvirtualaddresscb.md)
