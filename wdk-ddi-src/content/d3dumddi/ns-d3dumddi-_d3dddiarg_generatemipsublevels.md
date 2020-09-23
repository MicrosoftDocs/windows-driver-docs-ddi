---
UID: NS:d3dumddi._D3DDDIARG_GENERATEMIPSUBLEVELS
title: _D3DDDIARG_GENERATEMIPSUBLEVELS (d3dumddi.h)
description: The D3DDDIARG_GENERATEMIPSUBLEVELS structure describes how to generate the sublevels of a MIP-map texture.
old-location: display\d3dddiarg_generatemipsublevels.htm
tech.root: display
ms.assetid: 19c08206-cde8-4ec2-bbd1-92eadeecdb90
ms.date: 05/10/2018
keywords: ["D3DDDIARG_GENERATEMIPSUBLEVELS structure"]
ms.keywords: D3DDDIARG_GENERATEMIPSUBLEVELS, D3DDDIARG_GENERATEMIPSUBLEVELS structure [Display Devices], UMDisplayDriver_param_Structs_4000d18b-18c0-4499-bfbe-a3f5e866553b.xml, _D3DDDIARG_GENERATEMIPSUBLEVELS, d3dumddi/D3DDDIARG_GENERATEMIPSUBLEVELS, display.d3dddiarg_generatemipsublevels
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
targetos: Windows
req.typenames: D3DDDIARG_GENERATEMIPSUBLEVELS
f1_keywords:
 - _D3DDDIARG_GENERATEMIPSUBLEVELS
 - d3dumddi/_D3DDDIARG_GENERATEMIPSUBLEVELS
 - D3DDDIARG_GENERATEMIPSUBLEVELS
 - d3dumddi/D3DDDIARG_GENERATEMIPSUBLEVELS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - D3DDDIARG_GENERATEMIPSUBLEVELS
---

# _D3DDDIARG_GENERATEMIPSUBLEVELS structure


## -description

The D3DDDIARG_GENERATEMIPSUBLEVELS structure describes how to generate the sublevels of a MIP-map texture.

## -struct-fields

### -field hResource

[in] A handle to the MIP-map texture surface.

### -field Filter

[in] A D3DDDITEXTUREFILTERTYPE-typed value that indicates the texture magnification or minification filter type that is used in generating the sublevels of the MIP-map texture. This member can be one of the following values.

| **Value** | **Meaning** | 
|:--|:--|
| D3DDDITEXF_NONE | MIP-map filtering is disabled. | 
| D3DDDITEXF_POINT | Point filtering. The texel with coordinates that are nearest to the required pixel value is used. The texture filter to be used between MIP-map levels is nearest-point MIP-map filtering. | 
| D3DDDITEXF_LINEAR | Bilinear-interpolation filtering. A weighted average of a 2x2 area of texels that surround the required pixel is used. The texture filter to use between MIP-map levels is trilinear MIP-map interpolation. | 
| D3DDDITEXF_ANISOTROPIC | Anisotropic texture filtering. This filtering compensates for distortion that is caused by the difference in angle between the texture polygon and the plane of the screen. | 
| D3DDDITEXF_PYRAMIDALQUAD | Four-sample tent filtering. |

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_generatemipsublevels">GenerateMipSubLevels</a>