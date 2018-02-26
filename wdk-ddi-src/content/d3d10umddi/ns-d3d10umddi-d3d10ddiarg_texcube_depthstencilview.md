---
UID: NS:d3d10umddi.D3D10DDIARG_TEXCUBE_DEPTHSTENCILVIEW
title: D3D10DDIARG_TEXCUBE_DEPTHSTENCILVIEW
author: windows-driver-content
description: The D3D10DDIARG_TEXCUBE_DEPTHSTENCILVIEW structure describes a cube texture that is used to create a depth stencil view in a call to the CreateDepthStencilView function.
old-location: display\d3d10ddiarg_texcube_depthstencilview.htm
old-project: display
ms.assetid: b67570e5-ea0d-47e6-afe3-41dc3a4a0cdf
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, 0, 1, 3, A, B, C, D, D3D10DDIARG_TEXCUBE_DEPTHSTENCILVIEW, D3D10DDIARG_TEXCUBE_DEPTHSTENCILVIEW structure [Display Devices], E, G, H, I, L, N, P, R, S, T, U, UMDisplayDriver_Dx10param_Structs_95c96af9-bece-4fbe-ab6c-b8184828aa8d.xml, V, W, X, _, d3d10umddi/D3D10DDIARG_TEXCUBE_DEPTHSTENCILVIEW, display.d3d10ddiarg_texcube_depthstencilview"
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
-	D3D10DDIARG_TEXCUBE_DEPTHSTENCILVIEW
product: Windows
targetos: Windows
req.typenames: D3D10DDIARG_TEXCUBE_DEPTHSTENCILVIEW
---

# D3D10DDIARG_TEXCUBE_DEPTHSTENCILVIEW structure


## -description


The D3D10DDIARG_TEXCUBE_DEPTHSTENCILVIEW structure describes a cube texture that is used to create a depth stencil view in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdepthstencilview.md">CreateDepthStencilView</a> function. 


## -syntax


````
typedef struct D3D10DDIARG_TEXCUBE_DEPTHSTENCILVIEW {
  UINT MipSlice;
  UINT FirstArraySlice;
  UINT ArraySize;
} D3D10DDIARG_TEXCUBE_DEPTHSTENCILVIEW;
````


## -struct-fields




### -field MipSlice

[in] The identifier of the MIP-map slice. 


### -field FirstArraySlice

[in] The identifier of the first array slice. 


### -field ArraySize

[in] The number of array slices for the texture. 


## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdepthstencilview.md">D3D10DDIARG_CREATEDEPTHSTENCILVIEW</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdepthstencilview.md">CreateDepthStencilView</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivatedepthstencilviewsize.md">CalcPrivateDepthStencilViewSize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10DDIARG_TEXCUBE_DEPTHSTENCILVIEW structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

