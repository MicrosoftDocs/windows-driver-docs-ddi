---
UID: NS:d3dumddi._D3DDDIARG_COLORFILL
title: _D3DDDIARG_COLORFILL (d3dumddi.h)
description: The D3DDDIARG_COLORFILL structure describes the parameters of a color-fill operation.
old-location: display\d3dddiarg_colorfill.htm
tech.root: display
ms.assetid: 4d647c59-4e00-46b3-a46f-226e475eb63d
ms.date: 05/10/2018
keywords: ["D3DDDIARG_COLORFILL structure"]
ms.keywords: D3DDDIARG_COLORFILL, D3DDDIARG_COLORFILL structure [Display Devices], UMDisplayDriver_param_Structs_1ad82ddb-4070-45be-81c3-c2347170fad0.xml, _D3DDDIARG_COLORFILL, d3dumddi/D3DDDIARG_COLORFILL, display.d3dddiarg_colorfill
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
req.typenames: D3DDDIARG_COLORFILL
f1_keywords:
 - _D3DDDIARG_COLORFILL
 - d3dumddi/_D3DDDIARG_COLORFILL
 - D3DDDIARG_COLORFILL
 - d3dumddi/D3DDDIARG_COLORFILL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - D3DDDIARG_COLORFILL
---

# _D3DDDIARG_COLORFILL structure


## -description

The D3DDDIARG_COLORFILL structure describes the parameters of a color-fill operation.

## -struct-fields

### -field hResource

[in] A handle to the resource.

### -field SubResourceIndex

[in] The zero-based index into the resource, which is specified by the handle in the <b>hResource</b> member. This index indicates the subresource, or surface, on which a rectangular area is color-filled.

### -field DstRect

[in] A <a href="/windows/win32/api/windef/ns-windef-rectl">RECTL</a> structure that indicates the upper-left and lower-right points of a rectangle on the surface to color fill.

### -field Color

A D3DCOLOR data type for the A8R8G8B8 fill color.

### -field Flags

[in] A <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_colorfillflags">D3DDDI_COLORFILLFLAGS</a> structure that identifies the type of color-fill operation to perform.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_colorfill">ColorFill</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_colorfillflags">D3DDDI_COLORFILLFLAGS</a>



<a href="/windows/win32/api/windef/ns-windef-rectl">RECTL</a>