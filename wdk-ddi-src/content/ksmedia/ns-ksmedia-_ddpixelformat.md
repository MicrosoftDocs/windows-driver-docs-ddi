---
UID: NS:ksmedia._DDPIXELFORMAT
title: "_DDPIXELFORMAT"
author: windows-driver-content
description: The DDPIXELFORMAT structure describes the pixel format of a DirectDrawSurface object.
old-location: display\ddpixelformat.htm
old-project: display
ms.assetid: bbc26c03-c154-4b1e-883e-2942b59ded02
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: LPDDPIXELFORMAT, DDPIXELFORMAT, DDPIXELFORMAT structure [Display Devices], ksmedia/DDPIXELFORMAT, display.ddpixelformat, ddstrcts_861a4798-418e-492a-b4cb-c4f1ce794a71.xml, LPDDPIXELFORMAT structure pointer [Display Devices], ksmedia/LPDDPIXELFORMAT, _DDPIXELFORMAT, *LPDDPIXELFORMAT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	DDPIXELFORMAT
product: Windows
targetos: Windows
req.typenames: DDPIXELFORMAT, *LPDDPIXELFORMAT
---

# _DDPIXELFORMAT structure


## -description


The DDPIXELFORMAT structure describes the pixel format of a DirectDrawSurface object. 


## -syntax


````
typedef struct _DDPIXELFORMAT {
  DWORD dwSize;
  DWORD dwFlags;
  DWORD dwFourCC;
  union {
    DWORD dwRGBBitCount;
    DWORD dwYUVBitCount;
    DWORD dwZBufferBitDepth;
    DWORD dwAlphaBitDepth;
    DWORD dwLuminanceBitCount;
    DWORD dwBumpBitCount;
    DWORD dwPrivateFormatBitCount;
  };
  union {
    DWORD dwRBitMask;
    DWORD dwYBitMask;
    DWORD dwStencilBitDepth;
    DWORD dwLuminanceBitMask;
    DWORD dwBumpDuBitMask;
    DWORD dwOperations;
  };
  union {
    DWORD  dwGBitMask;
    DWORD  dwUBitMask;
    DWORD  dwZBitMask;
    DWORD  dwBumpDvBitMask;
    struct {
      WORD wFlipMSTypes;
      WORD wBltMSTypes;
    } MultiSampleCaps;
  };
  union {
    DWORD dwBBitMask;
    DWORD dwVBitMask;
    DWORD dwStencilBitMask;
    DWORD dwBumpLuminanceBitMask;
  };
  union {
    DWORD dwRGBAlphaBitMask, dwYUVAlphaBitMask;
    DWORD dwLuminanceAlphaBitMask;
    DWORD dwRGBZBitMask, dwYUVZBitMask;
  };
} DDPIXELFORMAT, *LPDDPIXELFORMAT;
````


## -struct-fields




### -field dwSize

Specifies the size in bytes of the DDPIXELFORMAT structure. The driver must initialize this member before the structure is used.

<b>DirectX 9.0 and later versions only.</b> Specifies, on input, the version of the Microsoft DirectX runtime being used by the application. This member is set to DD_RUNTIME_VERSION, which is 0x00000900 for DirectX 9.0, in the <b>format</b> member of the <a href="..\d3dhal\ns-d3dhal-_dd_getformatdata.md">DD_GETFORMATDATA</a> structure for a D3DGDI2_TYPE_GETFORMAT query.


### -field dwFlags

Indicates a set of flags that specify optional control flags. This member is a bitwise OR of any of the following values:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DDPF_ALPHA

</td>
<td>
The pixel format describes an alpha-only surface.

</td>
</tr>
<tr>
<td>
DDPF_ALPHAPIXELS

</td>
<td>
The surface has alpha channel information in the pixel format.

</td>
</tr>
<tr>
<td>
DDPF_ALPHAPREMULT

</td>
<td>
The color components in the pixel are premultiplied by the alpha value in the pixel. If this flag is set, the DDPF_ALPHAPIXELS flag must also be set. If this flag is not set but the DDPF_ALPHAPIXELS flag is set, the color components in the pixel format are not premultiplied by alpha. In this case, the color components must be multiplied by the alpha value at the time that an alpha-blending operation is performed.

