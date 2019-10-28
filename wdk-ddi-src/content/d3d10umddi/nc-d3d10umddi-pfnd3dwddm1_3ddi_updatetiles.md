---
UID: NC:d3d10umddi.PFND3DWDDM1_3DDI_UPDATETILES
title: PFND3DWDDM1_3DDI_UPDATETILES (d3d10umddi.h)
description: Updates tiles by copying from app memory to the tiled resource.
old-location: display\updatetiles.htm
ms.assetid: 4891AB01-DE51-4B32-AA52-5619E86CC474
ms.date: 05/10/2018
ms.keywords: PFND3DWDDM1_3DDI_UPDATETILES, PFND3DWDDM1_3DDI_UPDATETILES callback, UpdateTiles, UpdateTiles callback function [Display Devices], d3d10umddi/UpdateTiles, display.updatetiles
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3d10umddi/UpdateTiles"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - UpdateTiles
product:
 - Windows
---

# PFND3DWDDM1_3DDI_UPDATETILES callback function

## -description

Updates tiles by copying from app memory to the tiled resource.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param hDestTiledResource

A handle to the tiled resource.

### -param pDestTileRegionStartCoord

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm1_3ddi_tiled_resource_coordinate">D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</a> structure that describes the starting coordinates of the tiled resource.

### -param pDestTileRegionSize

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm1_3ddi_tile_region_size">D3DWDDM1_3DDI_TILE_REGION_SIZE</a> structure that describes the size of the tiled region.

### -param pSourceTileData

A pointer to memory that contains the source tile data that this function uses to update the tiled resource.

### -param Flags

A combination of values of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3dwddm1_3ddi_tile_copy_flag">D3DWDDM1_3DDI_TILE_COPY_FLAG</a> that are combined by using a bitwise <b>OR</b> operation. The only valid value is <b>D3DWDDM1_3DDI_TILE_COPY_NO_OVERWRITE</b>. The other enumeration constant values aren't meaningful here, though by definition using  <b>D3DWDDM1_3DDI_TILE_COPY_SWIZZLED_TILED_RESOURCE_TO_LINEAR_BUFFER</b> results in what the <i>UpdateTiles</i> function does, sourcing from app memory.

## -returns

None

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code.

The Direct3D runtime does not expect this function to fail.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm1_3ddi_tiled_resource_coordinate">D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3dwddm1_3ddi_tile_copy_flag">D3DWDDM1_3DDI_TILE_COPY_FLAG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm1_3ddi_tile_region_size">D3DWDDM1_3DDI_TILE_REGION_SIZE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3dwddm1_3ddi_updatetiles">UpdateTiles</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

