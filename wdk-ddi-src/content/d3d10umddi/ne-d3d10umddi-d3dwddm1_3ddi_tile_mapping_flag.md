---
UID: NE:d3d10umddi.D3DWDDM1_3DDI_TILE_MAPPING_FLAG
title: D3DWDDM1_3DDI_TILE_MAPPING_FLAG
author: windows-driver-content
description: Indicates how to update a tile mapping.
old-location: display\d3dwddm1_3ddi_tile_mapping_flag.htm
ms.assetid: 1149547D-9165-42AA-B12A-5C7681A8EAC1
ms.date: 5/10/2018
ms.keywords: D3DWDDM1_3DDI_TILE_MAPPING_FLAG, D3DWDDM1_3DDI_TILE_MAPPING_FLAG enumeration [Display Devices], D3DWDDM1_3DDI_TILE_MAPPING_NO_OVERWRITE, d3d10umddi/D3DWDDM1_3DDI_TILE_MAPPING_FLAG, d3d10umddi/D3DWDDM1_3DDI_TILE_MAPPING_NO_OVERWRITE, display.d3dwddm1_3ddi_tile_mapping_flag
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
-	D3DWDDM1_3DDI_TILE_MAPPING_FLAG
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DWDDM1_3DDI_TILE_MAPPING_FLAG
---

# D3DWDDM1_3DDI_TILE_MAPPING_FLAG enumeration


## -description


Indicates how to update a tile mapping.


## -enum-fields




### -field D3DWDDM1_3DDI_TILE_MAPPING_NO_OVERWRITE

Previously submitted commands to the 
device that may still be executing do not reference any of the tile region being updated.
This allows the device to avoid having to flush previously submitted work in order to update a tile mapping.

