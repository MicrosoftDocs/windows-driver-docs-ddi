---
UID: NS:d3dhal._D3DHAL_DP2BLT
title: _D3DHAL_DP2BLT (d3dhal.h)
description: DirectX 9.0 and later versions only. D3DHAL_DP2BLT is used for two dimensional surface blts when D3dDrawPrimitives2 responds to the D3DDP2OP_BLT command token.
old-location: display\d3dhal_dp2blt.htm
tech.root: display
ms.assetid: 2d0cdc50-a194-4eda-8bba-f6e5c06ff32c
ms.date: 05/10/2018
keywords: ["_D3DHAL_DP2BLT structure"]
ms.keywords: "*LPD3DHAL_DP2BLT, D3DHAL_DP2BLT, D3DHAL_DP2BLT structure [Display Devices], LPD3DHAL_DP2BLT, LPD3DHAL_DP2BLT structure pointer [Display Devices], _D3DHAL_DP2BLT, d3dhal/D3DHAL_DP2BLT, d3dhal/LPD3DHAL_DP2BLT, d3dstrct_cab5e8b8-ec72-4d7d-8aaa-4a1f6da44a9b.xml, display.d3dhal_dp2blt"
f1_keywords:
 - "d3dhal/D3DHAL_DP2BLT"
 - "D3DHAL_DP2BLT"
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
- D3DHAL_DP2BLT
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2BLT
---

# _D3DHAL_DP2BLT structure


## -description



   DirectX 9.0 and later versions only.
   

D3DHAL_DP2BLT is used for two dimensional surface blts when <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> responds to the D3DDP2OP_BLT command token.


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

Specifies a flag that indicates the type of filtering that the driver must perform. This member is set to zero to indicate that the driver can use its own filtering technique or is set to one of the following flags.

|Flag|Meaning|
|--- |--- |
|DP2BLT_LINEAR|Set for linear filtering.|
|DP2BLT_POINT|Set for point filtering.|
 


## -remarks



The <b>dwSource</b> or <b>dwDest</b> member specifies the kernel handle to the top-level surface and the <b>dwSourceMipLevel</b> or <b>dwDestMiplevel</b> member specifies the sublevel for the MIP-map chain where the blt occurs.




## -see-also




D3DDP2OP_BLT



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>
 

 

