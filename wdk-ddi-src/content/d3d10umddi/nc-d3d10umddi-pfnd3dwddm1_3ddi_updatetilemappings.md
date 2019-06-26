---
UID: NC:d3d10umddi.PFND3DWDDM1_3DDI_UPDATETILEMAPPINGS
title: PFND3DWDDM1_3DDI_UPDATETILEMAPPINGS (d3d10umddi.h)
description: Updates mappings of tile locations in tiled resources to memory locations in a tile pool.
old-location: display\updatetilemappings.htm
ms.assetid: 1C8FC920-145F-4AE9-B049-F6BDAE29D1F1
ms.date: 05/10/2018
ms.keywords: PFND3DWDDM1_3DDI_UPDATETILEMAPPINGS, PFND3DWDDM1_3DDI_UPDATETILEMAPPINGS callback, UpdateTileMappings, UpdateTileMappings callback function [Display Devices], d3d10umddi/UpdateTileMappings, display.updatetilemappings
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
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
- UserDefined
api_location:
- D3d10umddi.h
api_name:
- UpdateTileMappings
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3DWDDM1_3DDI_UPDATETILEMAPPINGS callback function


## -description


Updates mappings of tile locations in tiled resources to memory locations in a tile pool.


## -parameters




### -param hDevice

A handle to the display device (graphics context).


### -param hTiledResource

A handle to the tiled resource.


### -param NumTiledResourceRegions

The number of tiled resource regions.


### -param *pTiledResourceRegionStartCoords [in]

An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3dwddm1_3ddi_tiled_resource_coordinate">D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</a> structures that describe the starting coordinates of the tiled resource regions. The <i>NumTiledResourceRegions</i> parameter specifies the number of <b>D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</b> structures in the array.


### -param *pTiledResourceRegionSizes [in, optional]

An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3dwddm1_3ddi_tile_region_size">D3DWDDM1_3DDI_TILE_REGION_SIZE</a> structures that describe the sizes of the tiled resource regions. The <i>NumTiledResourceRegions</i> parameter specifies the number of <b>D3DWDDM1_3DDI_TILE_REGION_SIZE</b> structures in the array.


### -param hTilePool

A handle to the tile pool.


### -param NumRanges

The number of tile-pool ranges.


### -param *pRangeFlags [in, optional]

An array of values that describe each tile-pool range. The <i>NumRanges</i> parameter specifies the number of values in the array. Each value can be a combination of values of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3dwddm1_3ddi_tile_range_flag">D3DWDDM1_3DDI_TILE_RANGE_FLAG</a> combined by using a bitwise <b>OR</b> operation.


### -param *pTilePoolStartOffsets [in, optional]

An array of offsets into the tile pool. These are zero-based tile offsets, counting in tiles (not bytes).


### -param *pRangeTileCounts [in, optional]

An array of values that specify the number of tiles in each tile-pool range. The <i>NumRanges</i> parameter specifies the number of values in the array.


### -param Flags

A combination of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3dwddm1_3ddi_tile_mapping_flag">D3DWDDM1_3DDI_TILE_MAPPING_FLAG</a> values that are combined by using a bitwise <b>OR</b> operation.


## -returns



None

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. The driver can set <b>E_INVALIDARG</b> if a required input parameter does not exist or is <b>NULL</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3dwddm1_3ddi_tiled_resource_coordinate">D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3dwddm1_3ddi_tile_mapping_flag">D3DWDDM1_3DDI_TILE_MAPPING_FLAG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3dwddm1_3ddi_tile_range_flag">D3DWDDM1_3DDI_TILE_RANGE_FLAG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3dwddm1_3ddi_tile_region_size">D3DWDDM1_3DDI_TILE_REGION_SIZE</a>
 

 

