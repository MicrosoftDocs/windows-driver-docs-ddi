---
UID: NS:d3d10umddi.D3D10DDIARG_CREATERENDERTARGETVIEW
title: D3D10DDIARG_CREATERENDERTARGETVIEW
author: windows-driver-content
description: The D3D10DDIARG_CREATERENDERTARGETVIEW structure describes the render target view to create.
old-location: display\d3d10ddiarg_createrendertargetview.htm
old-project: display
ms.assetid: 2d21aacb-3b2b-4c33-ac35-9f15c1fa8171
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D10DDIARG_CREATERENDERTARGETVIEW structure [Display Devices], d3d10umddi/D3D10DDIARG_CREATERENDERTARGETVIEW, display.d3d10ddiarg_createrendertargetview, UMDisplayDriver_Dx10param_Structs_615cce2f-8ea4-4adc-9d7a-907414217ffc.xml, D3D10DDIARG_CREATERENDERTARGETVIEW
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	D3D10DDIARG_CREATERENDERTARGETVIEW
product: Windows
targetos: Windows
req.typenames: D3D10DDIARG_CREATERENDERTARGETVIEW
---

# D3D10DDIARG_CREATERENDERTARGETVIEW structure


## -description


The D3D10DDIARG_CREATERENDERTARGETVIEW structure describes the render target view to create.


## -syntax


````
typedef struct D3D10DDIARG_CREATERENDERTARGETVIEW {
  D3D10DDI_HRESOURCE    hDrvResource;
  DXGI_FORMAT           Format;
  D3D10DDIRESOURCE_TYPE ResourceDimension;
  union {
    D3D10DDIARG_BUFFER_RENDERTARGETVIEW  Buffer;
    D3D10DDIARG_TEX1D_RENDERTARGETVIEW   Tex1D;
    D3D10DDIARG_TEX2D_RENDERTARGETVIEW   Tex2D;
    D3D10DDIARG_TEX3D_RENDERTARGETVIEW   Tex3D;
    D3D10DDIARG_TEXCUBE_RENDERTARGETVIEW TexCube;
  };
} D3D10DDIARG_CREATERENDERTARGETVIEW;
````


## -struct-fields




### -field Buffer

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_BUFFER, a member in the union that is contained in D3D10DDIARG_CREATERENDERTARGETVIEW that can hold a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_buffer_rendertargetview.md">D3D10DDIARG_BUFFER_RENDERTARGETVIEW</a> structure for a buffer. 


### -field Tex1D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE1D, a member in the union that is contained in D3D10DDIARG_CREATERENDERTARGETVIEW that can hold a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_tex1d_rendertargetview.md">D3D10DDIARG_TEX1D_RENDERTARGETVIEW</a> structure for a one-dimensional texture. 


### -field Tex2D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE2D, a member in the union that is contained in D3D10DDIARG_CREATERENDERTARGETVIEW that can hold a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_tex2d_rendertargetview.md">D3D10DDIARG_TEX2D_RENDERTARGETVIEW</a> structure for a two-dimensional texture. 


### -field Tex3D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE3D, a member in the union that is contained in D3D10DDIARG_CREATERENDERTARGETVIEW that can hold a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_tex3d_rendertargetview.md">D3D10DDIARG_TEX3D_RENDERTARGETVIEW</a> structure for a three-dimensional texture. 


### -field TexCube

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURECUBE, a member in the union that is contained in D3D10DDIARG_CREATERENDERTARGETVIEW that can hold a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_texcube_rendertargetview.md">D3D10DDIARG_TEXCUBE_RENDERTARGETVIEW</a> structure for a cube texture. 


### -field hDrvResource

[in] A handle to the render target. 


### -field Format

[in] A DXGI_FORMAT-typed value that indicates the pixel format of the render target.


### -field ResourceDimension

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff541810">D3D10DDIRESOURCE_TYPE</a>-typed value that indicates the resource type and dimensionality of the render target. 


## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_tex1d_rendertargetview.md">D3D10DDIARG_TEX1D_RENDERTARGETVIEW</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivaterendertargetviewsize.md">CalcPrivateRenderTargetViewSize</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_texcube_rendertargetview.md">D3D10DDIARG_TEXCUBE_RENDERTARGETVIEW</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_tex2d_rendertargetview.md">D3D10DDIARG_TEX2D_RENDERTARGETVIEW</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createrendertargetview.md">CreateRenderTargetView</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541810">D3D10DDIRESOURCE_TYPE</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_buffer_rendertargetview.md">D3D10DDIARG_BUFFER_RENDERTARGETVIEW</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_tex3d_rendertargetview.md">D3D10DDIARG_TEX3D_RENDERTARGETVIEW</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10DDIARG_CREATERENDERTARGETVIEW structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