</td>
</tr>
<tr>
<td>
DDPF_BUMPDUDV

</td>
<td>
Bump map dUdV data in the pixel format is valid.

</td>
</tr>
<tr>
<td>
DDPF_BUMPHEIGHT

</td>
<td>
Bump map height data in the pixel format is valid.

</td>
</tr>
<tr>
<td>
DDPF_COMPRESSED

</td>
<td>
The surface accepts pixel data in the specified format and compresses it during the write operation.

</td>
</tr>
<tr>
<td>
DDPF_D3DFORMAT

</td>
<td>
Indicates a DirectX 8.0 and later format capability entry in the texture format list. This flag is not exposed to applications.

</td>
</tr>
<tr>
<td>
DDPF_FOURCC

</td>
<td>
The <a href="https://msdn.microsoft.com/f697e0db-1db0-4a81-94d8-0ca079885480">FOURCC</a> code is valid.

</td>
</tr>
<tr>
<td>
DDPF_LUMINANCE

</td>
<td>
Luminance data in the pixel format is valid. Use this flag for luminance-only or luminance-plus-alpha surfaces; the bit depth is then specified in the <b>dwLuminanceBitCount</b> member.

</td>
</tr>
<tr>
<td>
DDPF_LUMINANCEPIXELS

</td>
<td>
Luminance data in the pixel format is valid. Use this flag when hanging luminance off, for example, bumpmap surfaces. The bitmask for the luminance portion of the pixel is then specified in the <b>dwBumpLuminanceBitMask</b> member.

</td>
</tr>
<tr>
<td>
DDPF_NOVEL_TEXTURE_FORMAT

</td>
<td>
Indicates a new surface format that the runtime might not expose to all applications.

</td>
</tr>
<tr>
<td>
DDPF_PALETTEINDEXED1

</td>
<td>
The surface is 1-bit color indexed.

</td>
</tr>
<tr>
<td>
DDPF_PALETTEINDEXED2

</td>
<td>
The surface is 2-bit color indexed.

</td>
</tr>
<tr>
<td>
DDPF_PALETTEINDEXED4

</td>
<td>
The surface is 4-bit color indexed.

</td>
</tr>
<tr>
<td>
DDPF_PALETTEINDEXED8

</td>
<td>
The surface is 8-bit color indexed.

</td>
</tr>
<tr>
<td>
DDPF_PALETTEINDEXEDTO8

</td>
<td>
The surface is 1-, 2-, or 4-bit color indexed to an 8-bit palette.

</td>
</tr>
<tr>
<td>
DDPF_RGB

</td>
<td>
The RGB data in the pixel format structure is valid.

</td>
</tr>
<tr>
<td>
DDPF_RGBTOYUV

</td>
<td>
The surface accepts RGB data and translates it during the write operation to YUV data. The format of the data to be written is contained in the pixel format structure. The DDPF_RGB flag is set.

</td>
</tr>
<tr>
<td>
DDPF_STENCILBUFFER

</td>
<td>
The surface encodes stencil and depth information in each pixel of the z-buffer.

</td>
</tr>
<tr>
<td>
DDPF_YUV

</td>
<td>
The YUV data in the pixel format structure is valid.

</td>
</tr>
<tr>
<td>
DDPF_ZBUFFER

</td>
<td>
The pixel format describes a z-buffer-only surface.

</td>
</tr>
<tr>
<td>
DDPF_ZPIXELS

</td>
<td>
The surface is in RGBZ format.

</td>
</tr>
</table>
 


### -field dwFourCC

Specifies a surface format code including any of the codes in the D3DFORMAT enumerated type. Some <a href="https://msdn.microsoft.com/f697e0db-1db0-4a81-94d8-0ca079885480">FOURCC</a> codes are part of D3DFORMAT. For more information about D3DFORMAT, see the SDK documentation. Hardware vendors can also define and supply format codes that are specific to their hardware. 


#### - dwRGBBitCount

