---
UID: NE:d3dukmdt._D3DDDIFORMAT
title: _D3DDDIFORMAT
author: windows-driver-content
description: The D3DDDIFORMAT enumeration type contains values that identify surface formats.
old-location: display\d3dddiformat.htm
old-project: display
ms.assetid: 1ab8f431-867a-4ae2-a1d1-2eeceb6a6966
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DDDIFORMAT, D3DDDIFORMAT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIFORMAT
req.alt-loc: d3dukmdt.h
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
req.typenames: D3DDDIFORMAT
---

# _D3DDDIFORMAT enumeration



## -description
The D3DDDIFORMAT enumeration type contains values that identify surface formats.



## -syntax

````
typedef enum _D3DDDIFORMAT { 
  D3DDDIFMT_UNKNOWN                  = 0,
  D3DDDIFMT_R8G8B8                   = 20,
  D3DDDIFMT_A8R8G8B8                 = 21,
  D3DDDIFMT_X8R8G8B8                 = 22,
  D3DDDIFMT_R5G6B5                   = 23,
  D3DDDIFMT_X1R5G5B5                 = 24,
  D3DDDIFMT_A1R5G5B5                 = 25,
  D3DDDIFMT_A4R4G4B4                 = 26,
  D3DDDIFMT_R3G3B2                   = 27,
  D3DDDIFMT_A8                       = 28,
  D3DDDIFMT_A8R3G3B2                 = 29,
  D3DDDIFMT_X4R4G4B4                 = 30,
  D3DDDIFMT_A2B10G10R10              = 31,
  D3DDDIFMT_A8B8G8R8                 = 32,
  D3DDDIFMT_X8B8G8R8                 = 33,
  D3DDDIFMT_G16R16                   = 34,
  D3DDDIFMT_A2R10G10B10              = 35,
  D3DDDIFMT_A16B16G16R16             = 36,
  D3DDDIFMT_A8P8                     = 40,
  D3DDDIFMT_P8                       = 41,
  D3DDDIFMT_L8                       = 50,
  D3DDDIFMT_A8L8                     = 51,
  D3DDDIFMT_A4L4                     = 52,
  D3DDDIFMT_V8U8                     = 60,
  D3DDDIFMT_L6V5U5                   = 61,
  D3DDDIFMT_X8L8V8U8                 = 62,
  D3DDDIFMT_Q8W8V8U8                 = 63,
  D3DDDIFMT_V16U16                   = 64,
  D3DDDIFMT_W11V11U10                = 65,
  D3DDDIFMT_A2W10V10U10              = 67,
  D3DDDIFMT_UYVY                     = MAKEFOURCC('U', 'Y', 'V', 'Y'),
  D3DDDIFMT_R8G8_B8G8                = MAKEFOURCC('R', 'G', 'B', 'G'),
  D3DDDIFMT_YUY2                     = MAKEFOURCC('Y', 'U', 'U', '2'),
  D3DDDIFMT_G8R8_G8B8                = MAKEFOURCC('G', 'R', 'G', 'B'),
  D3DDDIFMT_DXT1                     = MAKEFOURCC('D', 'X', 'T', '1'),
  D3DDDIFMT_DXT2                     = MAKEFOURCC('D', 'X', 'T', '2'),
  D3DDDIFMT_DXT3                     = MAKEFOURCC('D', 'X', 'T', '3'),
  D3DDDIFMT_DXT4                     = MAKEFOURCC('D', 'X', 'T', '4'),
  D3DDDIFMT_DXT5                     = MAKEFOURC('D', 'X', 'T', '5')C,
  D3DDDIFMT_D16_LOCKABLE             = 70,
  D3DDDIFMT_D32                      = 71,
  D3DDDIFMT_D15S1                    = 73,
  D3DDDIFMT_D24S8                    = 75,
  D3DDDIFMT_D24X8                    = 77,
  D3DDDIFMT_D24X4S4                  = 79,
  D3DDDIFMT_D16                      = 80,
  D3DDDIFMT_D32F_LOCKABLE            = 82,
  D3DDDIFMT_D24FS8                   = 83,
  D3DDDIFMT_D32_LOCKABLE             = 84,
  D3DDDIFMT_S8_LOCKABLE              = 85,
  D3DDDIFMT_S1D15                    = 72,
  D3DDDIFMT_S8D24                    = 74,
  D3DDDIFMT_X8D24                    = 76,
  D3DDDIFMT_X4S4D24                  = 78,
  D3DDDIFMT_L16                      = 81,
#if (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WDDM1_3)
  D3DDDIFMT_G8R8                     = 91,
  D3DDDIFMT_R8                       = 92,
#endif 
  D3DDDIFMT_VERTEXDATA               = 100,
  D3DDDIFMT_INDEX16                  = 101,
  D3DDDIFMT_INDEX32                  = 102,
  D3DDDIFMT_Q16W16V16U16             = 110,
  D3DDDIFMT_MULTI2_ARGB8             = MAKEFOURCC('M', 'E', 'T', '1'),
  D3DDDIFMT_R16F                     = 111,
  D3DDDIFMT_G16R16F                  = 112,
  D3DDDIFMT_A16B16G16R16F            = 113,
  D3DDDIFMT_R32F                     = 114,
  D3DDDIFMT_G32R32F                  = 115,
  D3DDDIFMT_A32B32G32R32F            = 116,
  D3DDDIFMT_CxV8U8                   = 117,
  D3DDDIFMT_A1                       = 118,
  D3DDDIFMT_A2B10G10R10_XR_BIAS      = 119,
  D3DDDIFMT_DXVACOMPBUFFER_BASE      = 150,
  D3DDDIFMT_PICTUREPARAMSDATA        = D3DDDIFMT_DXVACOMPBUFFER_BASE+0,
  D3DDDIFMT_MACROBLOCKDATA           = D3DDDIFMT_DXVACOMPBUFFER_BASE+1,
  D3DDDIFMT_RESIDUALDIFFERENCEDATA   = D3DDDIFMT_DXVACOMPBUFFER_BASE+2,
  D3DDDIFMT_DEBLOCKINGDATA           = D3DDDIFMT_DXVACOMPBUFFER_BASE+3,
  D3DDDIFMT_INVERSEQUANTIZATIONDATA  = D3DDDIFMT_DXVACOMPBUFFER_BASE+4,
  D3DDDIFMT_SLICECONTROLDATA         = D3DDDIFMT_DXVACOMPBUFFER_BASE+5,
  D3DDDIFMT_BITSTREAMDATA            = D3DDDIFMT_DXVACOMPBUFFER_BASE+6,
  D3DDDIFMT_MOTIONVECTORBUFFER       = D3DDDIFMT_DXVACOMPBUFFER_BASE+7,
  D3DDDIFMT_FILMGRAINBUFFER          = D3DDDIFMT_DXVACOMPBUFFER_BASE+8,
  D3DDDIFMT_DXVA_RESERVED9           = D3DDDIFMT_DXVACOMPBUFFER_BASE+9,
  D3DDDIFMT_DXVA_RESERVED10          = D3DDDIFMT_DXVACOMPBUFFER_BASE+10,
  D3DDDIFMT_DXVA_RESERVED11          = D3DDDIFMT_DXVACOMPBUFFER_BASE+11,
  D3DDDIFMT_DXVA_RESERVED12          = D3DDDIFMT_DXVACOMPBUFFER_BASE+12,
  D3DDDIFMT_DXVA_RESERVED13          = D3DDDIFMT_DXVACOMPBUFFER_BASE+13,
  D3DDDIFMT_DXVA_RESERVED14          = D3DDDIFMT_DXVACOMPBUFFER_BASE+14,
  D3DDDIFMT_DXVA_RESERVED15          = D3DDDIFMT_DXVACOMPBUFFER_BASE+15,
  D3DDDIFMT_DXVA_RESERVED16          = D3DDDIFMT_DXVACOMPBUFFER_BASE+16,
  D3DDDIFMT_DXVA_RESERVED17          = D3DDDIFMT_DXVACOMPBUFFER_BASE+17,
  D3DDDIFMT_DXVA_RESERVED18          = D3DDDIFMT_DXVACOMPBUFFER_BASE+18,
  D3DDDIFMT_DXVA_RESERVED19          = D3DDDIFMT_DXVACOMPBUFFER_BASE+19,
  D3DDDIFMT_DXVA_RESERVED20          = D3DDDIFMT_DXVACOMPBUFFER_BASE+20,
  D3DDDIFMT_DXVA_RESERVED21          = D3DDDIFMT_DXVACOMPBUFFER_BASE+21,
  D3DDDIFMT_DXVA_RESERVED22          = D3DDDIFMT_DXVACOMPBUFFER_BASE+22,
  D3DDDIFMT_DXVA_RESERVED23          = D3DDDIFMT_DXVACOMPBUFFER_BASE+23,
  D3DDDIFMT_DXVA_RESERVED24          = D3DDDIFMT_DXVACOMPBUFFER_BASE+24,
  D3DDDIFMT_DXVA_RESERVED25          = D3DDDIFMT_DXVACOMPBUFFER_BASE+25,
  D3DDDIFMT_DXVA_RESERVED26          = D3DDDIFMT_DXVACOMPBUFFER_BASE+26,
  D3DDDIFMT_DXVA_RESERVED27          = D3DDDIFMT_DXVACOMPBUFFER_BASE+27,
  D3DDDIFMT_DXVA_RESERVED28          = D3DDDIFMT_DXVACOMPBUFFER_BASE+28,
  D3DDDIFMT_DXVA_RESERVED29          = D3DDDIFMT_DXVACOMPBUFFER_BASE+29,
  D3DDDIFMT_DXVA_RESERVED30          = D3DDDIFMT_DXVACOMPBUFFER_BASE+30,
  D3DDDIFMT_DXVA_RESERVED31          = D3DDDIFMT_DXVACOMPBUFFER_BASE+31,
  D3DDDIFMT_DXVACOMPBUFFER_MAX       = D3DDDIFMT_DXVA_RESERVED31,
  D3DDDIFMT_BINARYBUFFER             = 199,
  D3DDDIFMT_FORCE_UINT               = 0x7fffffff
} D3DDDIFORMAT;
````


