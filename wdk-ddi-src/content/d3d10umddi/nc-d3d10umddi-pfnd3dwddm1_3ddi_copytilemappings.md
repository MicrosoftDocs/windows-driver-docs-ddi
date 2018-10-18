---
UID: NC:d3d10umddi.PFND3DWDDM1_3DDI_COPYTILEMAPPINGS
title: PFND3DWDDM1_3DDI_COPYTILEMAPPINGS
author: windows-driver-content
description: Copies mappings from a source tiled resource to a destination tiled resource.
old-location: display\copytilemappings.htm
ms.assetid: CB2CE5E7-DDD4-4782-BB91-67A2C562A975
ms.date: 5/10/2018
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d10umddi.h
api_name:
-	CopyTileMappings
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3DWDDM1_3DDI_COPYTILEMAPPINGS callback function


## -description


Copies mappings from a source tiled resource to a destination tiled resource.


## -parameters




### -param hDevice

A handle to the display device (graphics context).


### -param hDestTiledResource

A handle to the destination tiled resource.


### -param *pDestRegionStartCoord [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn440996">D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</a> structure that describes the starting coordinates of the destination tiled resource.


### -param hSourceTiledResource

A handle to the source tiled resource.




### -param *pSourceRegionStartCoord [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn440996">D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</a> structure that describes the starting coordinates of the source tiled resource.


### -param *pTileRegionSize [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn440997">D3DWDDM1_3DDI_TILE_REGION_SIZE</a> structure that describes the size of the tiled region.


### -param Flags

A combination of <a href="https://msdn.microsoft.com/library/windows/hardware/dn458990">D3DWDDM1_3DDI_TILE_MAPPING_FLAG</a> values that are combined by using a bitwise <b>OR</b> operation.


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. The driver can set <b>E_INVALIDARG</b> if an input parameter does not exist or is <b>NULL</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn440996">D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn458990">D3DWDDM1_3DDI_TILE_MAPPING_FLAG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn440997">D3DWDDM1_3DDI_TILE_REGION_SIZE</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

