---
UID: NS:d3dumddi._D3DDDIARG_BUFFERBLT
title: _D3DDDIARG_BUFFERBLT (d3dumddi.h)
description: The D3DDDIARG_BUFFERBLT structure describes the parameters of a buffer bit-block transfer (bitblt) operation.
old-location: display\d3dddiarg_bufferblt.htm
tech.root: display
ms.assetid: 1d638aeb-299a-4707-be5d-99291a1605e0
ms.date: 05/10/2018
keywords: ["_D3DDDIARG_BUFFERBLT structure"]
ms.keywords: D3DDDIARG_BUFFERBLT, D3DDDIARG_BUFFERBLT structure [Display Devices], UMDisplayDriver_param_Structs_08885ff3-963c-4067-bddc-696b9cc96e1b.xml, _D3DDDIARG_BUFFERBLT, d3dumddi/D3DDDIARG_BUFFERBLT, display.d3dddiarg_bufferblt
f1_keywords:
 - "d3dumddi/D3DDDIARG_BUFFERBLT"
 - "D3DDDIARG_BUFFERBLT"
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
- D3DDDIARG_BUFFERBLT
targetos: Windows
req.typenames: D3DDDIARG_BUFFERBLT
---

# _D3DDDIARG_BUFFERBLT structure


## -description


The D3DDDIARG_BUFFERBLT structure describes the parameters of a buffer bit-block transfer (bitblt) operation. 


## -struct-fields




### -field hDstResource

[in] A handle to the destination vertex or index buffer.


### -field hSrcResource

[in] A handle to the source vertex or index buffer.


### -field Offset

[in] The offset, in bytes, of the destination buffer that the copy should be directed into.


### -field SrcRange

[in] A D3DDDIRANGE structure that indicates what range of the source buffer should be copied. This D3DDDIRANGE specifies an offset and size, in bytes.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_bufblt">BufBlt</a>
 

 

