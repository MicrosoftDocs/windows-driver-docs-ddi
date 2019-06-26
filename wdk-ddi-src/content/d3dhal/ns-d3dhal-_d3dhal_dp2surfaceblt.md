---
UID: NS:d3dhal._D3DHAL_DP2SURFACEBLT
title: _D3DHAL_DP2SURFACEBLT (d3dhal.h)
description: DirectX 9.0 and later versions only. D3DHAL_DP2SURFACEBLT is used for two dimensional system memory to video memory surface blts when D3dDrawPrimitives2 responds to the D3DDP2OP_SURFACEBLT command token.
old-location: display\d3dhal_dp2surfaceblt.htm
tech.root: display
ms.assetid: 0720635c-77a2-4391-ba75-b276c0d457d5
ms.date: 05/10/2018
ms.keywords: "*LPD3DHAL_DP2SURFACEBLT, D3DHAL_DP2SURFACEBLT, D3DHAL_DP2SURFACEBLT structure [Display Devices], LPD3DHAL_DP2SURFACEBLT, LPD3DHAL_DP2SURFACEBLT structure pointer [Display Devices], _D3DHAL_DP2SURFACEBLT, d3dhal/D3DHAL_DP2SURFACEBLT, d3dhal/LPD3DHAL_DP2SURFACEBLT, d3dstrct_705cb760-39d7-4953-b249-0b9a9358f0df.xml, display.d3dhal_dp2surfaceblt"
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dhal.h
api_name:
- D3DHAL_DP2SURFACEBLT
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2SURFACEBLT
---

# _D3DHAL_DP2SURFACEBLT structure


## -description



   DirectX 9.0 and later versions only.
   

D3DHAL_DP2SURFACEBLT is used for two dimensional system memory to video memory surface blts when <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> responds to the D3DDP2OP_SURFACEBLT command token.


## -struct-fields




### -field dwSource

Specifies the handle to the source surface.


### -field rSource

Specifies a RECTL structure that specifies the upper left and lower right points of a rectangle on the source surface. These points define the area of the source blit data and its position on the source surface.


### -field dwSourceMipLevel

Specifies the sublevel of a MIP-map texture that is the source of the blt.


### -field dwDest

Specifies the handle to the destination surface.


### -field rDest

Specifies a RECTL structure that specifies the upper left and lower right points of a rectangle on the destination surface. These points define the area in which the blit should occur and its position on the destination surface.


### -field dwDestMipLevel

Specifies the sublevel of a MIP-map texture that is the destination for the blt.


### -field Flags

Unused


## -remarks



The D3DDP2OP_SURFACEBLT operation code is identical to the D3DDP2OP_BLT operation code except that D3DDP2OP_SURFACEBLT is only used to copy system memory to video memory and is never used for stretch blts or color conversion. Because D3DDP2OP_SURFACEBLT is not used for stretch blts, no flags are currently defined.

The <b>dwSource</b> or <b>dwDest</b> member specifies the kernel handle to the top-level surface and the <b>dwSourceMipLevel</b> or <b>dwDestMiplevel</b> member specifies the sublevel for the MIP-map chain where the blt occurs.




## -see-also




D3DDP2OP_BLT



D3DDP2OP_SURFACEBLT



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>
 

 

