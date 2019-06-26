---
UID: NS:d3dumddi._D3DDDIARG_DECODEENDFRAME
title: _D3DDDIARG_DECODEENDFRAME (d3dumddi.h)
description: The D3DDDIARG_DECODEENDFRAME structure specifies the Microsoft DirectX Video Accelerator (VA) decoder that should stop decoding a frame.
old-location: display\d3dddiarg_decodeendframe.htm
tech.root: display
ms.assetid: 267335d2-37bd-4615-ad8e-5a8805eb93f7
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_DECODEENDFRAME, D3DDDIARG_DECODEENDFRAME structure [Display Devices], UMDisplayDriver_param_Structs_7c4f1596-3837-4094-9e8d-b5ea05207489.xml, _D3DDDIARG_DECODEENDFRAME, d3dumddi/D3DDDIARG_DECODEENDFRAME, display.d3dddiarg_decodeendframe
ms.topic: struct
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
- D3DDDIARG_DECODEENDFRAME
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_DECODEENDFRAME
---

# _D3DDDIARG_DECODEENDFRAME structure


## -description


The D3DDDIARG_DECODEENDFRAME structure specifies the Microsoft DirectX Video Accelerator (VA) decoder that should stop decoding a frame. 


## -struct-fields




### -field hDecode

A handle to the DirectX VA decode device. The user-mode display driver returns this handle in a call to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_createdecodedevice">CreateDecodeDevice</a> function.


### -field pHandleComplete

This member is reserved and should be set to <b>NULL</b>. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_createdecodedevice">CreateDecodeDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_decodeendframe">DecodeEndFrame</a>
 

 

