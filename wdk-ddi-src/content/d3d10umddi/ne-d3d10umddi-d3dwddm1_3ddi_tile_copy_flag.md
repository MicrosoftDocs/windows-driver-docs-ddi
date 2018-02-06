---
UID: NE:d3d10umddi.D3DWDDM1_3DDI_TILE_COPY_FLAG
title: D3DWDDM1_3DDI_TILE_COPY_FLAG
author: windows-driver-content
description: Identifies how to copy a tile using the CopyTiles function.
old-location: display\d3dwddm1_3ddi_tile_copy_flag.htm
old-project: display
ms.assetid: DE743C61-4060-4601-987C-8026C78801A7
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DWDDM1_3DDI_TILE_COPY_FLAG, d3d10umddi/D3DWDDM1_3DDI_TILE_COPY_NO_OVERWRITE, D3DWDDM1_3DDI_TILE_COPY_SWIZZLED_TILED_RESOURCE_TO_LINEAR_BUFFER, d3d10umddi/D3DWDDM1_3DDI_TILE_COPY_SWIZZLED_TILED_RESOURCE_TO_LINEAR_BUFFER, display.d3dwddm1_3ddi_tile_copy_flag, d3d10umddi/D3DWDDM1_3DDI_TILE_COPY_LINEAR_BUFFER_TO_SWIZZLED_TILED_RESOURCE, d3d10umddi/D3DWDDM1_3DDI_TILE_COPY_FLAG, D3DWDDM1_3DDI_TILE_COPY_LINEAR_BUFFER_TO_SWIZZLED_TILED_RESOURCE, D3DWDDM1_3DDI_TILE_COPY_NO_OVERWRITE, D3DWDDM1_3DDI_TILE_COPY_FLAG enumeration [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d10umddi.h
apiname:
-	D3DWDDM1_3DDI_TILE_COPY_FLAG
product: Windows
targetos: Windows
req.typenames: D3DWDDM1_3DDI_TILE_COPY_FLAG
---

# D3DWDDM1_3DDI_TILE_COPY_FLAG enumeration


## -description


Identifies how to copy a tile using the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm1_3ddi_copytiles.md">CopyTiles</a> function.


## -syntax


````
enum D3DWDDM1_3DDI_TILE_COPY_FLAG {
  D3DWDDM1_3DDI_TILE_COPY_NO_OVERWRITE                              = 0x00000001, 
  D3DWDDM1_3DDI_TILE_COPY_LINEAR_BUFFER_TO_SWIZZLED_TILED_RESOURCE  = 0x00000002, 
  D3DWDDM1_3DDI_TILE_COPY_SWIZZLED_TILED_RESOURCE_TO_LINEAR_BUFFER  = 0x00000004 

};
````


## -enum-fields




### -field D3DWDDM1_3DDI_TILE_COPY_NO_OVERWRITE

The GPU isn't currently referencing any of the portions of destination memory being written.


### -field D3DWDDM1_3DDI_TILE_COPY_LINEAR_BUFFER_TO_SWIZZLED_TILED_RESOURCE

The <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm1_3ddi_copytiles.md">CopyTiles</a> operation involves copying a linear buffer to a swizzled tiled resource. This means to copy tile data from the specified buffer location, reading tiles sequentially, to the specified tile region (in <i>x</i>, <i>y</i>, <i>z</i> order if the region is a box), swizzling to optimal hardware memory layout as needed. In this <i>CopyTiles</i> call, you specify the source data with the <i>hBuffer</i> parameter and the destination with the <i>hTiledResource</i> parameter.


### -field D3DWDDM1_3DDI_TILE_COPY_SWIZZLED_TILED_RESOURCE_TO_LINEAR_BUFFER

The <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm1_3ddi_copytiles.md">CopyTiles</a> operation involves copying a swizzled tiled resource to a linear buffer. This means to copy tile data from the tile region, reading tiles sequentially (in <i>x</i>, <i>y</i>, <i>z</i> order if the region is a box), to the specified buffer location, deswizzling to linear memory layout as needed. In this <i>CopyTiles</i> call, you specify the source data with the <i>hTiledResource</i> parameter and the destination with the <i>hBuffer</i> parameter.


## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm1_3ddi_copytiles.md">CopyTiles</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DWDDM1_3DDI_TILE_COPY_FLAG enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

