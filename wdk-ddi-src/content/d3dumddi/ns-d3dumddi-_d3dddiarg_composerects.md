---
UID: NS:d3dumddi._D3DDDIARG_COMPOSERECTS
title: _D3DDDIARG_COMPOSERECTS (d3dumddi.h)
description: The D3DDDIARG_COMPOSERECTS structure describes the parameters that are used to compose rectangular areas.
old-location: display\d3dddiarg_composerects.htm
tech.root: display
ms.assetid: 9360f9c4-e30e-4fc0-ade7-1d98ff8b1d1b
ms.date: 05/10/2018
keywords: ["D3DDDIARG_COMPOSERECTS structure"]
ms.keywords: D3DDDIARG_COMPOSERECTS, D3DDDIARG_COMPOSERECTS structure [Display Devices], UMDisplayDriver_param_Structs_2f10ffa4-f55f-490b-9aa4-08c0c3e3d924.xml, _D3DDDIARG_COMPOSERECTS, d3dumddi/D3DDDIARG_COMPOSERECTS, display.d3dddiarg_composerects
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
req.typenames: D3DDDIARG_COMPOSERECTS
f1_keywords:
 - _D3DDDIARG_COMPOSERECTS
 - d3dumddi/_D3DDDIARG_COMPOSERECTS
 - D3DDDIARG_COMPOSERECTS
 - d3dumddi/D3DDDIARG_COMPOSERECTS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - D3DDDIARG_COMPOSERECTS
---

# _D3DDDIARG_COMPOSERECTS structure


## -description

The D3DDDIARG_COMPOSERECTS structure describes the parameters that are used to compose rectangular areas.

## -struct-fields

### -field hSrcResource

[in] A handle to the source resource that contains the source surface. When the surface is created, the user-mode display driver receives the D3DDDIFMT_A1 (one bit per pixel) value in the <b>Format</b> member and the <b>TextApi</b> bit-field flag in the <b>Flags</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddiarg_createresource">D3DDDIARG_CREATERESOURCE</a> structure in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createresource">CreateResource</a> function. The surface must be created as part of a texture.

### -field SrcSubResourceIndex

[in] The index to the source surface within the source resource.

### -field hDstResource

[in] A handle to the destination resource that contains the destination surface. When the surface is created, the user-mode display driver receives the D3DDDIFMT_A1 (one bit per pixel) value in the <b>Format</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddiarg_createresource">D3DDDIARG_CREATERESOURCE</a> in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createresource">CreateResource</a>. The surface must be created as part of a texture. The surface might have been created with the <b>TextApi</b> bit-field flag.

### -field DstSubResourceIndex

[in] The index to the destination surface within the destination resource.

### -field hSrcRectDescsVB

[in] A handle to a vertex buffer that contains an array of D3DCOMPOSERECTSRCDESC structures. Each element in the array defines a rectangle on the source surface. When the vertex buffer is created, the user-mode display driver receives the <b>TextApi</b> bit-field flag in the <b>Flags</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddiarg_createresource">D3DDDIARG_CREATERESOURCE</a> structure in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createresource">CreateResource</a> function.

### -field NumRects

[in] The number of rectangular areas to copy, which is the number of D3DCOMPOSERECTDSTDESC structures in the vertex buffer that is identified by the <b>hDstRectDescsVB</b> member. Drivers should ignore calls to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_composerects">ComposeRects</a> with <b>NumRects</b> set to greater than 0xFFFF.

### -field hDstRectDescsVB

[in] A handle to a vertex buffer that contains an array of D3DCOMPOSERECTDSTDESC structures. Each element in the array defines where to copy a source rectangle on the destination surface. For more information, see the following Remarks section. When the vertex buffer is created, the user-mode display driver receives the <b>TextApi</b> bit-field flag in the <b>Flags</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddiarg_createresource">D3DDDIARG_CREATERESOURCE</a> structure in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createresource">CreateResource</a> function.

### -field Operation

[in] A D3DDDI_COMPOSERECTSOP value that describes how to compose the rectangular areas. This member can be one of the following values.

| **Value** | **Meaning** | 
|:--|:--|
| D3DDDICOMPOSERECTS_COPY | Copy each source bit to the destination. | 
| D3DDDICOMPOSERECTS_OR | Combine source and destination bits in an OR operation and copy to the destination. | 
| D3DDDICOMPOSERECTS_AND | Combine source and destination bits in an AND operation and copy to the destination. | 
| D3DDDICOMPOSERECTS_NEG | Combine the negative of the source bits with the destination bits and copy to the destination. [Dest bit & (~ Src bit)] |

### -field XOffset

[in] An offset to add to the <i>x</i>-coordinates of all of the destination rectangular areas. The offset can be negative, which might cause the resultant rectangles to be rejected or clipped.

### -field YOffset

[in] An offset to add to the <i>y</i>-coordinates of all of the destination rectangular areas. The offset can be negative, which might cause the resultant rectangles to be rejected or clipped.

## -remarks

The vertex buffers that contain the composing instructions are created with D3DUSAGE_TEXTAPI usage. The following code defines the structures that are contained in the vertex buffer arrays. For more information about these structures, see the DirectX SDK documentation.

```cpp
struct D3DCOMPOSERECTSRCDESC {
USHORT X, Y;          // Coordinates of top-left corner
USHORT width, height; // Width and height of the glyph in bits
};

struct D3DCOMPOSERECTDSTDESC {
USHORT RectDescIndex; // Index of one of the D3DCOMPOSERECTSRCDESC structures in the vertex buffer represented by hSrcRectDescsVB
USHORT reserved;      // Use to align the struct and fields to good boundaries
SHORT X, Y;            // Position in bits in the destination surface
};
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_composerects">ComposeRects</a>



<a href="https://docs.microsoft.com/windows/win32/api/windef/ns-windef-tagrect">RECT</a>

