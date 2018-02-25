---
UID: NE:d3d10umddi.D3D10_DDI_TEXTURE_ADDRESS_MODE
title: D3D10_DDI_TEXTURE_ADDRESS_MODE
author: windows-driver-content
description: The D3D10_DDI_TEXTURE_ADDRESS_MODE enumeration type contains values that identify the texture address mode of a sampler.
old-location: display\d3d10_ddi_texture_address_mode.htm
old-project: display
ms.assetid: 96bbba03-97c1-43f2-bf3e-902de77d5eb9
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 0, 1, 3, A, D, D3D10_DDI_TEXTURE_ADDRESS_BORDER, D3D10_DDI_TEXTURE_ADDRESS_CLAMP, D3D10_DDI_TEXTURE_ADDRESS_MIRROR, D3D10_DDI_TEXTURE_ADDRESS_MIRRORONCE, D3D10_DDI_TEXTURE_ADDRESS_MODE, D3D10_DDI_TEXTURE_ADDRESS_MODE enumeration [Display Devices], D3D10_DDI_TEXTURE_ADDRESS_WRAP, E, I, M, O, R, S, T, U, UMDisplayDriver_Dx10param_Structs_11f66184-ba3e-4c13-869b-d810c97b1878.xml, X, _, d3d10umddi/D3D10_DDI_TEXTURE_ADDRESS_BORDER, d3d10umddi/D3D10_DDI_TEXTURE_ADDRESS_CLAMP, d3d10umddi/D3D10_DDI_TEXTURE_ADDRESS_MIRROR, d3d10umddi/D3D10_DDI_TEXTURE_ADDRESS_MIRRORONCE, d3d10umddi/D3D10_DDI_TEXTURE_ADDRESS_MODE, d3d10umddi/D3D10_DDI_TEXTURE_ADDRESS_WRAP, display.d3d10_ddi_texture_address_mode"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3d10umddi.h
apiname:
-	D3D10_DDI_TEXTURE_ADDRESS_MODE
product: Windows
targetos: Windows
req.typenames: D3D10_DDI_TEXTURE_ADDRESS_MODE
---

# D3D10_DDI_TEXTURE_ADDRESS_MODE enumeration


## -description


The D3D10_DDI_TEXTURE_ADDRESS_MODE enumeration type contains values that identify the texture address mode of a sampler.


## -syntax


````
typedef enum D3D10_DDI_TEXTURE_ADDRESS_MODE { 
  D3D10_DDI_TEXTURE_ADDRESS_WRAP        = 1,
  D3D10_DDI_TEXTURE_ADDRESS_MIRROR      = 2,
  D3D10_DDI_TEXTURE_ADDRESS_CLAMP       = 3,
  D3D10_DDI_TEXTURE_ADDRESS_BORDER      = 4,
  D3D10_DDI_TEXTURE_ADDRESS_MIRRORONCE  = 5
} D3D10_DDI_TEXTURE_ADDRESS_MODE;
````


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

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10_ddi_sampler_desc.md">D3D10_DDI_SAMPLER_DESC</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_DDI_TEXTURE_ADDRESS_MODE enumeration%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

