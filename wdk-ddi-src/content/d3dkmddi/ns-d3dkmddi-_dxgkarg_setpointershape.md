---
UID: NS:d3dkmddi._DXGKARG_SETPOINTERSHAPE
title: _DXGKARG_SETPOINTERSHAPE (d3dkmddi.h)
description: The DXGKARG_SETPOINTERSHAPE structure describes the appearance of the mouse pointer and the location that it should be displayed in.
old-location: display\dxgkarg_setpointershape.htm
ms.date: 05/10/2018
keywords: ["DXGKARG_SETPOINTERSHAPE structure"]
ms.keywords: DXGKARG_SETPOINTERSHAPE, DXGKARG_SETPOINTERSHAPE structure [Display Devices], DmStructs_9fab674a-0138-4c55-b17e-87cb85110325.xml, _DXGKARG_SETPOINTERSHAPE, d3dkmddi/DXGKARG_SETPOINTERSHAPE, display.dxgkarg_setpointershape
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
tech.root: display
req.typenames: DXGKARG_SETPOINTERSHAPE
f1_keywords:
 - _DXGKARG_SETPOINTERSHAPE
 - d3dkmddi/_DXGKARG_SETPOINTERSHAPE
 - DXGKARG_SETPOINTERSHAPE
 - d3dkmddi/DXGKARG_SETPOINTERSHAPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_SETPOINTERSHAPE
 - DXGKARG_SETPOINTERSHAPE
---

# _DXGKARG_SETPOINTERSHAPE structure


## -description

The DXGKARG_SETPOINTERSHAPE structure describes the appearance of the mouse pointer and the location that it should be displayed in.

## -struct-fields

### -field Flags

[in] A <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_pointerflags">DXGK_POINTERFLAGS</a> structure that identifies, in bit-field flags, how to display the mouse pointer.

### -field Width

[in] The width of the mouse pointer, in pixels.

### -field Height

[in] The height of the mouse pointer, in scan lines.

### -field Pitch

[in] The width of the mouse pointer, in bytes.

### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the mouse pointer is located in.

### -field pPixels

[in] A pointer to the start of the following bitmap depending on the bit-field flag that is set in the <b>Flags</b> member:

|Bit-field flag|Bitmap|
|--- |--- |
|Monochrome|For monochrome mouse pointers:<br/>A monochrome bitmap whose size is specified by Width and Height in a 1 bits per pixel (bpp) DIB format AND mask that is followed by another 1 bpp DIB format XOR mask of the same size.|
|Color|For color mouse pointers:<br/>A color bitmap whose size is specified by Width and Height in a 32 bpp ARGB device independent bitmap (DIB) format.|
|MaskedColor|For masked color mouse pointers:<br/>A 32-bpp ARGB format bitmap with the mask value in the alpha bits. The only allowed mask values are 0 and 0xFF. When the mask value is 0, the RGB value should replace the screen pixel. When the mask value is 0xFF, an XOR operation is performed on the RGB value and the screen pixel; the result should replace the screen pixel.|

### -field XHot

[in] The column, in pixels, that the mouse pointer is located on from the top left of the bitmap that <b>pPixels</b> points to.

### -field YHot

[in] The row, in pixels, that the mouse pointer is located on from the top left of the bitmap that <b>pPixels</b> points to.

## -remarks

The <b>XHot</b> and <b>YHot</b> members are used by display miniport drivers that are not associated with hardware, and these members can be ignored by drivers that control hardware.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_pointerflags">DXGK_POINTERFLAGS</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_setpointershape">DxgkDdiSetPointerShape</a>

