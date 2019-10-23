---
UID: NC:d3d10umddi.PFND3DWDDM1_3DDI_COPYTILES
title: PFND3DWDDM1_3DDI_COPYTILES (d3d10umddi.h)
description: Copies tiles from buffer to tiled resource or vice versa.
old-location: display\copytiles.htm
ms.assetid: 8DA0FF6C-CA2C-4943-93C3-BFC3773617CC
ms.date: 05/10/2018
ms.keywords: CopyTiles, CopyTiles callback function [Display Devices], PFND3DWDDM1_3DDI_COPYTILES, PFND3DWDDM1_3DDI_COPYTILES callback, d3d10umddi/CopyTiles, display.copytiles
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
 - "d3d10umddi/CopyTiles"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - CopyTiles
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

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm1_3ddi_tiled_resource_coordinate">D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</a> structure that describes the starting coordinates of the destination tiled resource.

### -param pTileRegionSize

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm1_3ddi_tile_region_size">D3DWDDM1_3DDI_TILE_REGION_SIZE</a> structure that describes the size of the tiled region.

### -param hBuffer

A handle to a resource that represents a default, dynamic, or staging buffer.

### -param BufferStartOffsetInBytes

The offset, in bytes, into the buffer at <i>hBuffer</i> to start the operation.

### -param Flags

A combination of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3dwddm1_3ddi_tile_copy_flag">D3DWDDM1_3DDI_TILE_COPY_FLAG</a> values that are combined by using a bitwise <b>OR</b> operation.

## -returns

None

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code.

The Direct3D runtime does not expect this function to fail.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm1_3ddi_tiled_resource_coordinate">D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3dwddm1_3ddi_tile_copy_flag">D3DWDDM1_3DDI_TILE_COPY_FLAG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm1_3ddi_tile_region_size">D3DWDDM1_3DDI_TILE_REGION_SIZE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

