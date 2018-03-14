---
UID: NC:d3dumddi.PFND3DDDI_TEXBLT1
title: PFND3DDDI_TEXBLT1
author: windows-driver-content
description: Performs a bit-block transfer (bitblt) operation from a source texture to a destination texture, including all of the sublevels of the source texture. Implemented by Windows Display Driver Model (WDDM) 1.2 or later user-mode display drivers.
old-location: display\texblt1.htm
old-project: display
ms.assetid: 63EE8130-47E5-4976-8A72-1B11136B1192
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DDDI_TEXBLT1, TexBlt1, TexBlt1 callback function [Display Devices], d3dumddi/TexBlt1, display.texblt1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	d3dumddi.h
api_name:
-	TexBlt1
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_TEXBLT1 callback


## -description


Performs a bit-block transfer (bitblt) operation from a source texture to a destination texture, including all of the sublevels of the source texture. Implemented by Windows Display Driver Model (WDDM) 1.2 or later user-mode display drivers.


## -prototype


````
PFND3DDDI_TEXBLT1 TexBlt1;

__checkReturn HRESULT APIENTRY* TexBlt1(
  _In_       HANDLE            hDevice,
  _In_ const D3DDDIARG_TEXBLT1 *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_texblt1.md">D3DDDIARG_TEXBLT1</a> structure that defines the parameters for the texture bitblt operation.


## -returns



Returns S_OK or an appropriate error result if the texture bitblt operation is not successfully performed.




## -remarks



The Microsoft Direct3D runtime calls the user-mode display driver's <i>TexBlt</i> function to inform the driver to perform a bitblt operation from a source texture to a destination texture. A texture can also be a cubic environment map. The driver should copy the rectangle that is specified by the <b>SrcRect</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_texblt.md">D3DDDIARG_TEXBLT</a> structure in the source texture to the location that is specified by the <b>DstPoint</b> member of D3DDDIARG_TEXBLT in the destination texture. The destination and source textures are identified by the <b>hDstResource</b> and <b>hSrcResource</b> handles of D3DDDIARG_TEXBLT, respectively. 

For MIP-mapped textures, the driver must also copy all of the MIP-map sublevels that are present in the source texture. The source and destination textures might possibly contain different numbers of MIP-map levels. In this situation, the driver should copy the common levels. For example, if a 256x256 source texture has eight MIP-map levels, and if the destination is a 64x64 texture with six levels, the driver should copy the six corresponding levels from the source. Note that the dimensions of the top MIP level of the destination texture is always less than or equal to the dimensions of the top MIP level of the source texture.

The source and destination handles always refer to the top-level surfaces and never to any MIP-map sublevel. 

To copy an arbitrary level of a MIP-map texture, the runtime calls the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_blt.md">Blt</a> function instead.

The pixel formats of the source and destination textures are identical and, in general, the specified bitblt operation is safe to perform. 




## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_blt.md">Blt</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_texblt1.md">D3DDDIARG_TEXBLT1</a>



 

 


