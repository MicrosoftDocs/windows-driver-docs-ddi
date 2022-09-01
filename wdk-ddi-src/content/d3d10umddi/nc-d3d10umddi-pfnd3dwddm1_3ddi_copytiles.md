---
UID: NC:d3d10umddi.PFND3DWDDM1_3DDI_COPYTILES
title: PFND3DWDDM1_3DDI_COPYTILES (d3d10umddi.h)
description: Copies tiles from buffer to tiled resource or vice versa.
old-location: display\copytiles.htm
ms.date: 08/22/2022
keywords: ["PFND3DWDDM1_3DDI_COPYTILES callback function"]
ms.keywords: CopyTiles, CopyTiles callback function [Display Devices], PFND3DWDDM1_3DDI_COPYTILES, PFND3DWDDM1_3DDI_COPYTILES callback, d3d10umddi/CopyTiles, display.copytiles
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1 (WDDM 1.3)
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
 - PFND3DWDDM1_3DDI_COPYTILES
 - d3d10umddi/PFND3DWDDM1_3DDI_COPYTILES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - PFND3DWDDM1_3DDI_COPYTILES
product:
 - Windows
---

# PFND3DWDDM1_3DDI_COPYTILES callback function

## -description

Copies tiles from buffer to tiled resource or vice versa.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param hTiledResource

A handle to the tiled resource.

### -param pTileRegionStartCoord

A pointer to a [**D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE**](ns-d3d10umddi-d3dwddm1_3ddi_tiled_resource_coordinate.md) structure that describes the starting coordinates of the destination tiled resource.

### -param pTileRegionSize

A pointer to a [**D3DWDDM1_3DDI_TILE_REGION_SIZE**](ns-d3d10umddi-d3dwddm1_3ddi_tile_region_size.md) structure that describes the size of the tiled region.

### -param hBuffer

A handle to a resource that represents a default, dynamic, or staging buffer.

### -param BufferStartOffsetInBytes

The offset, in bytes, into the buffer at **hBuffer** to start the operation.

### -param Flags

A combination of [**D3DWDDM1_3DDI_TILE_COPY_FLAG**](ne-d3d10umddi-d3dwddm1_3ddi_tile_copy_flag.md) values that are combined by using a bitwise OR operation.

## -remarks

The driver can use the [**pfnSetErrorCb**](nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md) callback function to set an error code.

The Direct3D runtime does not expect this function to fail.

## -see-also

[**D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE**](ns-d3d10umddi-d3dwddm1_3ddi_tiled_resource_coordinate.md)

[**D3DWDDM1_3DDI_TILE_COPY_FLAG**](ne-d3d10umddi-d3dwddm1_3ddi_tile_copy_flag.md)

[**D3DWDDM1_3DDI_TILE_REGION_SIZE**](ns-d3d10umddi-d3dwddm1_3ddi_tile_region_size.md)

[**pfnSetErrorCb**](nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md)