## -enum-fields

### -field D3DDDIFMT_UNKNOWN

An unknown format.


### -field D3DDDIFMT_R8G8B8

24-bit RGB unsigned pixel format with 8 bits for each channel.


### -field D3DDDIFMT_A8R8G8B8

32-bit ARGB unsigned pixel format with alpha that uses 8 bits for each channel.


### -field D3DDDIFMT_X8R8G8B8

32-bit RGB unsigned pixel format, where 8 bits are reserved for each color.


### -field D3DDDIFMT_R5G6B5

16-bit RGB unsigned pixel format with 5 bits for red, 6 bits for green, and 5 bits for blue.


### -field D3DDDIFMT_X1R5G5B5

16-bit unsigned pixel format where 5 bits are reserved for each color.


### -field D3DDDIFMT_A1R5G5B5

16-bit unsigned pixel format where 5 bits are reserved for each color and 1 bit is reserved for alpha.


### -field D3DDDIFMT_A4R4G4B4

16-bit ARGB unsigned pixel format with 4 bits for each channel.


### -field D3DDDIFMT_R3G3B2

8-bit RGB unsigned texture format that uses 3 bits for red, 3 bits for green, and 2 bits for blue.


### -field D3DDDIFMT_A8

8-bit alpha only.


### -field D3DDDIFMT_A8R3G3B2

