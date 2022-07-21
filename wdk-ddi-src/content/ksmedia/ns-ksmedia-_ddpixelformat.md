---
UID: NS:ksmedia._DDPIXELFORMAT
title: _DDPIXELFORMAT (ksmedia.h)
description: The DDPIXELFORMAT structure describes the pixel format of a DirectDrawSurface object.
tech.root: display
ms.date: 03/08/2022
keywords: ["DDPIXELFORMAT structure"]
ms.keywords: "*LPDDPIXELFORMAT, DDPIXELFORMAT, DDPIXELFORMAT structure [Display Devices], LPDDPIXELFORMAT, LPDDPIXELFORMAT structure pointer [Display Devices], _DDPIXELFORMAT, ddstrcts_861a4798-418e-492a-b4cb-c4f1ce794a71.xml, display.ddpixelformat, ksmedia/DDPIXELFORMAT, ksmedia/LPDDPIXELFORMAT"
req.header: ksmedia.h
req.include-header: Ddraw.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.typenames: DDPIXELFORMAT, *LPDDPIXELFORMAT
f1_keywords:
 - _DDPIXELFORMAT
 - ksmedia/_DDPIXELFORMAT
 - LPDDPIXELFORMAT
 - ksmedia/LPDDPIXELFORMAT
 - DDPIXELFORMAT
 - ksmedia/DDPIXELFORMAT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - _DDPIXELFORMAT
 - LPDDPIXELFORMAT
 - DDPIXELFORMAT
---

## -description

The **DDPIXELFORMAT** structure describes the pixel format of a **DirectDrawSurface** object.

## -struct-fields

### -field dwSize

Specifies the size in bytes of the DDPIXELFORMAT structure. The driver must initialize this member before the structure is used.

**DirectX 9.0 and later versions only.** Specifies, on input, the version of the Microsoft DirectX runtime being used by the application. This member is set to DD_RUNTIME_VERSION, which is 0x00000900 for DirectX 9.0, in the **format** member of the [DD_GETFORMATDATA](../d3dhal/ns-d3dhal-_dd_getformatdata.md) structure for a D3DGDI2_TYPE_GETFORMAT query.

### -field dwFlags

Indicates a set of flags that specify optional control flags. This member is a bitwise OR of any of the following values:

| Flag | Meaning |
|--|--|
| DDPF_ALPHA | The pixel format describes an alpha-only surface. |
| DDPF_ALPHAPIXELS | The surface has alpha channel information in the pixel format. |
| DDPF_ALPHAPREMULT | The color components in the pixel are premultiplied by the alpha value in the pixel. If this flag is set, the DDPF_ALPHAPIXELS flag must also be set. If this flag is not set but the DDPF_ALPHAPIXELS flag is set, the color components in the pixel format are not premultiplied by alpha. In this case, the color components must be multiplied by the alpha value at the time that an alpha-blending operation is performed. |
| DDPF_BUMPDUDV | Bump map dUdV data in the pixel format is valid. |
| DDPF_BUMPHEIGHT | Bump map height data in the pixel format is valid. |
| DDPF_COMPRESSED | The surface accepts pixel data in the specified format and compresses it during the write operation. |
| DDPF_D3DFORMAT | Indicates a DirectX 8.0 and later format capability entry in the texture format list. This flag is not exposed to applications. |
| DDPF_FOURCC | The [FOURCC](/windows/win32/directshow/fourcc-codes) code is valid. |
| DDPF_LUMINANCE | Luminance data in the pixel format is valid. Use this flag for luminance-only or luminance-plus-alpha surfaces; the bit depth is then specified in the **dwLuminanceBitCount** member. |
| DDPF_LUMINANCEPIXELS | Luminance data in the pixel format is valid. Use this flag when hanging luminance off, for example, bumpmap surfaces. The bitmask for the luminance portion of the pixel is then specified in the **dwBumpLuminanceBitMask** member. |
| DDPF_NOVEL_TEXTURE_FORMAT | Indicates a new surface format that the runtime might not expose to all applications. |
| DDPF_PALETTEINDEXED1 | The surface is 1-bit color indexed. |
| DDPF_PALETTEINDEXED2 | The surface is 2-bit color indexed. |
| DDPF_PALETTEINDEXED4 | The surface is 4-bit color indexed. |
| DDPF_PALETTEINDEXED8 | The surface is 8-bit color indexed. |
| DDPF_PALETTEINDEXEDTO8 | The surface is 1-, 2-, or 4-bit color indexed to an 8-bit palette. |
| DDPF_RGB | The RGB data in the pixel format structure is valid. |
| DDPF_RGBTOYUV | The surface accepts RGB data and translates it during the write operation to YUV data. The format of the data to be written is contained in the pixel format structure. The DDPF_RGB flag is set. |
| DDPF_STENCILBUFFER | The surface encodes stencil and depth information in each pixel of the z-buffer. |
| DDPF_YUV | The YUV data in the pixel format structure is valid. |
| DDPF_ZBUFFER | The pixel format describes a z-buffer-only surface. |
| DDPF_ZPIXELS | The surface is in RGBZ format. |

