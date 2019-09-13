---
UID: NC:d3d10umddi.PFND3DWDDM1_3DDI_COPYTILEMAPPINGS
title: PFND3DWDDM1_3DDI_COPYTILEMAPPINGS (d3d10umddi.h)
description: Copies mappings from a source tiled resource to a destination tiled resource.
old-location: display\copytilemappings.htm
ms.assetid: CB2CE5E7-DDD4-4782-BB91-67A2C562A975
ms.date: 05/10/2018
ms.keywords: CopyTileMappings, CopyTileMappings callback function [Display Devices], PFND3DWDDM1_3DDI_COPYTILEMAPPINGS, PFND3DWDDM1_3DDI_COPYTILEMAPPINGS callback, d3d10umddi/CopyTileMappings, display.copytilemappings
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
 - "d3d10umddi/CopyTileMappings"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - CopyTileMappings
product:
 - Windows
---

# PFND3DWDDM1_3DDI_COPYTILEMAPPINGS callback function

## -description

Copies mappings from a source tiled resource to a destination tiled resource.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param hDestTiledResource

A handle to the destination tiled resource.

### -param pDestRegionStartCoord

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3dwddm1_3ddi_tiled_resource_coordinate">D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</a> structure that describes the starting coordinates of the destination tiled resource.

### -param hSourceTiledResource

A handle to the source tiled resource.

### -param pSourceRegionStartCoord

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3dwddm1_3ddi_tiled_resource_coordinate">D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</a> structure that describes the starting coordinates of the source tiled resource.

### -param pTileRegionSize

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3dwddm1_3ddi_tile_region_size">D3DWDDM1_3DDI_TILE_REGION_SIZE</a> structure that describes the size of the tiled region.

### -param Flags

A combination of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3dwddm1_3ddi_tile_mapping_flag">D3DWDDM1_3DDI_TILE_MAPPING_FLAG</a> values that are combined by using a bitwise <b>OR</b> operation.

## -returns

None

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. The driver can set <b>E_INVALIDARG</b> if an input parameter does not exist or is <b>NULL</b>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3dwddm1_3ddi_tiled_resource_coordinate">D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3dwddm1_3ddi_tile_mapping_flag">D3DWDDM1_3DDI_TILE_MAPPING_FLAG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3dwddm1_3ddi_tile_region_size">D3DWDDM1_3DDI_TILE_REGION_SIZE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