16-bit ARGB unsigned texture format that uses 8 bits for alpha, 3 bits each for red and green, and 2 bits for blue.


### -field D3DDDIFMT_X4R4G4B4

16-bit RGB unsigned pixel format that uses 4 bits for each color.


### -field D3DDDIFMT_A2B10G10R10

32-bit unsigned pixel format that uses 10 bits for each color and 2 bits for alpha.


### -field D3DDDIFMT_A8B8G8R8

32-bit ARGB unsigned pixel format with alpha that uses 8 bits for each channel.


### -field D3DDDIFMT_X8B8G8R8

32-bit RGB unsigned pixel format, where 8 bits are reserved for each color.


### -field D3DDDIFMT_G16R16

32-bit unsigned pixel format that uses 16 bits each for green and red.


### -field D3DDDIFMT_A2R10G10B10

32-bit unsigned pixel format that uses 10 bits for each color and 2 bits for alpha.


### -field D3DDDIFMT_A16B16G16R16

64-bit unsigned pixel format that uses 16 bits for each component.


### -field D3DDDIFMT_A8P8

8-bit color indexed with 8 bits of alpha.


### -field D3DDDIFMT_P8

8-bit color indexed.


### -field D3DDDIFMT_L8

8-bit luminance only.


### -field D3DDDIFMT_A8L8

16-bit format that uses 8 bits each for alpha and luminance.


### -field D3DDDIFMT_A4L4

8-bit format that uses 4 bits each for alpha and luminance.


### -field D3DDDIFMT_V8U8

16-bit signed bump-map format that uses 8 bits each for u and v data.


### -field D3DDDIFMT_L6V5U5

