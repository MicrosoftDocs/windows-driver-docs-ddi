---
UID: NS:d3dhal._D3DHAL_D3DEXTENDEDCAPS
title: "_D3DHAL_D3DEXTENDEDCAPS"
author: windows-driver-content
description: D3DHAL_D3DEXTENDEDCAPS describes additional 3D capabilities of the driver.
old-location: display\d3dhal_d3dextendedcaps.htm
old-project: display
ms.assetid: b1e63dce-6d51-438c-a4aa-cc17d9292576
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DHAL_D3DEXTENDEDCAPS structure [Display Devices], display.d3dhal_d3dextendedcaps, _D3DHAL_D3DEXTENDEDCAPS, *LPD3DHAL_D3DEXTENDEDCAPS, d3dstrct_f8cf62b4-6fd7-4a14-aa62-61e8f51ed444.xml, d3dhal/LPD3DHAL_D3DEXTENDEDCAPS, d3dhal/D3DHAL_D3DEXTENDEDCAPS, LPD3DHAL_D3DEXTENDEDCAPS, LPD3DHAL_D3DEXTENDEDCAPS structure pointer [Display Devices], D3DHAL_D3DEXTENDEDCAPS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
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
-	d3dhal.h
apiname:
-	D3DHAL_D3DEXTENDEDCAPS
product: Windows
targetos: Windows
req.typenames: D3DHAL_D3DEXTENDEDCAPS
---

# _D3DHAL_D3DEXTENDEDCAPS structure


## -description


D3DHAL_D3DEXTENDEDCAPS describes additional 3D capabilities of the driver.


## -syntax


````
typedef struct _D3DHAL_D3DEXTENDEDCAPS {
  DWORD    dwSize;
  DWORD    dwMinTextureWidth, dwMaxTextureWidth;
  DWORD    dwMinTextureHeight, dwMaxTextureHeight;
  DWORD    dwMinStippleWidth, dwMaxStippleWidth;
  DWORD    dwMinStippleHeight, dwMaxStippleHeight;
  DWORD    dwMaxTextureRepeat;
  DWORD    dwMaxTextureAspectRatio;
  DWORD    dwMaxAnisotropy;
  D3DVALUE dvGuardBandLeft;
  D3DVALUE dvGuardBandTop;
  D3DVALUE dvGuardBandRight;
  D3DVALUE dvGuardBandBottom;
  D3DVALUE dvExtentsAdjust;
  DWORD    dwStencilCaps;
  DWORD    dwFVFCaps;
  DWORD    dwTextureOpCaps;
  WORD     wMaxTextureBlendStages;
  WORD     wMaxSimultaneousTextures;
#if (DIRECT3D_VERSION >= 0x0700)
  DWORD    dwMaxActiveLights;
  D3DVALUE dvMaxVertexW;
  WORD     wMaxUserClipPlanes;
  WORD     wMaxVertexBlendMatrices;
  DWORD    dwVertexProcessingCaps;
  DWORD    dwReserved1;
  DWORD    dwReserved2;
  DWORD    dwReserved3;
  DWORD    dwReserved4;
#endif 
} D3DHAL_D3DEXTENDEDCAPS, *LPD3DHAL_D3DEXTENDEDCAPS;
````


## -struct-fields




### -field dwSize

Specifies the size in bytes of this D3DHAL_D3DEXTENDEDCAPS structure.


### -field dwMinTextureWidth

 


### -field dwMaxTextureWidth

 


### -field dwMinTextureHeight

 


### -field dwMaxTextureHeight

 


### -field dwMinStippleWidth

 


### -field dwMaxStippleWidth

 


### -field dwMinStippleHeight

 


### -field dwMaxStippleHeight

 


### -field dwMaxTextureRepeat

Specifies the full range of integer (subfractional) bits of the postnormalized texture indexes. If the D3DDEVCAPS_TEXREPEATNOTSCALEDBYSIZE bit is set, then the number of times a texture can be wrapped is specified by this member. If the D3DDEVCAPS_TEXREPEATNOTSCALEDBYSIZE bit is not set, then the number of time a texture can be wrapped is given by the expression: <b>dwMaxTextureRepeat</b> * (<i>texture size</i>).


### -field dwMaxTextureAspectRatio

