---
UID: NS:d3dhal._D3DHAL_DP2GENERATEMIPSUBLEVELS
title: "_D3DHAL_DP2GENERATEMIPSUBLEVELS"
author: windows-driver-content
description: DirectX 9.0 and later versions only. The D3DHAL_DP2GENERATEMIPSUBLEVELS structure is used to inform the driver to automatically generate the sublevels of a given MIP-map texture using a given filter type.
old-location: display\d3dhal_dp2generatemipsublevels.htm
old-project: display
ms.assetid: 7952cf0f-8a05-4d82-9669-db3db504d22d
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*LPD3DHAL_DP2GENERATEMIPSUBLEVELS, D3DHAL_DP2GENERATEMIPSUBLEVELS, D3DHAL_DP2GENERATEMIPSUBLEVELS structure [Display Devices], LPD3DHAL_DP2GENERATEMIPSUBLEVELS, LPD3DHAL_DP2GENERATEMIPSUBLEVELS structure pointer [Display Devices], _D3DHAL_DP2GENERATEMIPSUBLEVELS, d3dhal/D3DHAL_DP2GENERATEMIPSUBLEVELS, d3dhal/LPD3DHAL_DP2GENERATEMIPSUBLEVELS, d3dstrct_0b221ab6-0f8c-4406-9d99-c6101b353223.xml, display.d3dhal_dp2generatemipsublevels"
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
-	D3DHAL_DP2GENERATEMIPSUBLEVELS
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2GENERATEMIPSUBLEVELS
---

# _D3DHAL_DP2GENERATEMIPSUBLEVELS structure


## -description



   DirectX 9.0 and later versions only.
   

The D3DHAL_DP2GENERATEMIPSUBLEVELS structure is used to inform the driver to automatically generate the sublevels of a given MIP-map texture using a given filter type.


## -struct-fields




### -field hSurface

Specifies the surface handle used in the generation.


### -field Filter

Specifies the filter type used in the generation.


## -remarks



To generate the sublevels of a MIP-map texture, the driver receives a D3DDP2OP_GENERATEMIPSUBLEVELS command along with a D3DHAL_DP2GENERATEMIPSUBLEVELS structure. For more information about automatically generating the sublevels of MIP-map textures, see <a href="https://msdn.microsoft.com/fbfb0d1b-468d-4e7f-865e-bdc7d19f5516">Generating Sublevels of MIP Map Textures</a>.




## -see-also




D3DDP2OP_GENERATEMIPSUBLEVELS
 

 

