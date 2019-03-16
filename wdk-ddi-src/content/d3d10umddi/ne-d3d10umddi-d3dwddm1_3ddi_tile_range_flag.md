---
UID: NE:d3d10umddi.D3DWDDM1_3DDI_TILE_RANGE_FLAG
title: D3DWDDM1_3DDI_TILE_RANGE_FLAG (d3d10umddi.h)
description: Specifies a range of tile mappings to use with the UpdateTileMappings function.
old-location: display\d3dwddm1_3ddi_tile_range_flag.htm
ms.assetid: 7D8B55F1-00BD-414B-9E78-DABCEBEF949F
ms.date: 05/10/2018
ms.keywords: D3DWDDM1_3DDI_TILE_RANGE_FLAG, D3DWDDM1_3DDI_TILE_RANGE_FLAG enumeration [Display Devices], D3DWDDM_1_3DDI_TILE_RANGE_NULL, D3DWDDM_1_3DDI_TILE_RANGE_REUSE_SINGLE_TILE, D3DWDDM_1_3DDI_TILE_RANGE_SKIP, d3d10umddi/D3DWDDM1_3DDI_TILE_RANGE_FLAG, d3d10umddi/D3DWDDM_1_3DDI_TILE_RANGE_NULL, d3d10umddi/D3DWDDM_1_3DDI_TILE_RANGE_REUSE_SINGLE_TILE, d3d10umddi/D3DWDDM_1_3DDI_TILE_RANGE_SKIP, display.d3dwddm1_3ddi_tile_range_flag
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d10umddi.h
api_name:
- D3DWDDM1_3DDI_TILE_RANGE_FLAG
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DWDDM1_3DDI_TILE_RANGE_FLAG
---

# D3DWDDM1_3DDI_TILE_RANGE_FLAG enumeration


## -description


Specifies a range of tile mappings to use with the UpdateTileMappings function.


## -enum-fields




### -field D3DWDDM_1_3DDI_TILE_RANGE_NULL

The tile range is <b>NULL</b>.

If this flag is set in the UpdateTileMappings function's <i>pRangeFlags</i> parameter, the <i>pRangeTileCounts</i> parameter specifies the total 
number of tiles in all the tile regions, and the <i>pTilePoolStartOffsets</i> parameter is ignored.


### -field D3DWDDM_1_3DDI_TILE_RANGE_SKIP

Tiles should be skipped over, and existing tile mappings should be left unchanged.

If this flag is set in the UpdateTileMappings function's <i>pRangeFlags</i> parameter, the <i>pRangeTileCounts</i> parameter specifies how many tiles from the tile regions to skip over, and the <i>pTilePoolStartOffsets</i> parameter is ignored.


### -field D3DWDDM_1_3DDI_TILE_RANGE_REUSE_SINGLE_TILE

A single tile in the tile pool should be reused.

If this flag is set in the UpdateTileMappings function's <i>pRangeFlags</i> parameter, the <i>pTilePoolStartOffsets</i> parameter specifies the single tile in the tile pool to map to, and the <i>pRangeTileCounts</i> parameter specifies how many tiles from the tile region to map to that tile pool location.

