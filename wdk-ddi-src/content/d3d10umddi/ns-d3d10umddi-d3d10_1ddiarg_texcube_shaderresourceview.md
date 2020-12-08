---
UID: NS:d3d10umddi.D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW
title: D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW (d3d10umddi.h)
description: The D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW structure describes cube textures that are used to create a shader resource view in a call to the CreateShaderResourceView(D3D10_1) function.
old-location: display\d3d10_1ddiarg_texcube_shaderresourceview.htm
ms.date: 05/10/2018
keywords: ["D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW structure"]
ms.keywords: D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW, D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW structure [Display Devices], UMDisplayDriver_Dx10param_Structs_4988e1af-5552-4f7c-be15-5c54f88b9975.xml, d3d10umddi/D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW, display.d3d10_1ddiarg_texcube_shaderresourceview
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW is supported on Windows Vista with Service Pack 1 (SP1) and later versions and Windows Server 2008 and later versions.
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
req.typenames: D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW
f1_keywords:
 - D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW
 - d3d10umddi/D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW
---

# D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW structure


## -description

The D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW structure describes cube textures that are used to create a shader resource view in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10_1ddi_createshaderresourceview">CreateShaderResourceView(D3D10_1)</a> function.

## -struct-fields

### -field MostDetailedMip

[in] The identifier of the most detailed MIP-map.

### -field MipLevels

[in] The number of MIP-map levels for the texture.

### -field First2DArrayFace

[in] The identifier of the first 2-D texture that comprises one or more cube textures.

### -field NumCubes

[in] The number of cube textures for a shader resource view.

## -remarks

The value in the <b>First2DArrayFace</b> member added with 6 multiplied by the number in the <b>NumCubes</b> member must be less than or equal to the value in the <b>ArraySize</b> member of the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createresource">D3D10DDIARG_CREATERESOURCE</a> structure for the shader resource whose view is created in a call to the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10_1ddi_createshaderresourceview">CreateShaderResourceView(D3D10_1)</a> function. That is, the following calculation applies:

```cpp
::First2DArrayFace + 6 * ::NumCubes <= Resource ::ArraySize
```

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10_1ddi_calcprivateshaderresourceviewsize">CalcPrivateShaderResourceViewSize(D3D10_1)</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10_1ddi_createshaderresourceview">CreateShaderResourceView(D3D10_1)</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createresource">D3D10DDIARG_CREATERESOURCE</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_1ddiarg_createshaderresourceview">D3D10_1DDIARG_CREATESHADERRESOURCEVIEW</a>
