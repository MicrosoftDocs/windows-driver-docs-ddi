---
UID: NE:d3d10umddi.D3DWDDM1_3DDI_TILE_COPY_FLAG
title: D3DWDDM1_3DDI_TILE_COPY_FLAG
author: windows-driver-content
description: Identifies how to copy a tile using the CopyTiles function.
old-location: display\d3dwddm1_3ddi_tile_copy_flag.htm
ms.assetid: DE743C61-4060-4601-987C-8026C78801A7
ms.date: 05/10/2018
ms.keywords: D3DWDDM1_3DDI_TILE_COPY_FLAG, D3DWDDM1_3DDI_TILE_COPY_FLAG enumeration [Display Devices], D3DWDDM1_3DDI_TILE_COPY_LINEAR_BUFFER_TO_SWIZZLED_TILED_RESOURCE, D3DWDDM1_3DDI_TILE_COPY_NO_OVERWRITE, D3DWDDM1_3DDI_TILE_COPY_SWIZZLED_TILED_RESOURCE_TO_LINEAR_BUFFER, d3d10umddi/D3DWDDM1_3DDI_TILE_COPY_FLAG, d3d10umddi/D3DWDDM1_3DDI_TILE_COPY_LINEAR_BUFFER_TO_SWIZZLED_TILED_RESOURCE, d3d10umddi/D3DWDDM1_3DDI_TILE_COPY_NO_OVERWRITE, d3d10umddi/D3DWDDM1_3DDI_TILE_COPY_SWIZZLED_TILED_RESOURCE_TO_LINEAR_BUFFER, display.d3dwddm1_3ddi_tile_copy_flag
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1,WDDM 1.3
req.target-min-winversvr: Windows Server 2012 R2
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3DWDDM1_3DDI_TILE_COPY_FLAG
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DWDDM1_3DDI_TILE_COPY_FLAG
---

# D3DWDDM1_3DDI_TILE_COPY_FLAG enumeration


## -description


Identifies how to copy a tile using the <a href="https://msdn.microsoft.com/8DA0FF6C-CA2C-4943-93C3-BFC3773617CC">CopyTiles</a> function.


## -enum-fields




### -field D3DWDDM1_3DDI_TILE_COPY_NO_OVERWRITE

The GPU isn't currently referencing any of the portions of destination memory being written.


### -field D3DWDDM1_3DDI_TILE_COPY_LINEAR_BUFFER_TO_SWIZZLED_TILED_RESOURCE

The <a href="https://msdn.microsoft.com/8DA0FF6C-CA2C-4943-93C3-BFC3773617CC">CopyTiles</a> operation involves copying a linear buffer to a swizzled tiled resource. This means to copy tile data from the specified buffer location, reading tiles sequentially, to the specified tile region (in <i>x</i>, <i>y</i>, <i>z</i> order if the region is a box), swizzling to optimal hardware memory layout as needed. In this <i>CopyTiles</i> call, you specify the source data with the <i>hBuffer</i> parameter and the destination with the <i>hTiledResource</i> parameter.


### -field D3DWDDM1_3DDI_TILE_COPY_SWIZZLED_TILED_RESOURCE_TO_LINEAR_BUFFER

The <a href="https://msdn.microsoft.com/8DA0FF6C-CA2C-4943-93C3-BFC3773617CC">CopyTiles</a> operation involves copying a swizzled tiled resource to a linear buffer. This means to copy tile data from the tile region, reading tiles sequentially (in <i>x</i>, <i>y</i>, <i>z</i> order if the region is a box), to the specified buffer location, deswizzling to linear memory layout as needed. In this <i>CopyTiles</i> call, you specify the source data with the <i>hTiledResource</i> parameter and the destination with the <i>hBuffer</i> parameter.


## -see-also




<a href="https://msdn.microsoft.com/8DA0FF6C-CA2C-4943-93C3-BFC3773617CC">CopyTiles</a>
 

 

