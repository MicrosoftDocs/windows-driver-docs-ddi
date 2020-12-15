---
UID: NS:d3dumddi._D3DDDIARG_SETDISPLAYMODE
title: _D3DDDIARG_SETDISPLAYMODE (d3dumddi.h)
description: The D3DDDIARG_SETDISPLAYMODE structure describes parameters for setting the display mode.
old-location: display\d3dddiarg_setdisplaymode.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDIARG_SETDISPLAYMODE structure"]
ms.keywords: D3DDDIARG_SETDISPLAYMODE, D3DDDIARG_SETDISPLAYMODE structure [Display Devices], UMDisplayDriver_param_Structs_89fc526d-719f-43b5-b195-47a199a290ec.xml, _D3DDDIARG_SETDISPLAYMODE, d3dumddi/D3DDDIARG_SETDISPLAYMODE, display.d3dddiarg_setdisplaymode
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
req.typenames: D3DDDIARG_SETDISPLAYMODE
f1_keywords:
 - _D3DDDIARG_SETDISPLAYMODE
 - d3dumddi/_D3DDDIARG_SETDISPLAYMODE
 - D3DDDIARG_SETDISPLAYMODE
 - d3dumddi/D3DDDIARG_SETDISPLAYMODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - D3DDDIARG_SETDISPLAYMODE
---

# _D3DDDIARG_SETDISPLAYMODE structure


## -description

The D3DDDIARG_SETDISPLAYMODE structure describes parameters for setting the display mode.

## -struct-fields

### -field hResource

[in] A handle to the resource that contains the display surface.

### -field SubResourceIndex

[in] The zero-based index into the resource, which is specified by the handle in the <b>hResource</b> member. This index indicates the display surface.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_setdisplaymode">SetDisplayMode</a>