Specifies the number of RGB bits per pixel (4, 8, 16, 24, or 32). 


#### - dwYUVBitCount

Specifies the number of YUV bits per pixel. 


#### - dwZBufferBitDepth

Specifies the Z-buffer bit depth (8, 16, 24, or 32 bits). 


#### - dwAlphaBitDepth

Specifies the Alpha channel bit depth. 


#### - dwLuminanceBitCount

Specifies the number of bits per pixel.


#### - dwBumpBitCount

Specifies the total number of bits per "bumpel" (bump-map texel).


#### - dwPrivateFormatBitCount

Specifies the bits per pixel of a pixel format private to the driver (that is, not one of the standard ones defined by Microsoft Direct3D).


#### - dwRBitMask

Specifies the mask for red bits. 


#### - dwYBitMask

Specifies the mask for Y bits. 


#### - dwStencilBitDepth

Specifies the bit depth of the stencil buffer. This member specifies how many bits are reserved within each pixel of the z-buffer for stencil information.


#### - dwLuminanceBitMask

Specifies the mask for luminance bits.


#### - dwBumpDuBitMask

Specifies the mask for bump map U delta bits.


#### - dwOperations

<b>DirectX 8.0 and later versions only.</b> Specifies the intended operations that can be performed on surfaces with this pixel format, for example, whether such surfaces can be used as textures, bump environment maps, cube maps, volume textures, or render targets. The operations that can be reported are as follows:

<table>
<tr>
<th>Operation</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3DFORMAT_OP_TEXTURE

</td>
<td>
When this flag is specified in a pixel format, it indicates that surfaces of this format can be used as MIP mapped textures.

</td>
</tr>
<tr>
<td>
D3DFORMAT_OP_VOLUMETEXTURE

</td>
<td>
When this flag is specified in a pixel format, it indicates that surfaces of this format can be used as volume textures. Please note, that this flag is independent of D3DFORMAT_OP_TEXTURE. Thus, it is possible to specify a pixel format that can only be used for volume textures and not for conventional, MIP mapped textures.

</td>
</tr>
<tr>
<td>
D3DFORMAT_OP_CUBETEXTURE

</td>
<td>
When this flag is specified in a pixel format, it indicates that surfaces of this format can be used as cubic environment map textures. Please note, that this flag is independent of D3DFORMAT_OP_TEXTURE. Thus, it is possible to specify a pixel format that can only be used for cubic environment map textures and not for conventional, MIP mapped textures.

</td>
</tr>
<tr>
<td>
D3DFORMAT_OP_OFFSCREEN_RENDERTARGET

</td>
<td>
When this flag is specified in a pixel format, it indicates that surfaces of this format can be used as an offscreen render target regardless of the pixel format of the display mode (providing the pixel format of the current display mode was reported with the D3DFORMAT_OP_DISPLAYMODE and D3DFORMAT_OP_3DACCELERATION). If the pixel format of the current display mode did not have these flags set it indicates no 3D acceleration is available in this mode even if the render target is offscreen. This flag can be combined with D3DFORMAT_OP_TEXTURE to indicate that the device can render to textures of the specified pixel format.

</td>
</tr>
<tr>
<td>
D3DFORMAT_OP_SAME_FORMAT_RENDERTARGET

</td>
<td>
When this flag is specified in a pixel format, it indicates that surfaces of this format can be used as render targets but only when the pixel format of the surface matches the pixel format of the current display mode. This flag does not only apply to offscreen render target but can be specified on the pixel formats of display modes to indicate rendering target capability. This flag can be combined with D3DFORMAT_OP_TEXTURE to indicate that the device can render to textures of the specified pixel format.

</td>
</tr>
<tr>
<td>
D3DFORMAT_OP_ZSTENCIL

</td>
<td>
When this flag is specified in a pixel format, it indicates that surfaces of this format can be used as Z/Stencil buffers but only if the depth of the Z/Stencil surface matches the color depth of the rendering target to which the depth buffer is attached. When deciding on a match between Z/Stencil and color buffer depth, the pixel stride is used.

