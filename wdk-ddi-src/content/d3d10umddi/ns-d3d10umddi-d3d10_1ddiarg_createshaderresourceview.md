---
UID: NS:d3d10umddi.D3D10_1DDIARG_CREATESHADERRESOURCEVIEW
title: D3D10_1DDIARG_CREATESHADERRESOURCEVIEW (d3d10umddi.h)
description: The D3D10_1DDIARG_CREATESHADERRESOURCEVIEW structure describes the shader resource view to create.
old-location: display\d3d10_1ddiarg_createshaderresourceview.htm
ms.assetid: d899ae74-9ee6-43c9-a8a9-44deb9eaa368
ms.date: 05/10/2018
keywords: ["D3D10_1DDIARG_CREATESHADERRESOURCEVIEW structure"]
ms.keywords: D3D10_1DDIARG_CREATESHADERRESOURCEVIEW, D3D10_1DDIARG_CREATESHADERRESOURCEVIEW structure [Display Devices], UMDisplayDriver_Dx10param_Structs_a6468f32-7ebf-4ce8-b5c5-9163e65fce93.xml, d3d10umddi/D3D10_1DDIARG_CREATESHADERRESOURCEVIEW, display.d3d10_1ddiarg_createshaderresourceview
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D10_1DDIARG_CREATESHADERRESOURCEVIEW is supported on Windows Vista with Service Pack 1 (SP1) and later versions and Windows Server 2008 and later versions.
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
req.typenames: D3D10_1DDIARG_CREATESHADERRESOURCEVIEW
f1_keywords:
 - D3D10_1DDIARG_CREATESHADERRESOURCEVIEW
 - d3d10umddi/D3D10_1DDIARG_CREATESHADERRESOURCEVIEW
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D10_1DDIARG_CREATESHADERRESOURCEVIEW
---

# D3D10_1DDIARG_CREATESHADERRESOURCEVIEW structure


## -description

The D3D10_1DDIARG_CREATESHADERRESOURCEVIEW structure describes the shader resource view to create.

## -struct-fields

### -field hDrvResource

[in] A handle to the shader resource.

### -field Format

[in] A DXGI_FORMAT-typed value that indicates the pixel format of the view.

### -field ResourceDimension

[in] A <a href="/previous-versions/windows/hardware/drivers/ff541810(v=vs.85)">D3D10DDIRESOURCE_TYPE</a>-typed value that indicates the resource type and dimensionality.

### -field Buffer

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_BUFFER, a member in the union that is contained in D3D10_1DDIARG_CREATESHADERRESOURCEVIEW that can hold a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_buffer_shaderresourceview">D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW</a> structure for a buffer.

### -field Tex1D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE1D, a member in the union that is contained in D3D10_1DDIARG_CREATESHADERRESOURCEVIEW that can hold a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_tex1d_shaderresourceview">D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW</a> structure for a one-dimensional texture.

### -field Tex2D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE2D, a member in the union that is contained in D3D10_1DDIARG_CREATESHADERRESOURCEVIEW that can hold a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_tex2d_shaderresourceview">D3D10DDIARG_TEX2D_SHADERRESOURCEVIEW</a> structure for a two-dimensional texture.

### -field Tex3D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE3D, a member in the union that is contained in D3D10_1DDIARG_CREATESHADERRESOURCEVIEW that can hold a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_tex3d_shaderresourceview">D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW</a> structure for a three-dimensional texture.

### -field TexCube

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURECUBE, a member in the union that is contained in D3D10_1DDIARG_CREATESHADERRESOURCEVIEW that can hold a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_1ddiarg_texcube_shaderresourceview">D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW</a> structure for a cube texture.

## -remarks

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10_1ddi_createshaderresourceview">CreateShaderResourceView(D3D10_1)</a> has a major functionality difference from the Direct3D 10.0 version (that is,<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createshaderresourceview">CreateShaderResourceView</a>) in regard to the <b>ResourceDimension</b> member of D3D10_1DDIARG_CREATESHADERRESOURCEVIEW. If the Direct3D runtime attempts to create a view on a shader resource, <b>CreateShaderResourceView</b> requires that the <b>ResourceDimension</b> member of <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createshaderresourceview">D3D10DDIARG_CREATESHADERRESOURCEVIEW</a> match the <b>ResourceDimension</b> member of <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createresource">D3D10DDIARG_CREATERESOURCE</a> for the shader resource that was created in a call to the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createresource">CreateResource(D3D10)</a> function. If the Direct3D 10.1 runtime attempts to create a view on a shader resource, <b>CreateShaderResourceView(D3D10_1)</b> allows a slight relaxation for its <b>ResourceDimension</b> member. <b>CreateShaderResourceView(D3D10_1)</b> allows the creation of Tex2D views on TexCube resources. In addition, the distinction between TexCube at the resource level is gone in Direct3D version 10.1. <b>CreateShaderResourceView(D3D10_1)</b> only represents whether it can create a TexCube view. In Direct3D version 10.0, copying a resource, validation of a multiple render target, and so on (that is, various operations that required the resource type to be identical) all included the distinction of TexCube to factor into the resource type. In Direct3D version 10.1, the runtime can determine only Tex2D.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10_1ddi_calcprivateshaderresourceviewsize">CalcPrivateShaderResourceViewSize(D3D10_1)</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10_1ddi_createshaderresourceview">CreateShaderResourceView(D3D10_1)</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_buffer_shaderresourceview">D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_tex1d_shaderresourceview">D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_tex2d_shaderresourceview">D3D10DDIARG_TEX2D_SHADERRESOURCEVIEW</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_tex3d_shaderresourceview">D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW</a>



<a href="/previous-versions/windows/hardware/drivers/ff541810(v=vs.85)">D3D10DDIRESOURCE_TYPE</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_1ddiarg_texcube_shaderresourceview">D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW</a>