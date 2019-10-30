---
UID: NS:d3dumddi._D3DDDIARG_SETRENDERTARGET
title: _D3DDDIARG_SETRENDERTARGET (d3dumddi.h)
description: The D3DDDIARG_SETRENDERTARGET structure describes the render target surface.
old-location: display\d3dddiarg_setrendertarget.htm
tech.root: display
ms.assetid: 88b0de48-1b85-4733-809c-6d8da657e920
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_SETRENDERTARGET, D3DDDIARG_SETRENDERTARGET structure [Display Devices], UMDisplayDriver_param_Structs_42cfb4bf-f5af-4008-9c6d-062e910b3238.xml, _D3DDDIARG_SETRENDERTARGET, d3dumddi/D3DDDIARG_SETRENDERTARGET, display.d3dddiarg_setrendertarget
ms.topic: struct
f1_keywords:
 - "d3dumddi/D3DDDIARG_SETRENDERTARGET"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
- d3dumddi.h
api_name:
- D3DDDIARG_SETRENDERTARGET
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_SETRENDERTARGET
---

# _D3DDDIARG_SETRENDERTARGET structure


## -description


The D3DDDIARG_SETRENDERTARGET structure describes the render target surface. 


## -struct-fields




### -field RenderTargetIndex

[in] An index into the group of render target surfaces.


### -field hRenderTarget

[in] A handle to the render target surface or the group of render target surfaces.


### -field SubResourceIndex

[in] An index into the resource for the render target.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_setrendertarget">SetRenderTarget</a>
 

 