16-bit mixed signed and unsigned bump-map format with luminance that uses 6 bits for luminance and 5 bits each for v and u data.


### -field D3DDDIFMT_X8L8V8U8

32-bit mixed signed and unsigned bump-map format with luminance that uses 8 bits for each channel.


### -field D3DDDIFMT_Q8W8V8U8

32-bit signed bump-map format that uses 8 bits for each channel.


### -field D3DDDIFMT_V16U16

32-bit signed bump-map format using 16 bits each for u and v data.


### -field D3DDDIFMT_W11V11U10

32-bit signed bump-map format that uses 11 bits each for w and v and 10 bits for u.


### -field D3DDDIFMT_A2W10V10U10

32-bit mixed signed and unsigned bump-map format that uses 2 bits for alpha and 10 bits each for w, v, and u.


### -field D3DDDIFMT_UYVY

UYVY FOURCC format (MAKEFOURCC('U', 'Y', 'V', 'Y')).


### -field D3DDDIFMT_R8G8_B8G8

RGBG FOURCC format (MAKEFOURCC('R', 'G', 'B', 'G')).

A 16-bit packed RGB format that is analogous to UYVY (U0Y0, V0Y1, U2Y2, and so on). RGBG FOURCC format requires a pixel pair to represent the color value. The first pixel in the pair contains 8 bits of green (in the low 8 bits) and 8 bits of red (in the high 8 bits). The second pixel contains 8 bits of green (in the low 8 bits) and 8 bits of blue (in the high 8 bits). The two pixels share the red and blue components, and each has a unique green component (R0G0, B0G1, R2G2, and so on). 

The texture sampler does not normalize the colors when looking up into a pixel shader; they remain in the range from 0.0f through 255.0f. This situation occurs for all programmable pixel shader models. For the fixed function pixel shader, the hardware should normalize to the range from 0.f through 1.f and treat it as the YUY2 texture. Hardware that exposes this format must have the <b>PixelShader1xMaxValue</b> member of the D3DCAPS9 structure set to a value that is capable of handling that range (0.f through 1.f).


### -field D3DDDIFMT_YUY2

YUY2 FOURCC format (MAKEFOURCC('Y', 'U', 'Y', '2')).


### -field D3DDDIFMT_G8R8_G8B8

GRGB FOURCC format (MAKEFOURCC('G', 'R', 'G', 'B')).

A 16-bit packed RGB format that is analogous to YUY2 (Y0U0, Y1V0, Y2U2, and so on). GRGB FOURCC format requires a pixel pair to represent the color value. The first pixel in the pair contains 8 bits of green (in the high 8 bits) and 8 bits of red (in the low 8 bits). The second pixel contains 8 bits of green (in the high 8 bits) and 8 bits of blue (in the low 8 bits). The two pixels share the red and blue components, and each has a unique green component (G0R0, G1B0, G2R2, and so on). 

The texture sampler does not normalize the colors when looking up into a pixel shader; they remain in the range from 0.0f through 255.0f. This situation occurs for all programmable pixel shader models. For the fixed function pixel shader, the hardware should normalize to the range from 0.f through 1.f and treat it as the YUY2 texture. Hardware that exposes this format must have the <b>PixelShader1xMaxValue</b> member of D3DCAPS9 set to a value that is capable of handling that range (0.f through 1.f).


### -field D3DDDIFMT_DXT1

DXT1 FOURCC compression texture format (MAKEFOURCC('D', 'X', 'T', '1')).


### -field D3DDDIFMT_DXT2

DXT2 FOURCC compression texture format (MAKEFOURCC('D', 'X', 'T', '2')).


### -field D3DDDIFMT_DXT3

DXT3 FOURCC compression texture format (MAKEFOURCC('D', 'X', 'T', '3')).


### -field D3DDDIFMT_DXT4

DXT4 FOURCC compression texture format (MAKEFOURCC('D', 'X', 'T', '4')).


### -field D3DDDIFMT_DXT5

DXT5 FOURCC compression texture format (MAKEFOURCC('D', 'X', 'T', '5')).


### -field D3DDDIFMT_D16_LOCKABLE

16-bit z-buffer bit depth.


### -field D3DDDIFMT_D32

32-bit z-buffer bit depth.


### -field D3DDDIFMT_D15S1

16-bit z-buffer bit depth where 15 bits are reserved for the depth channel and 1 bit is reserved for the stencil channel.


### -field D3DDDIFMT_D24S8

