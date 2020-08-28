---
UID: NS:d3d10umddi.D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW
title: D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW (d3d10umddi.h)
description: The D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW structure describes a three-dimensional (3-D) texture that is used to create a shader resource view in a call to the CreateShaderResourceView function.
old-location: display\d3d10ddiarg_tex3d_shaderresourceview.htm
ms.assetid: 2b7d930e-7003-4875-8a2b-6ce50ea606c8
ms.date: 05/10/2018
keywords: ["D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW structure"]
ms.keywords: D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW, D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW structure [Display Devices], UMDisplayDriver_Dx10param_Structs_b3c96163-7085-43eb-a8da-84f0f824e069.xml, d3d10umddi/D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW, display.d3d10ddiarg_tex3d_shaderresourceview
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
targetos: Windows
tech.root: display
req.typenames: D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW
f1_keywords:
 - D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW
 - d3d10umddi/D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW
---

# D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW structure


## -description

The D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW structure describes a three-dimensional (3-D) texture that is used to create a shader resource view in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createshaderresourceview">CreateShaderResourceView</a> function.

## -struct-fields

### -field MostDetailedMip

[in] The identifier of the most detailed MIP-map.

### -field MipLevels

[in] The number of MIP-map levels for the texture.

## -remarks

If the <b>MipLevels</b> member is set to -1, the MIP-maps in the texture start from the MIP-map that is set in the <b>MostDetailedMip</b> member.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivateshaderresourceviewsize">CalcPrivateShaderResourceViewSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createshaderresourceview">CreateShaderResourceView</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createshaderresourceview">D3D10DDIARG_CREATESHADERRESOURCEVIEW</a>

