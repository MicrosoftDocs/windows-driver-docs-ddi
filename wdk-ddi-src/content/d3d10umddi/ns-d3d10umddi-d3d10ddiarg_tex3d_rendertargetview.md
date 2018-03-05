---
UID: NS:d3d10umddi.D3D10DDIARG_TEX3D_RENDERTARGETVIEW
title: D3D10DDIARG_TEX3D_RENDERTARGETVIEW
author: windows-driver-content
description: The D3D10DDIARG_TEX3D_RENDERTARGETVIEW structure describes a three-dimensional (3-D) texture that is used to create a render target view in a call to the CreateRenderTargetView function.
old-location: display\d3d10ddiarg_tex3d_rendertargetview.htm
old-project: display
ms.assetid: 2feff5f5-a104-4738-94be-add08fd99037
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D10DDIARG_TEX3D_RENDERTARGETVIEW, D3D10DDIARG_TEX3D_RENDERTARGETVIEW structure [Display Devices], UMDisplayDriver_Dx10param_Structs_705e661d-890a-45db-a805-60d2c2cbde6f.xml, d3d10umddi/D3D10DDIARG_TEX3D_RENDERTARGETVIEW, display.d3d10ddiarg_tex3d_rendertargetview
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
-	D3D10DDIARG_TEX3D_RENDERTARGETVIEW
product: Windows
targetos: Windows
req.typenames: D3D10DDIARG_TEX3D_RENDERTARGETVIEW
---

# D3D10DDIARG_TEX3D_RENDERTARGETVIEW structure


## -description


The D3D10DDIARG_TEX3D_RENDERTARGETVIEW structure describes a three-dimensional (3-D) texture that is used to create a render target view in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createrendertargetview.md">CreateRenderTargetView</a> function. 


## -syntax


````
typedef struct D3D10DDIARG_TEX3D_RENDERTARGETVIEW {
  UINT MipSlice;
  UINT FirstW;
  UINT WSize;
} D3D10DDIARG_TEX3D_RENDERTARGETVIEW;
````


## -struct-fields




### -field MipSlice

[in] The identifier of the MIP-map slice. 


### -field FirstW

[in] The identifier of the first array slice. 


### -field WSize

[in] The number of array slices for the texture. 


## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createrendertargetview.md">CreateRenderTargetView</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createrendertargetview.md">D3D10DDIARG_CREATERENDERTARGETVIEW</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivaterendertargetviewsize.md">CalcPrivateRenderTargetViewSize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10DDIARG_TEX3D_RENDERTARGETVIEW structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

