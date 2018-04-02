---
UID: NC:d3d10umddi.PFND3DWDDM1_3DDI_UPDATETILEMAPPINGS
title: PFND3DWDDM1_3DDI_UPDATETILEMAPPINGS
author: windows-driver-content
description: Updates mappings of tile locations in tiled resources to memory locations in a tile pool.
old-location: display\updatetilemappings.htm
old-project: display
ms.assetid: 1C8FC920-145F-4AE9-B049-F6BDAE29D1F1
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3DWDDM1_3DDI_UPDATETILEMAPPINGS, UpdateTileMappings, UpdateTileMappings callback function [Display Devices], d3d10umddi/UpdateTileMappings, display.updatetilemappings
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d10umddi.h
api_name:
-	UpdateTileMappings
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3DWDDM1_3DDI_UPDATETILEMAPPINGS callback


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

An array of <a href="https://msdn.microsoft.com/library/windows/hardware/dn440996">D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</a> structures that describe the starting coordinates of the tiled resource regions. The <i>NumTiledResourceRegions</i> parameter specifies the number of <b>D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</b> structures in the array.


### -param *pTiledResourceRegionSizes [in, optional]

An array of <a href="https://msdn.microsoft.com/library/windows/hardware/dn440997">D3DWDDM1_3DDI_TILE_REGION_SIZE</a> structures that describe the sizes of the tiled resource regions. The <i>NumTiledResourceRegions</i> parameter specifies the number of <b>D3DWDDM1_3DDI_TILE_REGION_SIZE</b> structures in the array.


### -param hTilePool

A handle to the tile pool.


### -param NumRanges

The number of tile-pool ranges.


### -param *pRangeFlags [in, optional]

An array of values that describe each tile-pool range. The <i>NumRanges</i> parameter specifies the number of values in the array. Each value can be a combination of values of type <a href="https://msdn.microsoft.com/library/windows/hardware/dn458991">D3DWDDM1_3DDI_TILE_RANGE_FLAG</a> combined by using a bitwise <b>OR</b> operation.


### -param *pTilePoolStartOffsets [in, optional]

An array of offsets into the tile pool. These are zero-based tile offsets, counting in tiles (not bytes).


### -param *pRangeTileCounts [in, optional]

An array of values that specify the number of tiles in each tile-pool range. The <i>NumRanges</i> parameter specifies the number of values in the array.


### -param Flags

A combination of <a href="https://msdn.microsoft.com/library/windows/hardware/dn458990">D3DWDDM1_3DDI_TILE_MAPPING_FLAG</a> values that are combined by using a bitwise <b>OR</b> operation.


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. The driver can set <b>E_INVALIDARG</b> if a required input parameter does not exist or is <b>NULL</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn440996">D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn458990">D3DWDDM1_3DDI_TILE_MAPPING_FLAG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn458991">D3DWDDM1_3DDI_TILE_RANGE_FLAG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn440997">D3DWDDM1_3DDI_TILE_REGION_SIZE</a>
 

 