Specifies the maximum texture aspect ratio supported by the hardware. This member is typically a power of 2. This maximum aspect ratio is provided as a measure of the texture's height in pixels divided by its width in pixels, or its width divided by height, whichever produces the greater result. For example, a texture that is 8192 pixels wide by 1 pixel high or 1 pixel wide by 8192 high is invalid with a display device that only supports a maximum aspect ratio of 4092. If the hardware is not limited in aspect ratio, <b>dwMaxTextureAspectRatio</b> is the larger of <b>dwMaxTextureWidth</b> and <b>dwMaxTextureHeight</b>.


### -field dwMaxAnisotropy

Specifies the maximum valid value for the D3DRENDERSTATE_ANISOTROPY render state. If the driver's hardware does not support anisotropic filtering, the driver should set this member to 1. Setting this member to 0 represents an invalid value.


### -field dvGuardBandLeft



### -field dvGuardBandTop



### -field dvGuardBandRight



### -field dvGuardBandBottom

Specify the screen-space coordinates, in pixels, of the guard-band clip region. The upper-left corner of this rectangle has coordinates (<b>dvGuardBandLeft</b>, <b>dvGuardBandTop</b>). The lower-left corner has coordinates (<b>dvGuardBandRight</b>, <b>dvGuardBandBottom</b>). Coordinates inside this rectangle but outside the viewport rectangle are automatically clipped. 


### -field dvExtentsAdjust

Specifies the number of pixels required to adjust the extents rectangle outward to accommodate antialiasing kernels.


### -field dwStencilCaps

Specifies the stencil buffer operations supported by the driver or device. For further descriptions of the stencil buffer operations shown in the following table, see D3DSTENCILOP in the DirectX SDK documentation. Stencil operations are assumed to be valid for all three stencil buffer operation render states (D3DRENDERSTATE_STENCILFAIL, D3DRENDERSTATE_STENCILPASS, and D3DRENDERSTATE_STENCILZFAIL). This member can be a bitwise OR of any of the following values:
<table>
<tr>
<th>Value</th>
<th>Stencil Buffer Operation</th>
</tr>
<tr>
<td>
D3DSTENCILCAPS_DECR

</td>
<td>
The D3DSTENCILOP_DECR operation is supported.

</td>
</tr>
<tr>
<td>
D3DSTENCILCAPS_DECRSAT

</td>
<td>
The D3DSTENCILOP_DECRSAT operation is supported.

</td>
</tr>
<tr>
<td>
D3DSTENCILCAPS_INCR

</td>
<td>
The D3DSTENCILOP_INCR operation is supported.

</td>
</tr>
<tr>
<td>
D3DSTENCILCAPS_INCRSAT

</td>
<td>
The D3DSTENCILOP_INCRSAT operation is supported.

</td>
</tr>
<tr>
<td>
D3DSTENCILCAPS_INVERT

</td>
<td>
The D3DSTENCILOP_INVERT operation is supported.

</td>
</tr>
<tr>
<td>
D3DSTENCILCAPS_KEEP

</td>
<td>
The D3DSTENCILOP_KEEP operation is supported.

</td>
</tr>
<tr>
<td>
D3DSTENCILCAPS_REPLACE

</td>
<td>
The D3DSTENCILOP_REPLACE operation is supported.

</td>
</tr>
<tr>
<td>
D3DSTENCILCAPS_ZERO

</td>
<td>
The D3DSTENCILOP_ZERO operation is supported.

</td>
</tr>
</table> 


### -field dwFVFCaps

Specifies the number of texture coordinates that the driver can process. This value can be an integer in the range 0 through 8, where 0 indicates that the driver does not support texturing, 1 indicates that the driver can process only one set of texture coordinates, 2 indicates that the driver can process two sets of texture coordinates, and so on.

A driver must be able to parse all texture coordinates present in the vertex data regardless of the number of texture coordinates that the driver actually uses. The driver should use the index provided with the D3DTSS_TEXCOORDINDEX value of the D3DTEXTURESTAGESTATETYPE enumeration, described in the DirectX SDK documentation, to determine what texture coordinate set to use when rendering.


### -field dwTextureOpCaps

Specifies the texture operations supported by the device. See D3DTEXTUREOP in the DirectX SDK documentation for descriptions of the texture operations listed in the following table. This member can be a bitwise OR of the following values:
<table>
<tr>
<th>Value</th>
<th>Texture Operation Supported</th>
</tr>
<tr>
<td>
D3DTEXOPCAPS_ADD

</td>
<td>
The D3DTOP_ADD texture blending operation is supported by this device.

</td>
</tr>
<tr>
<td>
D3DTEXOPCAPS_ADDSIGNED

</td>
<td>
The D3DTOP_ADDSIGNED texture blending operation is supported by this device.

