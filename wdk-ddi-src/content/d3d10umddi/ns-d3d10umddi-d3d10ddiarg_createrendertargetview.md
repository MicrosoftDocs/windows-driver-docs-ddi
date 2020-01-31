---
UID: NS:d3d10umddi.D3D10DDIARG_CREATERENDERTARGETVIEW
title: D3D10DDIARG_CREATERENDERTARGETVIEW (d3d10umddi.h)
description: The D3D10DDIARG_CREATERENDERTARGETVIEW structure describes the render target view to create.
old-location: display\d3d10ddiarg_createrendertargetview.htm
ms.assetid: 2d21aacb-3b2b-4c33-ac35-9f15c1fa8171
ms.date: 05/10/2018
ms.keywords: D3D10DDIARG_CREATERENDERTARGETVIEW, D3D10DDIARG_CREATERENDERTARGETVIEW structure [Display Devices], UMDisplayDriver_Dx10param_Structs_615cce2f-8ea4-4adc-9d7a-907414217ffc.xml, d3d10umddi/D3D10DDIARG_CREATERENDERTARGETVIEW, display.d3d10ddiarg_createrendertargetview
f1_keywords:
 - "d3d10umddi/D3D10DDIARG_CREATERENDERTARGETVIEW"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d10umddi.h
api_name:
- D3D10DDIARG_CREATERENDERTARGETVIEW
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10DDIARG_CREATERENDERTARGETVIEW
---

# D3D10DDIARG_CREATERENDERTARGETVIEW structure


## -description


The D3D10DDIARG_CREATERENDERTARGETVIEW structure describes the render target view to create.


## -struct-fields




### -field hDrvResource

[in] A handle to the render target. 


### -field Format

[in] A DXGI_FORMAT-typed value that indicates the pixel format of the render target.


### -field ResourceDimension

[in] A <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff541810(v=vs.85)">D3D10DDIRESOURCE_TYPE</a>-typed value that indicates the resource type and dimensionality of the render target. 


### -field Buffer

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_BUFFER, a member in the union that is contained in D3D10DDIARG_CREATERENDERTARGETVIEW that can hold a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_buffer_rendertargetview">D3D10DDIARG_BUFFER_RENDERTARGETVIEW</a> structure for a buffer. 


### -field Tex1D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE1D, a member in the union that is contained in D3D10DDIARG_CREATERENDERTARGETVIEW that can hold a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_tex1d_rendertargetview">D3D10DDIARG_TEX1D_RENDERTARGETVIEW</a> structure for a one-dimensional texture. 


### -field Tex2D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE2D, a member in the union that is contained in D3D10DDIARG_CREATERENDERTARGETVIEW that can hold a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_tex2d_rendertargetview">D3D10DDIARG_TEX2D_RENDERTARGETVIEW</a> structure for a two-dimensional texture. 


### -field Tex3D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE3D, a member in the union that is contained in D3D10DDIARG_CREATERENDERTARGETVIEW that can hold a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_tex3d_rendertargetview">D3D10DDIARG_TEX3D_RENDERTARGETVIEW</a> structure for a three-dimensional texture. 


### -field TexCube

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURECUBE, a member in the union that is contained in D3D10DDIARG_CREATERENDERTARGETVIEW that can hold a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_texcube_rendertargetview">D3D10DDIARG_TEXCUBE_RENDERTARGETVIEW</a> structure for a cube texture. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivaterendertargetviewsize">CalcPrivateRenderTargetViewSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createrendertargetview">CreateRenderTargetView</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_buffer_rendertargetview">D3D10DDIARG_BUFFER_RENDERTARGETVIEW</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_tex1d_rendertargetview">D3D10DDIARG_TEX1D_RENDERTARGETVIEW</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_tex2d_rendertargetview">D3D10DDIARG_TEX2D_RENDERTARGETVIEW</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_tex3d_rendertargetview">D3D10DDIARG_TEX3D_RENDERTARGETVIEW</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_texcube_rendertargetview">D3D10DDIARG_TEXCUBE_RENDERTARGETVIEW</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff541810(v=vs.85)">D3D10DDIRESOURCE_TYPE</a>
 

 

