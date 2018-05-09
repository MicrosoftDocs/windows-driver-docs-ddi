---
UID: NS:d3d10umddi.D3D10DDIARG_TEX3D_RENDERTARGETVIEW
title: D3D10DDIARG_TEX3D_RENDERTARGETVIEW
author: windows-driver-content
description: The D3D10DDIARG_TEX3D_RENDERTARGETVIEW structure describes a three-dimensional (3-D) texture that is used to create a render target view in a call to the CreateRenderTargetView function.
old-location: display\d3d10ddiarg_tex3d_rendertargetview.htm
old-project: display
ms.assetid: 2feff5f5-a104-4738-94be-add08fd99037
ms.author: windowsdriverdev
ms.date: 4/16/2018
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
product:
- Windows
targetos: Windows
req.typenames: D3D10DDIARG_TEX3D_RENDERTARGETVIEW
---

# D3D10DDIARG_TEX3D_RENDERTARGETVIEW structure


## -description


The D3D10DDIARG_TEX3D_RENDERTARGETVIEW structure describes a three-dimensional (3-D) texture that is used to create a render target view in a call to the <a href="https://msdn.microsoft.com/bf9fc732-5f9a-4fee-8ea0-19b140789463">CreateRenderTargetView</a> function. 


## -struct-fields




### -field MipSlice

[in] The identifier of the MIP-map slice. 


### -field FirstW

[in] The identifier of the first array slice. 


### -field WSize

[in] The number of array slices for the texture. 


## -see-also




<a href="https://msdn.microsoft.com/14d85e4a-960c-4438-9360-a4f2677603b8">CalcPrivateRenderTargetViewSize</a>



<a href="https://msdn.microsoft.com/bf9fc732-5f9a-4fee-8ea0-19b140789463">CreateRenderTargetView</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541689">D3D10DDIARG_CREATERENDERTARGETVIEW</a>
 

 