32-bit z-buffer bit depth that uses 24 bits for the depth channel and 8 bits for the stencil channel.


### -field D3DDDIFMT_D24X8

32-bit z-buffer bit depth that uses 24 bits for the depth channel.


### -field D3DDDIFMT_D24X4S4

32-bit z-buffer bit depth that uses 24 bits for the depth channel and 4 bits for the stencil channel.


### -field D3DDDIFMT_D16

16-bit z-buffer bit depth.


### -field D3DDDIFMT_D32F_LOCKABLE

A lockable buffer format where the depth value is represented as a standard IEEE floating-point number.


### -field D3DDDIFMT_D24FS8

A non-lockable buffer format that contains 24 bits of depth (in a 24-bit floating point format: - 20e4) and 8 bits of stencil.


### -field D3DDDIFMT_D32_LOCKABLE

A lockable buffer format that uses 32 bits for the depth channel.


### -field D3DDDIFMT_S8_LOCKABLE

A lockable buffer format that uses 8 bits for the stencil channel.


### -field D3DDDIFMT_S1D15

16-bit z-buffer bit depth where 15 bits are reserved for the depth channel and 1 bit is reserved for the stencil channel.


### -field D3DDDIFMT_S8D24

32-bit z-buffer bit depth that uses 24 bits for the depth channel and 8 bits for the stencil channel.


### -field D3DDDIFMT_X8D24

32-bit z-buffer bit depth that uses 24 bits for the depth channel.


### -field D3DDDIFMT_X4S4D24

32-bit z-buffer bit depth that uses 24 bits for the depth channel and 4 bits for the stencil channel.


### -field D3DDDIFMT_L16

16-bit luminance only.


### -field D3DDDIFMT_G8R8

A two-component, 16-bit unsigned-normalized-integer format that supports 8 bits for the red channel and 8 bits for the green channel. Equivalent to <b>DXGI_FORMAT_R8G8_UNORM</b> from the <a href="https://msdn.microsoft.com/dce61bc4-4ed5-4e64-84e8-6db88025e5c2">DXGI_FORMAT</a> enumeration.


### -field D3DDDIFMT_R8

A single-component, 8-bit unsigned-normalized-integer format that supports 8 bits for the red channel. Equivalent to <b>DXGI_FORMAT_R8_UNORM</b> from the <a href="https://msdn.microsoft.com/dce61bc4-4ed5-4e64-84e8-6db88025e5c2">DXGI_FORMAT</a> enumeration.


### -field D3DDDIFMT_VERTEXDATA

A vertex buffer surface.


### -field D3DDDIFMT_INDEX16

16-bit index buffer bit depth.


### -field D3DDDIFMT_INDEX32

32-bit index buffer bit depth.


### -field D3DDDIFMT_Q16W16V16U16

64-bit signed bump-map format that uses 16 bits for each channel.


### -field D3DDDIFMT_MULTI2_ARGB8

MultiElement FOURCC noncompressed texture (MAKEFOURCC('M','E','T','1')).


### -field D3DDDIFMT_R16F

16-bit s10e5 floating-point surface format that uses 16 bits for the red channel.


### -field D3DDDIFMT_G16R16F

32-bit s10e5 floating-point surface format that uses 16 bits for the red channel and 16 bits for the green channel.


### -field D3DDDIFMT_A16B16G16R16F

64-bit s10e5 floating-point surface format that uses 16 bits for each channel (alpha, blue, green, and red).


### -field D3DDDIFMT_R32F

32-bit s23e8 floating-point surface format that uses 32 bits for the red channel.


### -field D3DDDIFMT_G32R32F

64-bit s23e8 floating-point surface format that uses 32 bits for the red channel and 32 bits for the green channel.


### -field D3DDDIFMT_A32B32G32R32F

128-bit s23e8 floating-point surface format that uses 32 bits for the each channel (alpha, blue, green, and red).


### -field D3DDDIFMT_CxV8U8

16-bit signed normal compression format. The texture sampler computes the C channel from: C = sqrt(1 - U2 - V2).


### -field D3DDDIFMT_A1

A monochrome 1-bit per pixel format. 


### -field D3DDDIFMT_A2B10G10R10_XR_BIAS

Supported in Windows 7 and later versions.

32-bit unsigned pixel format that uses 10 bits for each color and 2 bits for alpha along with 2.8 biased fixed point. 


### -field D3DDDIFMT_DXVACOMPBUFFER_BASE

