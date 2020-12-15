---
UID: NS:d3d10umddi.D3D10DDIARG_TEX2D_RENDERTARGETVIEW
title: D3D10DDIARG_TEX2D_RENDERTARGETVIEW (d3d10umddi.h)
description: The D3D10DDIARG_TEX2D_RENDERTARGETVIEW structure describes a two-dimensional (2-D) texture that is used to create a render target view in a call to the CreateRenderTargetView function.
old-location: display\d3d10ddiarg_tex2d_rendertargetview.htm
ms.date: 05/10/2018
keywords: ["D3D10DDIARG_TEX2D_RENDERTARGETVIEW structure"]
ms.keywords: D3D10DDIARG_TEX2D_RENDERTARGETVIEW, D3D10DDIARG_TEX2D_RENDERTARGETVIEW structure [Display Devices], UMDisplayDriver_Dx10param_Structs_542468b2-b74d-4146-b745-65727ecd9510.xml, d3d10umddi/D3D10DDIARG_TEX2D_RENDERTARGETVIEW, display.d3d10ddiarg_tex2d_rendertargetview
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
req.typenames: D3D10DDIARG_TEX2D_RENDERTARGETVIEW
f1_keywords:
 - D3D10DDIARG_TEX2D_RENDERTARGETVIEW
 - d3d10umddi/D3D10DDIARG_TEX2D_RENDERTARGETVIEW
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D10DDIARG_TEX2D_RENDERTARGETVIEW
---

# D3D10DDIARG_TEX2D_RENDERTARGETVIEW structure


## -description

The D3D10DDIARG_TEX2D_RENDERTARGETVIEW structure describes a two-dimensional (2-D) texture that is used to create a render target view in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createrendertargetview">CreateRenderTargetView</a> function.

## -struct-fields

### -field MipSlice

[in] The identifier of the MIP-map slice.

### -field FirstArraySlice

[in] The identifier of the first array slice.

### -field ArraySize

[in] The number of array slices for the texture.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivaterendertargetviewsize">CalcPrivateRenderTargetViewSize</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createrendertargetview">CreateRenderTargetView</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createrendertargetview">D3D10DDIARG_CREATERENDERTARGETVIEW</a>