</td>
</tr>
<tr>
<td>
D3DFORMAT_OP_ZSTENCIL_WITH_ARBITRARY_COLOR_DEPTH

</td>
<td>
When this flag is specified in a pixel format, it indicates that surfaces of this format can be used as Z/Stencil buffers regardless of the color depth of the render target to which the surface is attached. When specifying this flag you also should specify D3DFORMAT_OP_ZSTENCIL.

</td>
</tr>
<tr>
<td>
D3DFORMAT_OP_SAME_FORMAT_UP_TO_ALPHA_RENDERTARGET

</td>
<td>
When this flag is specified in a pixel format, it indicates that surfaces of this format can be used as a render target if the current display mode is the same depth, if the alpha channel is ignored. For example, if the device can render to A8R8G8B8 when the display mode is X8R8G8B8, then the format operation list entry for A8R8G8B8 should have this flag set.

</td>
</tr>
<tr>
<td>
D3DFORMAT_OP_DISPLAYMODE

</td>
<td>
When this flag is specified, it indicates that there is a display mode with this pixel format that has DirectDraw support (including Flip). This flag should not be set on alpha formats.

</td>
</tr>
<tr>
<td>
D3DFORMAT_OP_3DACCELERATION

</td>
<td>
When this flag is specified, the graphics accelerator can support some level of Direct3D acceleration when in a display mode with this pixel format and also implies that the driver can create a context in this mode (for some render target format). This flag can only be used when reporting display mode formats (by specifying the D3DFORMAT_OP_DISPLAYMODE). It is not required and indeed should not be set when reporting offscreen render targets formats.

</td>
</tr>
<tr>
<td>
D3DFORMAT_OP_PIXELSIZE

</td>
<td>

<dl>
<dt><b>DirectX 9.0 and later versions only.</b></dt>
<dt>When this flag is specified in a pixel format, it indicates that the driver filled in the bits per pixel for the format in the <b>dwPrivateFormatBitCount</b> member. </dt>
<dt>If the driver requires that managed surfaces and textures use a private format (a format that is understood by the driver but not natively by the Direct3D runtime), then the driver must specify this flag, along with the pixel size in <b>dwPrivateFormatBitCount</b>.</dt>
</dl>


</td>
</tr>
<tr>
<td>
D3DFORMAT_OP_CONVERT_TO_ARGB

</td>
<td>

<dl>
<dt><b>DirectX 9.0 and later versions only.</b></dt>
<dt>When this flag is specified in a pixel format, it indicates that source surfaces of this format can be converted to any target surface with an RGB pixel format that has the D3DFORMAT_MEMBEROFGROUP_ARGB flag specified in <b>dwOperations</b>.</dt>
</dl>


</td>
</tr>
<tr>
<td>
D3DFORMAT_OP_OFFSCREENPLAIN

</td>
<td>

<dl>
<dt><b>DirectX 9.0 and later versions only.</b></dt>
<dt>When this flag is specified in a pixel format, it indicates that the driver can stretch to and from and color fill surfaces of this format.</dt>
</dl>


</td>
</tr>
<tr>
<td>
D3DFORMAT_OP_SRGBREAD

</td>
<td>

<dl>
<dt><b>DirectX 9.0 and later versions only.</b></dt>
<dt>When this flag is specified in a pixel format, it indicates that surfaces of this format can be read from as SRGB textures (that is, the sampler linearizes the looked up data).</dt>
</dl>


</td>
</tr>
<tr>
<td>
D3DFORMAT_OP_BUMPMAP

</td>
<td>

<dl>
<dt><b>DirectX 9.0 and later versions only.</b></dt>
<dt>When this flag is specified in a pixel format, it indicates that surfaces of this format can be used as bump environment map textures.</dt>
<dt>Note that this flag is independent of D3DFORMAT_OP_TEXTURE. Therefore, you can specify a pixel format that can only be used for bump environment map textures and not for conventional MIP mapped textures.</dt>
</dl>


</td>
</tr>
<tr>
<td>
D3DFORMAT_OP_DMAP

</td>
<td>