A base compressed buffer format value. 


### -field D3DDDIFMT_PICTUREPARAMSDATA

Picture parameters decode compressed buffer format.


### -field D3DDDIFMT_MACROBLOCKDATA

Macroblock control command decode compressed buffer format.


### -field D3DDDIFMT_RESIDUALDIFFERENCEDATA

Residual block difference decode compressed buffer format.


### -field D3DDDIFMT_DEBLOCKINGDATA

Deblocking filter control command decode compressed buffer format.


### -field D3DDDIFMT_INVERSEQUANTIZATIONDATA

Inverse-quantization matrix decode compressed buffer format.


### -field D3DDDIFMT_SLICECONTROLDATA

Slice-control decode compressed buffer format.


### -field D3DDDIFMT_BITSTREAMDATA

Bitstream data decode compressed buffer format.


### -field D3DDDIFMT_MOTIONVECTORBUFFER

Motion-vector decode compressed buffer format.


### -field D3DDDIFMT_FILMGRAINBUFFER

Film-grain decode compressed buffer format.


### -field D3DDDIFMT_DXVA_RESERVED9

Reserved for a DirectX VA format type.


### -field D3DDDIFMT_DXVA_RESERVED10

Reserved for a DirectX VA format type.


### -field D3DDDIFMT_DXVA_RESERVED11

Reserved for a DirectX VA format type.


### -field D3DDDIFMT_DXVA_RESERVED12

Reserved for a DirectX VA format type.


### -field D3DDDIFMT_DXVA_RESERVED13

Reserved for a DirectX VA format type.


### -field D3DDDIFMT_DXVA_RESERVED14

Reserved for a DirectX VA format type.


### -field D3DDDIFMT_DXVA_RESERVED15

Reserved for a DirectX VA format type.


### -field D3DDDIFMT_DXVA_RESERVED16

Reserved for a DirectX VA format type.


### -field D3DDDIFMT_DXVA_RESERVED17

Reserved for a DirectX VA format type.


### -field D3DDDIFMT_DXVA_RESERVED18

Reserved for a DirectX VA format type.


### -field D3DDDIFMT_DXVA_RESERVED19

Reserved for a DirectX VA format type.


### -field D3DDDIFMT_DXVA_RESERVED20

Reserved for a DirectX VA format type.


### -field D3DDDIFMT_DXVA_RESERVED21

Reserved for a DirectX VA format type.


### -field D3DDDIFMT_DXVA_RESERVED22

Reserved for a DirectX VA format type.


### -field D3DDDIFMT_DXVA_RESERVED23

Reserved for a DirectX VA format type.


### -field D3DDDIFMT_DXVA_RESERVED24

Reserved for a DirectX VA format type.


### -field D3DDDIFMT_DXVA_RESERVED25

Reserved for a DirectX VA format type.


### -field D3DDDIFMT_DXVA_RESERVED26

Reserved for a DirectX VA format type.


### -field D3DDDIFMT_DXVA_RESERVED27

Reserved for a DirectX VA format type.


### -field D3DDDIFMT_DXVA_RESERVED28

Reserved for a DirectX VA format type.


### -field D3DDDIFMT_DXVA_RESERVED29

Reserved for a DirectX VA format type.


### -field D3DDDIFMT_DXVA_RESERVED30

Reserved for a DirectX VA format type.


### -field D3DDDIFMT_DXVA_RESERVED31

Reserved for a DirectX VA format type.


### -field D3DDDIFMT_DXVACOMPBUFFER_MAX

Indicates that the maximum compressed buffer format value was reached.


### -field D3DDDIFMT_BINARYBUFFER

A binary-buffer format.


### -field D3DDDIFMT_FORCE_UINT

Forces this enumeration to compile to 32 bits in size. Without this value, some compilers would allow this enumeration to compile to a size other than 32 bits. You should not use this value.


## -remarks
Note that formats are supplied by hardware vendors and many FOURCC codes are not listed in the D3DDDIFORMAT enumeration type. The formats in D3DDDIFORMAT are unique because they are sanctioned by the Microsoft Direct3D runtime; that is, the reference rasterizer operates on all of them. Vendors support vendor-supplied formats on a card-by-card basis.


## -see-also
<dl>
<dt>
<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddiarg_createresource.md">D3DDDIARG_CREATERESOURCE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/dce61bc4-4ed5-4e64-84e8-6db88025e5c2">DXGI_FORMAT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIFORMAT enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

