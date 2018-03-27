---
UID: NS:d3dhal._D3DHAL_DP2SURFACEBLT
title: "_D3DHAL_DP2SURFACEBLT"
author: windows-driver-content
description: DirectX 9.0 and later versions only. D3DHAL_DP2SURFACEBLT is used for two dimensional system memory to video memory surface blts when D3dDrawPrimitives2 responds to the D3DDP2OP_SURFACEBLT command token.
old-location: display\d3dhal_dp2surfaceblt.htm
old-project: display
ms.assetid: 0720635c-77a2-4391-ba75-b276c0d457d5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPD3DHAL_DP2SURFACEBLT, D3DHAL_DP2SURFACEBLT, D3DHAL_DP2SURFACEBLT structure [Display Devices], LPD3DHAL_DP2SURFACEBLT, LPD3DHAL_DP2SURFACEBLT structure pointer [Display Devices], _D3DHAL_DP2SURFACEBLT, d3dhal/D3DHAL_DP2SURFACEBLT, d3dhal/LPD3DHAL_DP2SURFACEBLT, d3dstrct_705cb760-39d7-4953-b249-0b9a9358f0df.xml, display.d3dhal_dp2surfaceblt"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dhal.h
api_name:
-	D3DHAL_DP2SURFACEBLT
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2SURFACEBLT
---

# _D3DHAL_DP2SURFACEBLT structure


## -description



   DirectX 9.0 and later versions only.
   

D3DHAL_DP2SURFACEBLT is used for two dimensional system memory to video memory surface blts when <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a> responds to the D3DDP2OP_SURFACEBLT command token.


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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a>



<a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2SURFACEBLT structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

