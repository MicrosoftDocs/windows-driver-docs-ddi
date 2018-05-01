---
UID: NS:d3d10umddi.D3D10DDIARG_CREATEDEPTHSTENCILVIEW
title: D3D10DDIARG_CREATEDEPTHSTENCILVIEW
author: windows-driver-content
description: The D3D10DDIARG_CREATEDEPTHSTENCILVIEW structure describes the depth stencil view to create.
old-location: display\d3d10ddiarg_createdepthstencilview.htm
old-project: display
ms.assetid: 03851dee-4ed8-484f-8a00-68aca1da19ce
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3D10DDIARG_CREATEDEPTHSTENCILVIEW, D3D10DDIARG_CREATEDEPTHSTENCILVIEW structure [Display Devices], UMDisplayDriver_Dx10param_Structs_7460e9f5-4a7b-469a-8019-cc634f00d4c1.xml, d3d10umddi/D3D10DDIARG_CREATEDEPTHSTENCILVIEW, display.d3d10ddiarg_createdepthstencilview
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d10umddi.h
api_name:
-	D3D10DDIARG_CREATEDEPTHSTENCILVIEW
product: Windows
targetos: Windows
req.typenames: D3D10DDIARG_CREATEDEPTHSTENCILVIEW
---

# D3D10DDIARG_CREATEDEPTHSTENCILVIEW structure


## -description


The D3D10DDIARG_CREATEDEPTHSTENCILVIEW structure describes the depth stencil view to create.


## -struct-fields




### -field hDrvResource

[in] A handle to the base depth stencil resource. 


### -field Format

[in] A DXGI_FORMAT-typed value that indicates the pixel format of the depth stencil view.


### -field ResourceDimension

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff541810">D3D10DDIRESOURCE_TYPE</a>-typed value that indicates the resource type and dimensionality of the base resource. 


### -field Tex1D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE1D, a member in the union that is contained in D3D10DDIARG_CREATEDEPTHSTENCILVIEW that can hold a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541754">D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW</a> structure for a one-dimensional texture. 


### -field Tex2D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE2D, a member in the union that is contained in D3D10DDIARG_CREATEDEPTHSTENCILVIEW that can hold a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541763">D3D10DDIARG_TEX2D_DEPTHSTENCILVIEW</a> structure for a two-dimensional texture. 


### -field TexCube

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURECUBE, a member in the union that is contained in D3D10DDIARG_CREATEDEPTHSTENCILVIEW that can hold a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541797">D3D10DDIARG_TEXCUBE_DEPTHSTENCILVIEW</a> structure for a cube texture. 


## -see-also




<a href="https://msdn.microsoft.com/e5dfa018-f9a5-467f-8e84-9697d5f94689">CalcPrivateDepthStencilViewSize</a>



<a href="https://msdn.microsoft.com/1a1c28f0-8343-4255-8055-d31eb643b7d5">CreateDepthStencilView</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541754">D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541763">D3D10DDIARG_TEX2D_DEPTHSTENCILVIEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541797">D3D10DDIARG_TEXCUBE_DEPTHSTENCILVIEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541810">D3D10DDIRESOURCE_TYPE</a>
 

 