### -field dwFourCC

Specifies a surface format code including any of the codes in the D3DFORMAT enumerated type. Some [FOURCC](/windows/win32/directshow/fourcc-codes) codes are part of D3DFORMAT. For more information about D3DFORMAT, see the SDK documentation. Hardware vendors can also define and supply format codes that are specific to their hardware.

### -field dwRGBBitCount

Specifies the number of RGB bits per pixel (4, 8, 16, 24, or 32).

### -field dwYUVBitCount

Specifies the number of YUV bits per pixel.

### -field dwZBufferBitDepth

Specifies the Z-buffer bit depth (8, 16, 24, or 32 bits).

### -field dwAlphaBitDepth

Specifies the Alpha channel bit depth.

### -field dwRBitMask

Specifies the mask for red bits.

### -field dwYBitMask

Specifies the mask for Y bits.

### -field dwGBitMask

Specifies the mask for green bits.

### -field dwUBitMask

Specifies the mask for U bits.

### -field dwBBitMask

Specifies the mask for blue bits.

### -field dwVBitMask

Specifies the mask for V bits.

### -field dwRGBAlphaBitMask

Mask for alpha channel.

### -field dwYUVAlphaBitMask

Mask for alpha channel.

### -field dwRGBZBitMask

Mask for Z channel.

### -field dwYUVZBitMask

Mask for Z channel.

## -remarks

The DirectX 8.0 and later runtime imposes the following rules on the operation (op) list:

- Only one Endian-ness (big or little) for any DS format is allowed, for example D15S1 or S1D15, not both independent of other bits.

- A list should only include D3DFORMAT_OP_DISPLAYMODE for exactly one 16bpp format (for example it should not enumerate 5:5:5 and 5:6:5).

- A list should not contain any alpha formats with D3DFORMAT_OP_DISPLAYMODE or D3DFORMAT_OP_3DACCELLERATION set.

- The D3DFORMAT_OP_3DACCELLERATION flag can only be set when the D3DFORMAT_OP_DISPLAYMODE flag is also set.

If the driver supports a lockable D16, it should report D3DFMT_D16_LOCKABLE in the op list; otherwise, it should report D3DFMT_D16.

Drivers supporting multisampling must fill in the **MultiSampleCaps** in the Depth/Stencil formats for which multisampling can be supported. This allows the runtime to detect if a driver supports multisampling for combinations of render target and Z buffer formats. For additional information about the restrictions related to stretch blt multisampling, see the description of D3DPRASTERCAPS_STRETCHBLTMULTISAMPLE cap in the rastercaps contained in the D3DCAPS8 structure in the SDK documentation.

The enumerated type D3DMULTISAMPLE_TYPE defined in *d3d8types.h* is used when setting the bits in **wFlipMSTypes** and **wBltMSTypes**. To specify support for a specific number of samples per pixel, simply logically shift 1 by the appropriate value from the D3DMULTISAMPLE_TYPE enumerated type less 1 and OR this into the appropriate field (**wFlipMSTypes** and **wBltMSTypes**).

For example, if the driver supports both two and four samples per pixel when flipping (fullscreen mode) and four samples per pixel when blitting (windowed mode) on X8R8G8B8 surface the following entry would be reported in the surface format list.

```cpp
DDPIXELFORMAT ddpf;
ZeroMemory(&ddpf, sizeof(ddpf));
ddpf.dwSize       = sizeof(DDPIXELFORMAT);
ddpf.dwFlags      = DDPF_D3DFORMAT;
ddpf.dwFourCC     = D3DFMT_X8R8G8B8;
ddpf.dwOperations = D3DFORMAT_OP_DISPLAYMODE |
                    D3DFORMAT_OP_3DACCELERATION;
ddpf.MultiSampleCaps.wFlipMSTypes = (1 << (D3DMULTISAMPLE_4_SAMPLES âˆ' 1))
                                  | (1 << (D3DMULTISAMPLE_2_SAMPLES âˆ' 1));
ddpf.MultiSampleCaps.wBltMSTypes = (1 << (D3DMULTISAMPLE_4_SAMPLES âˆ' 1));
```

It is not necessary to specify 1 << (D3DMULTISAMPLE_NONE - 1) when reporting formats. It is assumed that any format reported can also be used without multisampling. If the hardware supports multisample rendering with a z-buffer the z-buffer formats reported should also include the supported samples-per-pixels.

## -see-also
