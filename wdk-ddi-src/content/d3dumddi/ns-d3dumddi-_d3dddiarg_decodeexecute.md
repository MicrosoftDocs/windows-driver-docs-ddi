---
UID: NS:d3dumddi._D3DDDIARG_DECODEEXECUTE
title: _D3DDDIARG_DECODEEXECUTE (d3dumddi.h)
description: The D3DDDIARG_DECODEEXECUTE structure describes a Microsoft DirectX Video Acceleration (VA) decode operation to perform.
old-location: display\d3dddiarg_decodeexecute.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDIARG_DECODEEXECUTE structure"]
ms.keywords: D3DDDIARG_DECODEEXECUTE, D3DDDIARG_DECODEEXECUTE structure [Display Devices], UMDisplayDriver_param_Structs_bd4aee7e-91f5-41dc-bb63-0fed88e04c7d.xml, _D3DDDIARG_DECODEEXECUTE, d3dumddi/D3DDDIARG_DECODEEXECUTE, display.d3dddiarg_decodeexecute
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
targetos: Windows
req.typenames: D3DDDIARG_DECODEEXECUTE
f1_keywords:
 - _D3DDDIARG_DECODEEXECUTE
 - d3dumddi/_D3DDDIARG_DECODEEXECUTE
 - D3DDDIARG_DECODEEXECUTE
 - d3dumddi/D3DDDIARG_DECODEEXECUTE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _D3DDDIARG_DECODEEXECUTE
 - D3DDDIARG_DECODEEXECUTE
---

# _D3DDDIARG_DECODEEXECUTE structure


## -description

The D3DDDIARG_DECODEEXECUTE structure describes a Microsoft DirectX Video Acceleration (VA) decode operation to perform.

## -struct-fields

### -field hDecode [in]

A handle to the DirectX VA decode device. The user-mode display driver returns this handle in a call to its <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createdecodedevice">CreateDecodeDevice</a> function.

### -field NumCompBuffers [in]

The number of compressed buffer that are pointed to by the <b>pCompressedBuffers</b> member.

### -field pCompressedBuffers [in]

A pointer to a list of <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_decodebufferdesc">DXVADDI_DECODEBUFFERDESC</a> structures that describe the compressed buffers that are passed from the host decoder to the accelerator.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createdecodedevice">CreateDecodeDevice</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_decodebufferdesc">DXVADDI_DECODEBUFFERDESC</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_decodeexecute">DecodeExecute</a>

