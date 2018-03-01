---
UID: NC:d3d10umddi.PFND3DWDDM1_3DDI_UPDATETILES
title: PFND3DWDDM1_3DDI_UPDATETILES
author: windows-driver-content
description: Updates tiles by copying from app memory to the tiled resource.
old-location: display\updatetiles.htm
old-project: display
ms.assetid: 4891AB01-DE51-4B32-AA52-5619E86CC474
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PFND3DWDDM1_3DDI_UPDATETILES, UpdateTiles, UpdateTiles callback function [Display Devices], d3d10umddi/UpdateTiles, display.updatetiles
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
-	UpdateTiles
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3DWDDM1_3DDI_UPDATETILES callback


## -description


Updates tiles by copying from app memory to the tiled resource.


## -prototype


````
PFND3DWDDM1_3DDI_UPDATETILES UpdateTiles;

VOID APIENTRY* UpdateTiles(
             D3D10DDI_HDEVICE                        hDevice,
             D3D10DDI_HRESOURCE                      hDestTiledResource,
  _In_ const D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE *pDestTileRegionStartCoord,
  _In_ const D3DWDDM1_3DDI_TILE_REGION_SIZE          *pDestTileRegionSize,
  _In_ const VOID                                    *pSourceTileData,
             UINT                                    Flags
)
{ ... }
````


## -parameters




### -param hDevice

A handle to the display device (graphics context).


### -param hDestTiledResource

A handle to the tiled resource.


### -param *pDestTileRegionStartCoord [in]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm1_3ddi_tiled_resource_coordinate.md">D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</a> structure that describes the starting coordinates of the tiled resource.




### -param *pDestTileRegionSize [in]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm1_3ddi_tile_region_size.md">D3DWDDM1_3DDI_TILE_REGION_SIZE</a> structure that describes the size of the tiled region.




### -param *pSourceTileData [in]

A pointer to memory that contains the source tile data that this function uses to update the tiled resource.


### -param Flags

A combination of values of type <a href="..\d3d10umddi\ne-d3d10umddi-d3dwddm1_3ddi_tile_copy_flag.md">D3DWDDM1_3DDI_TILE_COPY_FLAG</a> that are combined by using a bitwise <b>OR</b> operation. The only valid value is <b>D3DWDDM1_3DDI_TILE_COPY_NO_OVERWRITE</b>. The other enumeration constant values aren't meaningful here, though by definition using  <b>D3DWDDM1_3DDI_TILE_COPY_SWIZZLED_TILED_RESOURCE_TO_LINEAR_BUFFER</b> results in what the <i>UpdateTiles</i> function does, sourcing from app memory.


## -returns



None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code.

The Direct3D runtime does not expect this function to fail.




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm1_3ddi_tiled_resource_coordinate.md">D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm1_3ddi_tile_region_size.md">D3DWDDM1_3DDI_TILE_REGION_SIZE</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3dwddm1_3ddi_tile_copy_flag.md">D3DWDDM1_3DDI_TILE_COPY_FLAG</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm1_3ddi_updatetiles.md">UpdateTiles</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DWDDM1_3DDI_UPDATETILES callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