<dl>
<dt><b>DirectX 9.0 and later versions only.</b></dt>
<dt>When this flag is specified in a pixel format, it indicates that surfaces of this format can be sampled by the displacement map sampler.</dt>
</dl>


</td>
</tr>
<tr>
<td>
D3DFORMAT_OP_NOFILTER

</td>
<td>

<dl>
<dt><b>DirectX 9.0 and later versions only.</b></dt>
<dt>When this flag is specified in a pixel format, it indicates that surfaces of this format cannot be used with texture filtering.</dt>
</dl>


</td>
</tr>
<tr>
<td>
D3DFORMAT_MEMBEROFGROUP_ARGB

</td>
<td>

<dl>
<dt><b>DirectX 9.0 and later versions only.</b></dt>
<dt>When this flag is specified in a pixel format, it indicates that target surfaces of this format can be converted from any source surface with a pixel format that has the D3DFORMAT_OP_CONVERT_TO_ARGB flag specified in <b>DirectX 9.0 and later versions only.</b>.</dt>
<dt>The driver can only specify this flag for ARGB surfaces with at least 5 bits color information per channel. That is, the D3DFMT_A1R5G5B5 format is valid. However, the D3DFMT_A4R4G4B4 format is invalid. If the driver specifies this flag with an invalid format, the runtime prevents the Direct3D HAL from loading. Note that although this flag indicates ARGB formats, the runtime also allows the driver to specify surfaces with XRGB formats (for example, D3DFMT_X1R5G5B5).</dt>
</dl>


</td>
</tr>
<tr>
<td>
D3DFORMAT_OP_SRGBWRITE

</td>
<td>

<dl>
<dt><b>DirectX 9.0 and later versions only.</b></dt>
<dt>When this flag is specified in a pixel format, it indicates that surfaces of this format can be written to as SRGB targets (that is, the pixel pipe delinearizes data on output to this format).</dt>
</dl>


</td>
</tr>
<tr>
<td>
D3DFORMAT_OP_NOALPHABLEND

</td>
<td>

<dl>
<dt><b>DirectX 9.0 and later versions only.</b></dt>
<dt>When this flag is specified in a pixel format, it indicates that surfaces of this format cannot be used with alpha blending.</dt>
</dl>


</td>
</tr>
<tr>
<td>
D3DFORMAT_OP_AUTOGENMIPMAP

</td>
<td>

<dl>
<dt><b>DirectX 9.0 and later versions only.</b></dt>
<dt>When this flag is specified in a pixel format, it indicates that the sublevels of MIP-map textures with this format can be automatically generated. To receive D3DDP2OP_GENERATEMIPSUBLEVELS operation requests, this flag must be exposed. </dt>
</dl>


</td>
</tr>
<tr>
<td>
D3DFORMAT_OP_VERTEXTEXTURE

</td>
<td>

<dl>
<dt><b>DirectX 9.0 and later versions only.</b></dt>
<dt>When this flag is specified in a pixel format, it indicates that surfaces of this format can be used by a vertex texture sampler. That is, only surfaces of this format can be used as vertex textures. </dt>
</dl>


</td>
</tr>
</table>
 


#### - dwGBitMask

Specifies the mask for green bits. 


#### - dwUBitMask

Specifies the mask for U bits. 


#### - dwZBitMask

Specifies the mask for Z bits.


#### - dwBumpDvBitMask

Specifies the mask for bump map V delta bits.


#### - MultiSampleCaps

<b>DirectX 8.0 and later versions only.</b> Structure that contains the following two members. It specifies 16-bitmasks for the number of samples per pixel for both flip (fullscreen) and blt (windowed) multisampling. It is used when specifying surfaces that can be used when performing multisample rendering (see the Remarks section). Each bit in these 16-bitmasks indicates support of multisampling with a specific number of samples. For example, bit 0 indicates the support of multisampling with only a single sample, bit 1 indicates the support of multisampling with two samples, bit 2 indicates the support of multisampling with three samples, and so on. The driver can indicate more than one supported level by combining the bits using a bitwise OR (see Remarks).



#### wFlipMSTypes

<b>DirectX 8.0 and later versions only.</b> Specifies a 16-bitmask for fullscreen multisampling.



