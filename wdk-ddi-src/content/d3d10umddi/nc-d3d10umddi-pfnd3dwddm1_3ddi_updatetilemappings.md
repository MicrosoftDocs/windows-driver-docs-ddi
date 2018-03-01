---
UID: NC:d3d10umddi.PFND3DWDDM1_3DDI_UPDATETILEMAPPINGS
title: PFND3DWDDM1_3DDI_UPDATETILEMAPPINGS
author: windows-driver-content
description: Updates mappings of tile locations in tiled resources to memory locations in a tile pool.
old-location: display\updatetilemappings.htm
old-project: display
ms.assetid: 1C8FC920-145F-4AE9-B049-F6BDAE29D1F1
ms.author: windowsdriverdev
ms.date: 2/26/2018
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


## -prototype


````
PFND3DWDDM1_3DDI_UPDATETILEMAPPINGS UpdateTileMappings;

VOID APIENTRY* UpdateTileMappings(
                 D3D10DDI_HDEVICE                        hDevice,
                 D3D10DDI_HRESOURCE                      hTiledResource,
                 UINT                                    NumTiledResourceRegions,
  _In_     const D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE *pTiledResourceRegionStartCoords,
  _In_opt_ const D3DWDDM1_3DDI_TILE_REGION_SIZE          *pTiledResourceRegionSizes,
                 D3D10DDI_HRESOURCE                      hTilePool,
                 UINT                                    NumRanges,
  _In_opt_ const UINT                                    *pRangeFlags,
  _In_opt_ const UINT                                    *pTilePoolStartOffsets,
  _In_opt_ const UINT                                    *pRangeTileCounts,
                 UINT                                    Flags
)
{ ... }
````


## -parameters




### -param hDevice

A handle to the display device (graphics context).


### -param hTiledResource

A handle to the tiled resource.


### -param NumTiledResourceRegions

The number of tiled resource regions.


### -param *pTiledResourceRegionStartCoords [in]

An array of <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm1_3ddi_tiled_resource_coordinate.md">D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</a> structures that describe the starting coordinates of the tiled resource regions. The <i>NumTiledResourceRegions</i> parameter specifies the number of <b>D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</b> structures in the array.


### -param *pTiledResourceRegionSizes [in, optional]

An array of <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm1_3ddi_tile_region_size.md">D3DWDDM1_3DDI_TILE_REGION_SIZE</a> structures that describe the sizes of the tiled resource regions. The <i>NumTiledResourceRegions</i> parameter specifies the number of <b>D3DWDDM1_3DDI_TILE_REGION_SIZE</b> structures in the array.


### -param hTilePool

A handle to the tile pool.


### -param NumRanges

The number of tile-pool ranges.


### -param *pRangeFlags [in, optional]

An array of values that describe each tile-pool range. The <i>NumRanges</i> parameter specifies the number of values in the array. Each value can be a combination of values of type <a href="..\d3d10umddi\ne-d3d10umddi-d3dwddm1_3ddi_tile_range_flag.md">D3DWDDM1_3DDI_TILE_RANGE_FLAG</a> combined by using a bitwise <b>OR</b> operation.


### -param *pTilePoolStartOffsets [in, optional]

An array of offsets into the tile pool. These are zero-based tile offsets, counting in tiles (not bytes).


### -param *pRangeTileCounts [in, optional]

An array of values that specify the number of tiles in each tile-pool range. The <i>NumRanges</i> parameter specifies the number of values in the array.


### -param Flags

A combination of <a href="..\d3d10umddi\ne-d3d10umddi-d3dwddm1_3ddi_tile_mapping_flag.md">D3DWDDM1_3DDI_TILE_MAPPING_FLAG</a> values that are combined by using a bitwise <b>OR</b> operation.


## -returns



None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. The driver can set <b>E_INVALIDARG</b> if a required input parameter does not exist or is <b>NULL</b>.




## -see-also

<a href="..\d3d10umddi\ne-d3d10umddi-d3dwddm1_3ddi_tile_mapping_flag.md">D3DWDDM1_3DDI_TILE_MAPPING_FLAG</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3dwddm1_3ddi_tile_range_flag.md">D3DWDDM1_3DDI_TILE_RANGE_FLAG</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm1_3ddi_tiled_resource_coordinate.md">D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm1_3ddi_tile_region_size.md">D3DWDDM1_3DDI_TILE_REGION_SIZE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DWDDM1_3DDI_UPDATETILEMAPPINGS callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

