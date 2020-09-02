---
UID: NS:d3d10umddi.D3D11DDIARG_BUFFER_RENDERTARGETVIEW
title: D3D11DDIARG_BUFFER_RENDERTARGETVIEW (d3d10umddi.h)
description: The D3D11DDIARG_BUFFER_RENDERTARGETVIEW structure describes a buffer that is used to create a render target view in a call to the CreateRenderTargetView function.
old-location: display\d3d11ddiarg_buffer_rendertargetview.htm
ms.assetid: 1c89b4bd-7473-4da6-afbe-4103f3f3d7be
ms.date: 05/10/2018
keywords: ["D3D11DDIARG_BUFFER_RENDERTARGETVIEW structure"]
ms.keywords: D3D11DDIARG_BUFFER_RENDERTARGETVIEW, D3D11DDIARG_BUFFER_RENDERTARGETVIEW structure [Display Devices], UMDisplayDriver_Dx11param_Structs_1e10bcbc-ad5c-47b4-a36d-d1d471e38a7e.xml, d3d10umddi/D3D11DDIARG_BUFFER_RENDERTARGETVIEW, display.d3d11ddiarg_buffer_rendertargetview
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDIARG_BUFFER_RENDERTARGETVIEW is supported beginning with the Windows 7 operating system.
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
targetos: Windows
tech.root: display
req.typenames: D3D11DDIARG_BUFFER_RENDERTARGETVIEW
f1_keywords:
 - D3D11DDIARG_BUFFER_RENDERTARGETVIEW
 - d3d10umddi/D3D11DDIARG_BUFFER_RENDERTARGETVIEW
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D11DDIARG_BUFFER_RENDERTARGETVIEW
---

# D3D11DDIARG_BUFFER_RENDERTARGETVIEW structure


## -description

The D3D11DDIARG_BUFFER_RENDERTARGETVIEW structure describes a buffer that is used to create a render target view in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createrendertargetview">CreateRenderTargetView</a> function.

## -struct-fields

### -field FirstElement

[in] The offset, in bytes, to the first element in the buffer.

### -field ElementOffset

[in] The offset, in bytes, to the first element in the buffer.

### -field NumElements

[in] The number of elements in the buffer.

### -field ElementWidth

[in] The width, in elements, in the buffer.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivaterendertargetviewsize">CalcPrivateRenderTargetViewSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createrendertargetview">CreateRenderTargetView</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createrendertargetview">D3D10DDIARG_CREATERENDERTARGETVIEW</a>