#### wBltMSTypes

<b>DirectX 8.0 and later versions only.</b> Specifies a 16-bitmask for windowed multisampling.


#### - dwBBitMask

Specifies the mask for blue bits. 


#### - dwVBitMask

Specifies the mask for V bits. 


#### - dwStencilBitMask

Specifies the mask for stencil bits within each z-buffer pixel.


#### - dwBumpLuminanceBitMask

Specifies the mask for luminance in a bump map.


#### - dwRGBAlphaBitMask, dwYUVAlphaBitMask

Specify the masks for alpha channel. 


#### - dwLuminanceAlphaBitMask

Specifies the mask for luminance in the alpha channel.


#### - dwRGBZBitMask, dwYUVZBitMask

Specifies the masks for the z channel. 


## -remarks



The DirectX 8.0 and later runtime imposes the following rules on the operation (op) list:

<ul>
<li>
Only one Endian-ness (big or little) for any DS format is allowed, for example D15S1 or S1D15, not both independent of other bits.

</li>
<li>
A list should only include D3DFORMAT_OP_DISPLAYMODE for exactly one 16bpp format (for example it should not enumerate 5:5:5 and 5:6:5).

</li>
<li>
A list should not contain any alpha formats with D3DFORMAT_OP_DISPLAYMODE or D3DFORMAT_OP_3DACCELLERATION set.

</li>
<li>
The D3DFORMAT_OP_3DACCELLERATION flag can only be set when the D3DFORMAT_OP_DISPLAYMODE flag is also set.

</li>
</ul>
If the driver supports a lockable D16, it should report D3DFMT_D16_LOCKABLE in the op list; otherwise, it should report D3DFMT_D16.

Drivers supporting multisampling must fill in the <b>MultiSampleCaps</b> in the Depth/Stencil formats for which multisampling can be supported. This allows the runtime to detect if a driver supports multisampling for combinations of render target and Z buffer formats. For additional information about the restrictions related to stretch blt multisampling, see the description of D3DPRASTERCAPS_STRETCHBLTMULTISAMPLE cap in the rastercaps contained in the D3DCAPS8 structure in the SDK documentation.

The enumerated type D3DMULTISAMPLE_TYPE defined in <i>d3d8types.h</i> is used when setting the bits in <b>wFlipMSTypes</b> and <b>wBltMSTypes</b>. To specify support for a specific number of samples per pixel, simply logically shift 1 by the appropriate value from the D3DMULTISAMPLE_TYPE enumerated type less 1 and OR this into the appropriate field (<b>wFlipMSTypes</b> and <b>wBltMSTypes</b>).

For example, if the driver supports both two and four samples per pixel when flipping (fullscreen mode) and four samples per pixel when blitting (windowed mode) on X8R8G8B8 surface the following entry would be reported in the surface format list.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>DDPIXELFORMAT ddpf;
ZeroMemory(&amp;ddpf, sizeof(ddpf));
ddpf.dwSize       = sizeof(DDPIXELFORMAT);
ddpf.dwFlags      = DDPF_D3DFORMAT;
ddpf.dwFourCC     = D3DFMT_X8R8G8B8;
ddpf.dwOperations = D3DFORMAT_OP_DISPLAYMODE |
                    D3DFORMAT_OP_3DACCELERATION;
ddpf.MultiSampleCaps.wFlipMSTypes = (1 &lt;&lt; (D3DMULTISAMPLE_4_SAMPLES âˆ’ 1))
                                  | (1 &lt;&lt; (D3DMULTISAMPLE_2_SAMPLES âˆ’ 1));
ddpf.MultiSampleCaps.wBltMSTypes = (1 &lt;&lt; (D3DMULTISAMPLE_4_SAMPLES âˆ’ 1));</pre>
</td>
</tr>
</table></span></div>
It is not necessary to specify 1 &lt;&lt; (D3DMULTISAMPLE_NONE - 1) when reporting formats. It is assumed that any format reported can also be used without multisampling. If the hardware supports multisample rendering with a z-buffer the z-buffer formats reported should also include the supported samples-per-pixels.