</td>
</tr>
<tr>
<td>
D3DTEXOPCAPS_ADDSIGNED2X

</td>
<td>
The D3DTOP_ADDSIGNED2X texture blending operation is supported by this device.

</td>
</tr>
<tr>
<td>
D3DTEXOPCAPS_ADDSMOOTH

</td>
<td>
The D3DTOP_ADDSMOOTH texture blending operation is supported by this device.

</td>
</tr>
<tr>
<td>
D3DTEXOPCAPS_BLENDCURRENTALPHA

</td>
<td>
The D3DTOP_BLENDCURRENTALPHA texture blending operation is supported by this device.

</td>
</tr>
<tr>
<td>
D3DTEXOPCAPS_BLENDDIFFUSEALPHA

</td>
<td>
The D3DTOP_BLENDDIFFUSEALPHA texture blending operation is supported by this device.

</td>
</tr>
<tr>
<td>
D3DTEXOPCAPS_BLENDFACTORALPHA

</td>
<td>
The D3DTOP_BLENDFACTORALPHA texture blending operation is supported by this device.

</td>
</tr>
<tr>
<td>
D3DTEXOPCAPS_BLENDTEXTUREALPHA

</td>
<td>
The D3DTOP_BLENDTEXTUREALPHA texture blending operation is supported by this device.

</td>
</tr>
<tr>
<td>
D3DTEXOPCAPS_BLENDTEXTUREALPHAPM

</td>
<td>
The D3DTOP_BLENDTEXTUREALPHAPM texture blending operation is supported by this device.

</td>
</tr>
<tr>
<td>
D3DTEXOPCAPS_BUMPENVMAP.

</td>
<td>
The D3DTOP_BUMPENVMAP texture blending operation is supported by this device.

</td>
</tr>
<tr>
<td>
D3DTEXOPCAPS_BUMPENVMAPLUMINANCE

</td>
<td>
The D3DTOP_BUMPENVMAPLUMINANCE texture blending operation is supported by this device.

</td>
</tr>
<tr>
<td>
D3DTEXOPCAPS_DISABLE

</td>
<td>
The D3DTOP_DISABLE texture blending operation is supported by this device.

</td>
</tr>
<tr>
<td>
D3DTEXOPCAPS_DOTPRODUCT3

</td>
<td>
The D3DTOP_DOTPRODUCT3 texture blending operation is supported by this device.

</td>
</tr>
<tr>
<td>
D3DTEXOPCAPS_MODULATE

</td>
<td>
The D3DTOP_MODULATE texture blending operation is supported by this device.

</td>
</tr>
<tr>
<td>
D3DTEXOPCAPS_MODULATE2X

</td>
<td>
The D3DTOP_MODULATE2X texture blending operation is supported by this device.

</td>
</tr>
<tr>
<td>
D3DTEXOPCAPS_MODULATE4X

</td>
<td>
The D3DTOP_MODULATE4X texture blending operation is supported by this device.

</td>
</tr>
<tr>
<td>
D3DTEXOPCAPS_MODULATEALPHA_ADDCOLOR

</td>
<td>
The D3DTOP_MODULATEALPHA_ADDCOLOR texture blending operation is supported by this device.

</td>
</tr>
<tr>
<td>
D3DTEXOPCAPS_MODULATECOLOR_ADDALPHA

</td>
<td>
The D3DTOP_MODULATEALPHA_ADDCOLOR texture blending operation is supported by this device.

</td>
</tr>
<tr>
<td>
D3DTEXOPCAPS_MODULATEINVALPHA_ADDCOLOR

</td>
<td>
The D3DTOP_MODULATEINVALPHA_ADDCOLOR texture blending operation is supported by this device.

</td>
</tr>
<tr>
<td>
D3DTEXOPCAPS_MODULATEINVCOLOR_ADDALPHA

</td>
<td>
The D3DTOP_MODULATEINVCOLOR_ADDALPHA texture blending operation is supported by this device.

</td>
</tr>
<tr>
<td>
D3DTEXOPCAPS_PREMODULATE

</td>
<td>
The D3DTOP_PREMODULATE texture blending operation is supported by this device.

</td>
</tr>
<tr>
<td>
D3DTEXOPCAPS_SELECTARG1

</td>
<td>
The D3DTOP_SELECTARG1 texture blending operation is supported by this device.

</td>
</tr>
<tr>
<td>
D3DTEXOPCAPS_SELECTARG2

</td>
<td>
The D3DTOP_SELECTARG2 texture blending operation is supported by this device.

