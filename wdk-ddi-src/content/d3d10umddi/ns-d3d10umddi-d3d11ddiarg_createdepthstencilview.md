---
UID: NS:d3d10umddi.D3D11DDIARG_CREATEDEPTHSTENCILVIEW
title: D3D11DDIARG_CREATEDEPTHSTENCILVIEW
author: windows-driver-content
description: The D3D11DDIARG_CREATEDEPTHSTENCILVIEW structure describes the depth-stencil view to create.
old-location: display\d3d11ddiarg_createdepthstencilview.htm
old-project: display
ms.assetid: 563a443b-f460-4fb2-b179-454466c2291b
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3D11DDIARG_CREATEDEPTHSTENCILVIEW, D3D11DDIARG_CREATEDEPTHSTENCILVIEW structure [Display Devices], UMDisplayDriver_Dx11param_Structs_17e6fa50-317c-445d-b304-8097f658652f.xml, d3d10umddi/D3D11DDIARG_CREATEDEPTHSTENCILVIEW, display.d3d11ddiarg_createdepthstencilview
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDIARG_CREATEDEPTHSTENCILVIEW is supported beginning with the Windows 7 operating system.
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
-	D3D11DDIARG_CREATEDEPTHSTENCILVIEW
product: Windows
targetos: Windows
req.typenames: D3D11DDIARG_CREATEDEPTHSTENCILVIEW
---

# D3D11DDIARG_CREATEDEPTHSTENCILVIEW structure


## -description


The D3D11DDIARG_CREATEDEPTHSTENCILVIEW structure describes the depth-stencil view to create.


## -struct-fields




### -field hDrvResource

[in] A handle to the base depth stencil resource. 


### -field Format

[in] A DXGI_FORMAT-typed value that indicates the pixel format of the depth-stencil view.


### -field ResourceDimension

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff541810">D3D10DDIRESOURCE_TYPE</a>-typed value that indicates the resource type and dimensionality of the base resource. 


### -field Flags

[in] A valid bitwise OR of <a href="https://msdn.microsoft.com/library/windows/hardware/ff542167">D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG</a>-typed values that indicates the type of depth-stencil view to create. 


### -field Tex1D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE1D, a member in the union that is contained in D3D10DDIARG_CREATEDEPTHSTENCILVIEW that can hold a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541754">D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW</a> structure for a one-dimensional texture. 


### -field Tex2D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE2D, a member in the union that is contained in D3D10DDIARG_CREATEDEPTHSTENCILVIEW that can hold a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541763">D3D10DDIARG_TEX2D_DEPTHSTENCILVIEW</a> structure for a two-dimensional texture. 


### -field TexCube

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURECUBE, a member in the union that is contained in D3D10DDIARG_CREATEDEPTHSTENCILVIEW that can hold a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541797">D3D10DDIARG_TEXCUBE_DEPTHSTENCILVIEW</a> structure for a cube texture. 


## -see-also




<a href="https://msdn.microsoft.com/d92e3bde-9527-401e-aafd-4ba39603d4a7">CalcPrivateDepthStencilViewSize(D3D11)</a>



<a href="https://msdn.microsoft.com/cf4c34da-71df-4b49-b1c8-73d1a2dbc3cb">CreateDepthStencilView(D3D11)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541754">D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541763">D3D10DDIARG_TEX2D_DEPTHSTENCILVIEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541797">D3D10DDIARG_TEXCUBE_DEPTHSTENCILVIEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541810">D3D10DDIRESOURCE_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542167">D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG</a>
 

 

