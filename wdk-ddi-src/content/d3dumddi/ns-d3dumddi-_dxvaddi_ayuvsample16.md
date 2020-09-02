---
UID: NS:d3dumddi._DXVADDI_AYUVSAMPLE16
title: _DXVADDI_AYUVSAMPLE16 (d3dumddi.h)
description: The DXVADDI_AYUVSAMPLE16 structure describes 16-bit Cr, Cb, and Y color values and an associated opacity.
old-location: display\dxvaddi_ayuvsample16.htm
tech.root: display
ms.assetid: 9cd2e943-dc20-4c5c-ab5c-090463e0a88c
ms.date: 05/10/2018
keywords: ["DXVADDI_AYUVSAMPLE16 structure"]
ms.keywords: DXVA2_Structs_9e7fc230-f50c-4a07-b1cb-358694dc207d.xml, DXVADDI_AYUVSAMPLE16, DXVADDI_AYUVSAMPLE16 structure [Display Devices], _DXVADDI_AYUVSAMPLE16, d3dumddi/DXVADDI_AYUVSAMPLE16, display.dxvaddi_ayuvsample16
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
req.typenames: DXVADDI_AYUVSAMPLE16
f1_keywords:
 - _DXVADDI_AYUVSAMPLE16
 - d3dumddi/_DXVADDI_AYUVSAMPLE16
 - DXVADDI_AYUVSAMPLE16
 - d3dumddi/DXVADDI_AYUVSAMPLE16
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - DXVADDI_AYUVSAMPLE16
---

# _DXVADDI_AYUVSAMPLE16 structure


## -description

The DXVADDI_AYUVSAMPLE16 structure describes 16-bit Cr, Cb, and Y color values and an associated opacity.

## -struct-fields

### -field Cr

[in] A 16-bit chrominance (V) sample value.

### -field Cb

[in] A 16-bit chrominance (U) sample value.

### -field Y

[in] A 16-bit luminance (Y) sample value.

### -field Alpha

[in] The 16-bit opacity of the pixel when it is used as a source graphic for blending with another picture.

## -remarks

A value of 0 in the <b>Alpha</b> member indicates that the pixel is transparent (so that the other entries have no effect on the resulting blended picture), and a value of 255 indicates that the pixel is opaque (so that the other entries completely determine the value of the resulting blended picture sample). 

For nonzero values of <b>Alpha</b>, the blend to use is calculated by the following expression:

```cpp
( ( ( (Alpha + 1) x (graphic value) ) + ( (255 - Alpha) x (picture value) ) )  + 128 ) >> 8
```

If <b>Alpha</b> is 0, the specified blend to use is the picture value without alteration. 

The color value is scaled according to ITU-R Rec. BT.601, which you can learn about from the <a href="https://go.microsoft.com/fwlink/p/?linkid=8741">International Telecommunication Union</a> website. Therefore, the color black is nominally specified by Y=16, Cb=Cr=128, and the color white is nominally specified by Y=235, Cb=Cr=128.

> [!NOTE]
> If the alpha-blending surface originates as a DVD video subpicture, the preferred method for converting from the 4-bit alpha that is used by DVD video to the 8-bit alpha that is specified by <b>Alpha</b> is to map a 4-bit alpha value of zero to an 8-bit alpha value of zero and to convert all of the nonzero 4-bit alphas to 8-bit alphas by performing a left shift of four places and adding the constant 15.</div>
<div> </div>
The width and height of the AYUV alpha-blending surface are specified in the associated <a href="https://docs.microsoft.com/windows-hardware/drivers/display/buffer-description-list">buffer description list</a> that is defined by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_decodebufferdesc">DXVADDI_DECODEBUFFERDESC</a> structure.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_decodebufferdesc">DXVADDI_DECODEBUFFERDESC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_videodesc">DXVADDI_VIDEODESC</a>