</td>
</tr>
<tr>
<td>
D3DTEXOPCAPS_SUBTRACT

</td>
<td>
The D3DTOP_SUBTRACT texture blending operation is supported by this device.

</td>
</tr>
</table> 


### -field wMaxTextureBlendStages

Specifies the maximum number of texture blending stages supported by this device.


### -field wMaxSimultaneousTextures

Specifies the maximum number of textures that can be simultaneously bound to the texture blending stages for this device. That is, <b>wMaxSimultaneousTextures</b> specifies how many of the texture stages can have textures bound to them through the <b>lDirect3DDevice7::SetTexture</b> method. See the Microsoft Windows SDK documentation for more information about this method.


### -field dwMaxActiveLights

Specifies the maximum number of active lights supported by this device. This only needs to be specified in drivers that support hardware transform and lighting (and therefore specify D3DDEVCAPS_HWTRANSFORMANDLIGHT in their device caps).


### -field dvMaxVertexW

Specifies the maximum W range supported by this device. This only needs to be specified in drivers that support W buffering (and therefore specify D3DPRASTERCAPS_WBUFFER in their rasterization caps). The units for W depth values depend on the running application. For example, the application might specify depth in meters.


### -field wMaxUserClipPlanes

Specifies the maximum number of user-defined clip planes supported. 


### -field wMaxVertexBlendMatrices

Specifies the number of world matrices supported for vertex blending.


### -field dwVertexProcessingCaps

Specifies the vertex processing caps that are supported by the driver. This member can be a bitwise OR of the following values:
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3DVTXPCAPS_DIRECTIONALLIGHTS

</td>
<td>
Device can do directional lights.

</td>
</tr>
<tr>
<td>
D3DVTXPCAPS_LOCALVIEWER

</td>
<td>
Device can do local viewer.

</td>
</tr>
<tr>
<td>
D3DVTXPCAPS_MATERIALSOURCE7

</td>
<td>
Device can do DirectX 7.0 color-material-source operations.

</td>
</tr>
<tr>
<td>
D3DVTXPCAPS_NO_TEXGEN_NONLOCALVIEWER

</td>
<td>
Device does not support texture generation in nonlocal viewer mode.

</td>
</tr>
<tr>
<td>
D3DVTXPCAPS_POSITIONALLIGHTS

</td>
<td>
Device can do positional lights (includes point and spot).

</td>
</tr>
<tr>
<td>
D3DVTXPCAPS_TEXGEN

</td>
<td>
Device can do texgen.

</td>
</tr>
<tr>
<td>
D3DVTXPCAPS_TEXGEN_SPHEREMAP

</td>
<td>
Device supports D3DTSS_TCI_SPHEREMAP.

</td>
</tr>
<tr>
<td>
D3DVTXPCAPS_TWEENING

</td>
<td>
Device can do vertex tweening.

</td>
</tr>
</table> 


### -field dwReserved1

Reserved for system use.


### -field dwReserved2

Reserved for system use.


### -field dwReserved3

Reserved for system use.


### -field dwReserved4

Reserved for system use.


#### - dwMinTextureWidth, dwMaxTextureWidth

Specify the minimum and maximum texture widths, in pixels, supported by the driver or device. This member is typically a power of 2. These members are provided as hints to the application, and it is the application's responsibility to adjust texture sizes when necessary.


#### - dwMinTextureHeight, dwMaxTextureHeight

Specify the minimum and maximum texture heights, in pixels, supported by the driver. This member is typically a power of 2.


#### - dwMinStippleWidth, dwMaxStippleWidth

Specify the minimum and maximum stipple widths, in pixels, supported by the driver.


#### - dwMinStippleHeight, dwMaxStippleHeight

Specify the minimum and maximum stipple heights, in pixels, supported by the driver.


## -remarks


The driver allocates and zero-initializes this structure and sets appropriate values in the members it supports. The driver's <a href="https://msdn.microsoft.com/89a22163-a678-4c72-932a-ae4d17922e0b">DdGetDriverInfo</a> function returns a pointer to this structure when that function is called with the GUID_D3DExtendedCaps GUID.

When the driver fills in this structure, it can set values for execute buffer capabilities even when the interface being used to retrieve the capabilities (such as <b>lDirect3DDevice3</b>) does not support execute buffers.



## -see-also

<a href="https://msdn.microsoft.com/89a22163-a678-4c72-932a-ae4d17922e0b">DdGetDriverInfo</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_D3DEXTENDEDCAPS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

