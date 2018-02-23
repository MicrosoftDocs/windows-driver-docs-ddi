---
UID: NS:d3d10umddi.D3D10DDIARG_CREATEDEPTHSTENCILVIEW
title: D3D10DDIARG_CREATEDEPTHSTENCILVIEW
author: windows-driver-content
description: The D3D10DDIARG_CREATEDEPTHSTENCILVIEW structure describes the depth stencil view to create.
old-location: display\d3d10ddiarg_createdepthstencilview.htm
old-project: display
ms.assetid: 03851dee-4ed8-484f-8a00-68aca1da19ce
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: D3D10DDIARG_CREATEDEPTHSTENCILVIEW, d3d10umddi/D3D10DDIARG_CREATEDEPTHSTENCILVIEW, UMDisplayDriver_Dx10param_Structs_7460e9f5-4a7b-469a-8019-cc634f00d4c1.xml, D3D10DDIARG_CREATEDEPTHSTENCILVIEW structure [Display Devices], display.d3d10ddiarg_createdepthstencilview
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
-	D3D10DDIARG_CREATEDEPTHSTENCILVIEW
product: Windows
targetos: Windows
req.typenames: D3D10DDIARG_CREATEDEPTHSTENCILVIEW
---

# D3D10DDIARG_CREATEDEPTHSTENCILVIEW structure


## -description


The D3D10DDIARG_CREATEDEPTHSTENCILVIEW structure describes the depth stencil view to create.


## -syntax


````
typedef struct D3D10DDIARG_CREATEDEPTHSTENCILVIEW {
  D3D10DDI_HRESOURCE    hDrvResource;
  DXGI_FORMAT           Format;
  D3D10DDIRESOURCE_TYPE ResourceDimension;
  union {
    D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW   Tex1D;
    D3D10DDIARG_TEX2D_DEPTHSTENCILVIEW   Tex2D;
    D3D10DDIARG_TEXCUBE_DEPTHSTENCILVIEW TexCube;
  };
} D3D10DDIARG_CREATEDEPTHSTENCILVIEW;
````


## -struct-fields




### -field hDrvResource

[in] A handle to the base depth stencil resource. 


### -field Format

[in] A DXGI_FORMAT-typed value that indicates the pixel format of the depth stencil view.


### -field ResourceDimension

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff541810">D3D10DDIRESOURCE_TYPE</a>-typed value that indicates the resource type and dimensionality of the base resource. 


#### - Tex1D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE1D, a member in the union that is contained in D3D10DDIARG_CREATEDEPTHSTENCILVIEW that can hold a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_tex1d_depthstencilview.md">D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW</a> structure for a one-dimensional texture. 


#### - Tex2D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE2D, a member in the union that is contained in D3D10DDIARG_CREATEDEPTHSTENCILVIEW that can hold a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_tex2d_depthstencilview.md">D3D10DDIARG_TEX2D_DEPTHSTENCILVIEW</a> structure for a two-dimensional texture. 


#### - TexCube

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURECUBE, a member in the union that is contained in D3D10DDIARG_CREATEDEPTHSTENCILVIEW that can hold a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_texcube_depthstencilview.md">D3D10DDIARG_TEXCUBE_DEPTHSTENCILVIEW</a> structure for a cube texture. 


## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_tex1d_depthstencilview.md">D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_texcube_depthstencilview.md">D3D10DDIARG_TEXCUBE_DEPTHSTENCILVIEW</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivatedepthstencilviewsize.md">CalcPrivateDepthStencilViewSize</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_tex2d_depthstencilview.md">D3D10DDIARG_TEX2D_DEPTHSTENCILVIEW</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdepthstencilview.md">CreateDepthStencilView</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541810">D3D10DDIRESOURCE_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10DDIARG_CREATEDEPTHSTENCILVIEW structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

