---
UID: NS:d3dumddi._D3DDDIARG_SETDECODERENDERTARGET
title: _D3DDDIARG_SETDECODERENDERTARGET (d3dumddi.h)
description: The D3DDDIARG_SETDECODERENDERTARGET structure describes the decode render target surface.
old-location: display\d3dddiarg_setdecoderendertarget.htm
tech.root: display
ms.assetid: 8903b579-8a63-42a5-9115-251f4e77ebb4
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_SETDECODERENDERTARGET, D3DDDIARG_SETDECODERENDERTARGET structure [Display Devices], UMDisplayDriver_param_Structs_1638f20c-2243-4b24-8373-d5e310aa10a0.xml, _D3DDDIARG_SETDECODERENDERTARGET, d3dumddi/D3DDDIARG_SETDECODERENDERTARGET, display.d3dddiarg_setdecoderendertarget
ms.topic: struct
f1_keywords:
 - "d3dumddi/D3DDDIARG_SETDECODERENDERTARGET"
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
- D3DDDIARG_SETDECODERENDERTARGET
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_SETDECODERENDERTARGET
---

# _D3DDDIARG_SETDECODERENDERTARGET structure


## -description


The D3DDDIARG_SETDECODERENDERTARGET structure describes the decode render target surface. 


## -struct-fields




### -field hDecode

[in] A handle to the Microsoft DirectX Video Acceleration (DirectX VA) decode device. The user-mode display driver returns this handle in a call to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createdecodedevice">CreateDecodeDevice</a> function.


### -field hRenderTarget

[in] A handle to the decode render target surface.


### -field SubResourceIndex

[in] An index into the resource for the decode render target surface.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createdecodedevice">CreateDecodeDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_setdecoderendertarget">SetDecodeRenderTarget</a>
 

 

