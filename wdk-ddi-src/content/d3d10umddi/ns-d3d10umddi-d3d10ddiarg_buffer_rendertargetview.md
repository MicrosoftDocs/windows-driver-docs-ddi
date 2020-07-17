---
UID: NS:d3d10umddi.D3D10DDIARG_BUFFER_RENDERTARGETVIEW
title: D3D10DDIARG_BUFFER_RENDERTARGETVIEW (d3d10umddi.h)
description: The D3D10DDIARG_BUFFER_RENDERTARGETVIEW structure describes a buffer that is used to create a render target view in a call to the CreateRenderTargetView function.
old-location: display\d3d10ddiarg_buffer_rendertargetview.htm
ms.assetid: 05c1d6e2-61e1-4bf0-b02e-5ea8ad144a9f
ms.date: 05/10/2018
keywords: ["D3D10DDIARG_BUFFER_RENDERTARGETVIEW structure"]
ms.keywords: D3D10DDIARG_BUFFER_RENDERTARGETVIEW, D3D10DDIARG_BUFFER_RENDERTARGETVIEW structure [Display Devices], UMDisplayDriver_Dx10param_Structs_7307c354-c2a6-45e8-a9f6-9cb3d7c7724d.xml, d3d10umddi/D3D10DDIARG_BUFFER_RENDERTARGETVIEW, display.d3d10ddiarg_buffer_rendertargetview
f1_keywords:
 - "d3d10umddi/D3D10DDIARG_BUFFER_RENDERTARGETVIEW"
 - "D3D10DDIARG_BUFFER_RENDERTARGETVIEW"
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
- D3D10DDIARG_BUFFER_RENDERTARGETVIEW
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10DDIARG_BUFFER_RENDERTARGETVIEW
---

# D3D10DDIARG_BUFFER_RENDERTARGETVIEW structure


## -description


The D3D10DDIARG_BUFFER_RENDERTARGETVIEW structure describes a buffer that is used to create a render target view in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createrendertargetview">CreateRenderTargetView</a> function. 


## -struct-fields




### -field FirstElement


### -field ElementOffset

[in] The offset (that is, the number of elements) between the beginning of the buffer and the first element that is to be used in the view, starting at 0. 


### -field NumElements


### -field ElementWidth

[in] The number of elements in the view. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivaterendertargetviewsize">CalcPrivateRenderTargetViewSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createrendertargetview">CreateRenderTargetView</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createrendertargetview">D3D10DDIARG_CREATERENDERTARGETVIEW</a>
 

 

