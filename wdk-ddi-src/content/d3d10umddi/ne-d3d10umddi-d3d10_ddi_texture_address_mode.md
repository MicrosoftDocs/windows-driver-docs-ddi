---
UID: NE:d3d10umddi.D3D10_DDI_TEXTURE_ADDRESS_MODE
title: D3D10_DDI_TEXTURE_ADDRESS_MODE
author: windows-driver-content
description: The D3D10_DDI_TEXTURE_ADDRESS_MODE enumeration type contains values that identify the texture address mode of a sampler.
old-location: display\d3d10_ddi_texture_address_mode.htm
old-project: display
ms.assetid: 96bbba03-97c1-43f2-bf3e-902de77d5eb9
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D10_DDI_TEXTURE_ADDRESS_BORDER, D3D10_DDI_TEXTURE_ADDRESS_CLAMP, D3D10_DDI_TEXTURE_ADDRESS_MIRROR, D3D10_DDI_TEXTURE_ADDRESS_MIRRORONCE, D3D10_DDI_TEXTURE_ADDRESS_MODE, D3D10_DDI_TEXTURE_ADDRESS_MODE enumeration [Display Devices], D3D10_DDI_TEXTURE_ADDRESS_WRAP, UMDisplayDriver_Dx10param_Structs_11f66184-ba3e-4c13-869b-d810c97b1878.xml, d3d10umddi/D3D10_DDI_TEXTURE_ADDRESS_BORDER, d3d10umddi/D3D10_DDI_TEXTURE_ADDRESS_CLAMP, d3d10umddi/D3D10_DDI_TEXTURE_ADDRESS_MIRROR, d3d10umddi/D3D10_DDI_TEXTURE_ADDRESS_MIRRORONCE, d3d10umddi/D3D10_DDI_TEXTURE_ADDRESS_MODE, d3d10umddi/D3D10_DDI_TEXTURE_ADDRESS_WRAP, display.d3d10_ddi_texture_address_mode
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d10umddi.h
api_name:
-	D3D10_DDI_TEXTURE_ADDRESS_MODE
product:
- Windows
targetos: Windows
req.typenames: D3D10_DDI_TEXTURE_ADDRESS_MODE
---

# D3D10_DDI_TEXTURE_ADDRESS_MODE enumeration


## -description


The D3D10_DDI_TEXTURE_ADDRESS_MODE enumeration type contains values that identify the texture address mode of a sampler.


## -enum-fields




### -field D3D10_DDI_TEXTURE_ADDRESS_WRAP

Tile the texture at every integer junction. For example, for u values between 0 and 3, the texture is repeated three times; no mirroring is performed.


### -field D3D10_DDI_TEXTURE_ADDRESS_MIRROR

Similar to D3D10_DDI_TEXTURE_ADDRESS_WRAP, except that the texture is flipped at every integer junction. For u values between 0 and 1, for example, the texture is addressed normally; between 1 and 2, the texture is flipped (mirrored); and between 2 and 3, the texture is normal again, and so on.


### -field D3D10_DDI_TEXTURE_ADDRESS_CLAMP

Texture coordinates outside the range [0.0, 1.0] are set to the texture color at 0.0 or 1.0, respectively.


### -field D3D10_DDI_TEXTURE_ADDRESS_BORDER

Texture coordinates outside the range [0.0, 1.0] are set to the border color.


### -field D3D10_DDI_TEXTURE_ADDRESS_MIRRORONCE

Similar to D3D10_DDI_TEXTURE_ADDRESS_MIRROR and D3D10_DDI_TEXTURE_ADDRESS_CLAMP. Takes the absolute value of the texture coordinate (thus, mirroring around 0), and then clamps to the maximum value. The most common usage of D3D10_DDI_TEXTURE_ADDRESS_MIRRORONCE is for volume textures, where support for the full D3D10_DDI_TEXTURE_ADDRESS_MIRRORONCE texture-addressing mode is not necessary, but the data is symmetric around the one axis.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542011">D3D10_DDI_SAMPLER_DESC</a>
 

 

