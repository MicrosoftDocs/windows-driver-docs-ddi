---
UID: NS:d3dumddi._D3DDDIARG_SETINDICES
title: _D3DDDIARG_SETINDICES (d3dumddi.h)
description: The D3DDDIARG_SETINDICES structure describes parameters for setting the current index buffer.
old-location: display\d3dddiarg_setindices.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDIARG_SETINDICES structure"]
ms.keywords: D3DDDIARG_SETINDICES, D3DDDIARG_SETINDICES structure [Display Devices], UMDisplayDriver_param_Structs_68458ee2-76c8-41c5-b610-47ef40874c1e.xml, _D3DDDIARG_SETINDICES, d3dumddi/D3DDDIARG_SETINDICES, display.d3dddiarg_setindices
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
req.typenames: D3DDDIARG_SETINDICES
f1_keywords:
 - _D3DDDIARG_SETINDICES
 - d3dumddi/_D3DDDIARG_SETINDICES
 - D3DDDIARG_SETINDICES
 - d3dumddi/D3DDDIARG_SETINDICES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _D3DDDIARG_SETINDICES
 - D3DDDIARG_SETINDICES
---

# _D3DDDIARG_SETINDICES structure


## -description

The D3DDDIARG_SETINDICES structure describes parameters for setting the current index buffer.

## -struct-fields

### -field hIndexBuffer

[in] A handle to the surface that is associated with the index buffer.

### -field Stride

[in] The size, in bytes, of the indices that are contained in the index buffer. The value of this member is 2 if the indices are 16-bit quantities or 4 if the indices are 32-bit quantities.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_setindices">SetIndices</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_setstreamsourceum">SetStreamSourceUM</a>

