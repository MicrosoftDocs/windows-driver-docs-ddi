---
UID: NS:d3d10umddi.D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE
title: D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE
author: windows-driver-content
description: Specifies the (x, y, z) coordinate values below the index tiles of a tiled resource, along with the respective subresource. Note that the coordinate values do not indicate pixels or bytes.
old-location: display\d3dwddm1_3ddi_tiled_resource_coordinate.htm
old-project: display
ms.assetid: A927CAF9-EF7F-47CC-9BDE-B6E13597368E
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE, D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE structure [Display Devices], d3d10umddi/D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE, display.d3dwddm1_3ddi_tiled_resource_coordinate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE
product:
- Windows
targetos: Windows
req.typenames: D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE
---

# D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE structure


## -description


Specifies the (<i>x</i>, <i>y</i>, <i>z</i>) coordinate values below the index tiles  of a tiled resource, along with the respective subresource. Note that the coordinate values do not indicate pixels or bytes.


## -struct-fields




### -field X

The <i>x</i> coordinate of the tiled resource. Used for buffer, 1-D, 2-D, and 3-D rendering.


### -field Y

The <i>y</i> coordinate of the tiled resource. Used for 2-D and 3-D rendering.


### -field Z

The <i>z</i> coordinate of the tiled resource. Used for 3-D rendering.


### -field Subresource

The subresource of the tiled resource. Used to index into mipmaps and arrays for 1-D, 2-D, and 3-D rendering.

If mipmaps are packed into a single tile, any subresource value that indicates any of the packed mipmaps refers to the same tile.

