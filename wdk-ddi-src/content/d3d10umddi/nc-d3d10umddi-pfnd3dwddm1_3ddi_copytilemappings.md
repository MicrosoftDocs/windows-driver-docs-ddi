---
UID: NC:d3d10umddi.PFND3DWDDM1_3DDI_COPYTILEMAPPINGS
title: PFND3DWDDM1_3DDI_COPYTILEMAPPINGS
author: windows-driver-content
description: Copies mappings from a source tiled resource to a destination tiled resource.
old-location: display\copytilemappings.htm
old-project: display
ms.assetid: CB2CE5E7-DDD4-4782-BB91-67A2C562A975
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _SETRESULT_INFO, *PSETRESULT_INFO, SETRESULT_INFO
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
req.alt-api: CopyTileMappings
req.alt-loc: D3d10umddi.h
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
req.typenames: *PSETRESULT_INFO, SETRESULT_INFO
---

# PFND3DWDDM1_3DDI_COPYTILEMAPPINGS callback



## -description
Copies mappings from a source tiled resource to a destination tiled resource.



## -prototype

````
PFND3DWDDM1_3DDI_COPYTILEMAPPINGS CopyTileMappings;

VOID APIENTRY* CopyTileMappings(
             D3D10DDI_HDEVICE                        hDevice,
             D3D10DDI_HRESOURCE                      hDestTiledResource,
  _In_ const D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE *pDestRegionStartCoord,
             D3D10DDI_HRESOURCE                      hSourceTiledResource,
  _In_ const D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE *pSourceRegionStartCoord,
  _In_ const D3DWDDM1_3DDI_TILE_REGION_SIZE          *pTileRegionSize,
             UINT                                    Flags
)
{ ... }
````


## -parameters

### -param hDevice 

A handle to the display device (graphics context).


### -param hDestTiledResource 

A handle to the destination tiled resource.


### -param pDestRegionStartCoord [in]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm1_3ddi_tiled_resource_coordinate.md">D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</a> structure that describes the starting coordinates of the destination tiled resource.


### -param hSourceTiledResource 

A handle to the source tiled resource.




### -param pSourceRegionStartCoord [in]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm1_3ddi_tiled_resource_coordinate.md">D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</a> structure that describes the starting coordinates of the source tiled resource.


### -param pTileRegionSize [in]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm1_3ddi_tile_region_size.md">D3DWDDM1_3DDI_TILE_REGION_SIZE</a> structure that describes the size of the tiled region.


### -param Flags 

A combination of <a href="..\d3d10umddi\ne-d3d10umddi-d3dwddm1_3ddi_tile_mapping_flag.md">D3DWDDM1_3DDI_TILE_MAPPING_FLAG</a> values that are combined by using a bitwise <b>OR</b> operation.


## -returns
None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. The driver can set <b>E_INVALIDARG</b> if an input parameter does not exist or is <b>NULL</b>.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\ne-d3d10umddi-d3dwddm1_3ddi_tile_mapping_flag.md">D3DWDDM1_3DDI_TILE_MAPPING_FLAG</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm1_3ddi_tile_region_size.md">D3DWDDM1_3DDI_TILE_REGION_SIZE</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm1_3ddi_tiled_resource_coordinate.md">D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DWDDM1_3DDI_COPYTILEMAPPINGS callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

