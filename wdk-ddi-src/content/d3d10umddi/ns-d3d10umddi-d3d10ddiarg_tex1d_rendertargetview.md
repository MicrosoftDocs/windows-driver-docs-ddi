---
UID: NS:d3d10umddi.D3D10DDIARG_TEX1D_RENDERTARGETVIEW
title: D3D10DDIARG_TEX1D_RENDERTARGETVIEW (d3d10umddi.h)
description: The D3D10DDIARG_TEX1D_RENDERTARGETVIEW structure describes a one-dimensional (1-D) texture that is used to create a render target view in a call to the CreateRenderTargetView function.
old-location: display\d3d10ddiarg_tex1d_rendertargetview.htm
ms.assetid: 42b0b937-55a3-47c2-9b5b-f9e3859cab71
ms.date: 05/10/2018
ms.keywords: D3D10DDIARG_TEX1D_RENDERTARGETVIEW, D3D10DDIARG_TEX1D_RENDERTARGETVIEW structure [Display Devices], UMDisplayDriver_Dx10param_Structs_588779f0-1830-4434-b83e-1f1d8e16906b.xml, d3d10umddi/D3D10DDIARG_TEX1D_RENDERTARGETVIEW, display.d3d10ddiarg_tex1d_rendertargetview
ms.topic: struct
f1_keywords:
 - "d3d10umddi/D3D10DDIARG_TEX1D_RENDERTARGETVIEW"
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
- D3D10DDIARG_TEX1D_RENDERTARGETVIEW
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10DDIARG_TEX1D_RENDERTARGETVIEW
---

# D3D10DDIARG_TEX1D_RENDERTARGETVIEW structure


## -description


The D3D10DDIARG_TEX1D_RENDERTARGETVIEW structure describes a one-dimensional (1-D) texture that is used to create a render target view in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createrendertargetview">CreateRenderTargetView</a> function. 


## -struct-fields




### -field MipSlice

[in] The identifier of the MIP-map slice. 


### -field FirstArraySlice

[in] The identifier of the first array slice. 


### -field ArraySize

[in] The number of array slices for the texture. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivaterendertargetviewsize">CalcPrivateRenderTargetViewSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createrendertargetview">CreateRenderTargetView</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createrendertargetview">D3D10DDIARG_CREATERENDERTARGETVIEW</a>
 

 

