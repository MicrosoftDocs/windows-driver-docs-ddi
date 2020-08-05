---
UID: NS:ksmedia._DDPIXELFORMAT
title: _DDPIXELFORMAT (ksmedia.h)
description: The DDPIXELFORMAT structure describes the pixel format of a DirectDrawSurface object.
old-location: display\ddpixelformat.htm
tech.root: display
ms.assetid: bbc26c03-c154-4b1e-883e-2942b59ded02
ms.date: 05/10/2018
keywords: ["DDPIXELFORMAT structure"]
ms.keywords: "*LPDDPIXELFORMAT, DDPIXELFORMAT, DDPIXELFORMAT structure [Display Devices], LPDDPIXELFORMAT, LPDDPIXELFORMAT structure pointer [Display Devices], _DDPIXELFORMAT, ddstrcts_861a4798-418e-492a-b4cb-c4f1ce794a71.xml, display.ddpixelformat, ksmedia/DDPIXELFORMAT, ksmedia/LPDDPIXELFORMAT"
f1_keywords:
 - "ksmedia/DDPIXELFORMAT"
 - "DDPIXELFORMAT"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ksmedia.h
api_name:
- DDPIXELFORMAT
targetos: Windows
req.typenames: DDPIXELFORMAT, *LPDDPIXELFORMAT
---

# _DDPIXELFORMAT structure

## -description

The DDPIXELFORMAT structure describes the pixel format of a DirectDrawSurface object.

## -struct-fields

### -field dwSize

Specifies the size in bytes of the DDPIXELFORMAT structure. The driver must initialize this member before the structure is used.

**DirectX 9.0 and later versions only.** Specifies, on input, the version of the Microsoft DirectX runtime being used by the application. This member is set to DD_RUNTIME_VERSION, which is 0x00000900 for DirectX 9.0, in the **format** member of the [DD_GETFORMATDATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_getformatdata) structure for a D3DGDI2_TYPE_GETFORMAT query.

### -field dwFlags

Indicates a set of flags that specify optional control flags. This member is a bitwise OR of any of the following values:

| Flag | Meaning |
| --- | --- |
| DDPF_ALPHA | The pixel format describes an alpha-only surface. |
| DDPF_ALPHAPIXELS | The surface has alpha channel information in the pixel format. |
| DDPF_ALPHAPREMULT | The color components in the pixel are premultiplied by the alpha value in the pixel. If this flag is set, the DDPF_ALPHAPIXELS flag must also be set. If this flag is not set but the DDPF_ALPHAPIXELS flag is set, the color components in the pixel format are not premultiplied by alpha. In this case, the color components must be multiplied by the alpha value at the time that an alpha-blending operation is performed. |
| DDPF_BUMPDUDV | Bump map dUdV data in the pixel format is valid. |
| DDPF_BUMPHEIGHT | Bump map height data in the pixel format is valid. |
| DDPF_COMPRESSED | The surface accepts pixel data in the specified format and compresses it during the write operation. |
| DDPF_D3DFORMAT | Indicates a DirectX 8.0 and later format capability entry in the texture format list. This flag is not exposed to applications. |
| DDPF_FOURCC | The [FOURCC](https://docs.microsoft.com/windows/desktop/directshow/fourcc-codes) code is valid. |
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

Specifies a surface format code including any of the codes in the D3DFORMAT enumerated type. Some [FOURCC](https://docs.microsoft.com/windows/desktop/directshow/fourcc-codes) codes are part of D3DFORMAT. For more information about D3DFORMAT, see the SDK documentation. Hardware vendors can also define and supply format codes that are specific to their hardware.

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

### -field dwYUVAlphaBitMask

### -field dwRGBZBitMask

### -field dwYUVZBitMask

#### - MultiSampleCaps

**DirectX 8.0 and later versions only.** Structure that contains the following two members. It specifies 16-bitmasks for the number of samples per pixel for both flip (fullscreen) and blt (windowed) multisampling. It is used when specifying surfaces that can be used when performing multisample rendering (see the Remarks section). Each bit in these 16-bitmasks indicates support of multisampling with a specific number of samples. For example, bit 0 indicates the support of multisampling with only a single sample, bit 1 indicates the support of multisampling with two samples, bit 2 indicates the support of multisampling with three samples, and so on. The driver can indicate more than one supported level by combining the bits using a bitwise OR (see Remarks).

#### wFlipMSTypes

**DirectX 8.0 and later versions only.** Specifies a 16-bitmask for fullscreen multisampling.

#### wBltMSTypes

**DirectX 8.0 and later versions only.** Specifies a 16-bitmask for windowed multisampling.

#### - dwBumpBitCount

Specifies the total number of bits per "bumpel" (bump-map texel).

#### - dwBumpDuBitMask

Specifies the mask for bump map U delta bits.

#### - dwBumpDvBitMask

Specifies the mask for bump map V delta bits.

#### - dwBumpLuminanceBitMask

Specifies the mask for luminance in a bump map.

#### - dwLuminanceAlphaBitMask

Specifies the mask for luminance in the alpha channel.

#### - dwLuminanceBitCount

Specifies the number of bits per pixel.

#### - dwLuminanceBitMask

Specifies the mask for luminance bits.

#### - dwOperations

**DirectX 8.0 and later versions only.** Specifies the intended operations that can be performed on surfaces with this pixel format, for example, whether such surfaces can be used as textures, bump environment maps, cube maps, volume textures, or render targets. The operations that can be reported are as follows:

| Operation | Meaning |
| --- | --- |
| D3DFORMAT_OP_TEXTURE | When this flag is specified in a pixel format, it indicates that surfaces of this format can be used as MIP mapped textures. |
| D3DFORMAT_OP_VOLUMETEXTURE | When this flag is specified in a pixel format, it indicates that surfaces of this format can be used as volume textures. Please note, that this flag is independent of D3DFORMAT_OP_TEXTURE. Thus, it is possible to specify a pixel format that can only be used for volume textures and not for conventional, MIP mapped textures. |
| D3DFORMAT_OP_CUBETEXTURE | When this flag is specified in a pixel format, it indicates that surfaces of this format can be used as cubic environment map textures. Please note, that this flag is independent of D3DFORMAT_OP_TEXTURE. Thus, it is possible to specify a pixel format that can only be used for cubic environment map textures and not for conventional, MIP mapped textures. |
| D3DFORMAT_OP_OFFSCREEN_RENDERTARGET | When this flag is specified in a pixel format, it indicates that surfaces of this format can be used as an offscreen render target regardless of the pixel format of the display mode (providing the pixel format of the current display mode was reported with the D3DFORMAT_OP_DISPLAYMODE and D3DFORMAT_OP_3DACCELERATION). If the pixel format of the current display mode did not have these flags set it indicates no 3D acceleration is available in this mode even if the render target is offscreen. This flag can be combined with D3DFORMAT_OP_TEXTURE to indicate that the device can render to textures of the specified pixel format. |
| D3DFORMAT_OP_SAME_FORMAT_RENDERTARGET | When this flag is specified in a pixel format, it indicates that surfaces of this format can be used as render targets but only when the pixel format of the surface matches the pixel format of the current display mode. This flag does not only apply to offscreen render target but can be specified on the pixel formats of display modes to indicate rendering target capability. This flag can be combined with D3DFORMAT_OP_TEXTURE to indicate that the device can render to textures of the specified pixel format. |
| D3DFORMAT_OP_ZSTENCIL | When this flag is specified in a pixel format, it indicates that surfaces of this format can be used as Z/Stencil buffers but only if the depth of the Z/Stencil surface matches the color depth of the rendering target to which the depth buffer is attached. When deciding on a match between Z/Stencil and color buffer depth, the pixel stride is used. |
| D3DFORMAT_OP_ZSTENCIL_WITH_ARBITRARY_COLOR_DEPTH | When this flag is specified in a pixel format, it indicates that surfaces of this format can be used as Z/Stencil buffers regardless of the color depth of the render target to which the surface is attached. When specifying this flag you also should specify D3DFORMAT_OP_ZSTENCIL. |
| D3DFORMAT_OP_SAME_FORMAT_UP_TO_ALPHA_RENDERTARGET | When this flag is specified in a pixel format, it indicates that surfaces of this format can be used as a render target if the current display mode is the same depth, if the alpha channel is ignored. For example, if the device can render to A8R8G8B8 when the display mode is X8R8G8B8, then the format operation list entry for A8R8G8B8 should have this flag set. |
| D3DFORMAT_OP_DISPLAYMODE | When this flag is specified, it indicates that there is a display mode with this pixel format that has DirectDraw support (including Flip). This flag should not be set on alpha formats. |
| D3DFORMAT_OP_3DACCELERATION | When this flag is specified, the graphics accelerator can support some level of Direct3D acceleration when in a display mode with this pixel format and also implies that the driver can create a context in this mode (for some render target format). This flag can only be used when reporting display mode formats (by specifying the D3DFORMAT_OP_DISPLAYMODE). It is not required and indeed should not be set when reporting offscreen render targets formats. |
| D3DFORMAT_OP_PIXELSIZE | **DirectX 9.0 and later versions only.** When this flag is specified in a pixel format, it indicates that the driver filled in the bits per pixel for the format in the **dwPrivateFormatBitCount** member. If the driver requires that managed surfaces and textures use a private format (a format that is understood by the driver but not natively by the Direct3D runtime), then the driver must specify this flag, along with the pixel size in **dwPrivateFormatBitCount**. |
| D3DFORMAT_OP_CONVERT_TO_ARGB | **DirectX 9.0 and later versions only.** When this flag is specified in a pixel format, it indicates that source surfaces of this format can be converted to any target surface with an RGB pixel format that has the D3DFORMAT_MEMBEROFGROUP_ARGB flag specified in **dwOperations**. |
| D3DFORMAT_OP_OFFSCREENPLAIN | **DirectX 9.0 and later versions only.** When this flag is specified in a pixel format, it indicates that the driver can stretch to and from and color fill surfaces of this format. |
| D3DFORMAT_OP_SRGBREAD | **DirectX 9.0 and later versions only.** When this flag is specified in a pixel format, it indicates that surfaces of this format can be read from as SRGB textures (that is, the sampler linearizes the looked up data). |
| D3DFORMAT_OP_BUMPMAP | **DirectX 9.0 and later versions only.** When this flag is specified in a pixel format, it indicates that surfaces of this format can be used as bump environment map textures. Note that this flag is independent of D3DFORMAT_OP_TEXTURE. Therefore, you can specify a pixel format that can only be used for bump environment map textures and not for conventional MIP mapped textures. |
| D3DFORMAT_OP_DMAP | **DirectX 9.0 and later versions only.** When this flag is specified in a pixel format, it indicates that surfaces of this format can be sampled by the displacement map sampler. |
| D3DFORMAT_OP_NOFILTER | **DirectX 9.0 and later versions only.** When this flag is specified in a pixel format, it indicates that surfaces of this format cannot be used with texture filtering. |
| D3DFORMAT_MEMBEROFGROUP_ARGB | **DirectX 9.0 and later versions only.** When this flag is specified in a pixel format, it indicates that target surfaces of this format can be converted from any source surface with a pixel format that has the D3DFORMAT_OP_CONVERT_TO_ARGB flag specified in **DirectX 9.0 and later versions only.**. The driver can only specify this flag for ARGB surfaces with at least 5 bits color information per channel. That is, the D3DFMT_A1R5G5B5 format is valid. However, the D3DFMT_A4R4G4B4 format is invalid. If the driver specifies this flag with an invalid format, the runtime prevents the Direct3D HAL from loading. Note that although this flag indicates ARGB formats, the runtime also allows the driver to specify surfaces with XRGB formats (for example, D3DFMT_X1R5G5B5). |
| D3DFORMAT_OP_SRGBWRITE | **DirectX 9.0 and later versions only.** When this flag is specified in a pixel format, it indicates that surfaces of this format can be written to as SRGB targets (that is, the pixel pipe delinearizes data on output to this format). |
| D3DFORMAT_OP_NOALPHABLEND | **DirectX 9.0 and later versions only.** When this flag is specified in a pixel format, it indicates that surfaces of this format cannot be used with alpha blending. |
| D3DFORMAT_OP_AUTOGENMIPMAP | **DirectX 9.0 and later versions only.** When this flag is specified in a pixel format, it indicates that the sublevels of MIP-map textures with this format can be automatically generated. To receive D3DDP2OP_GENERATEMIPSUBLEVELS operation requests, this flag must be exposed. |
| D3DFORMAT_OP_VERTEXTEXTURE | **DirectX 9.0 and later versions only.** When this flag is specified in a pixel format, it indicates that surfaces of this format can be used by a vertex texture sampler. That is, only surfaces of this format can be used as vertex textures. |

#### - dwPrivateFormatBitCount

Specifies the bits per pixel of a pixel format private to the driver (that is, not one of the standard ones defined by Microsoft Direct3D).

#### - dwRGBAlphaBitMask, dwYUVAlphaBitMask

Specify the masks for alpha channel.

#### - dwRGBZBitMask, dwYUVZBitMask

Specifies the masks for the z channel.

#### - dwStencilBitDepth

Specifies the bit depth of the stencil buffer. This member specifies how many bits are reserved within each pixel of the z-buffer for stencil information.

#### - dwStencilBitMask

Specifies the mask for stencil bits within each z-buffer pixel.

#### - dwZBitMask

Specifies the mask for Z bits.

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
ddpf.MultiSampleCaps.wFlipMSTypes = (1 << (D3DMULTISAMPLE_4_SAMPLES âˆ’ 1))
                                  | (1 << (D3DMULTISAMPLE_2_SAMPLES âˆ’ 1));
ddpf.MultiSampleCaps.wBltMSTypes = (1 << (D3DMULTISAMPLE_4_SAMPLES âˆ’ 1));
```

It is not necessary to specify 1 << (D3DMULTISAMPLE_NONE - 1) when reporting formats. It is assumed that any format reported can also be used without multisampling. If the hardware supports multisample rendering with a z-buffer the z-buffer formats reported should also include the supported samples-per-pixels.
