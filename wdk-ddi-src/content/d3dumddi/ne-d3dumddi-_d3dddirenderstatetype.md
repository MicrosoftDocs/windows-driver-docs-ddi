---
UID: NE:d3dumddi._D3DDDIRENDERSTATETYPE
title: _D3DDDIRENDERSTATETYPE
description: The render state type.
ms.assetid: 6af2548f-7751-4b41-b15b-117d67df3db6
ms.date: 10/19/2018
ms.topic: enum
ms.keywords: _D3DDDIRENDERSTATETYPE, D3DDDIRENDERSTATETYPE, 
req.header: d3dumddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: D3DDDIRENDERSTATETYPE
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3dumddi.h
api_name: 
-	_D3DDDIRENDERSTATETYPE
product:
-	Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# _D3DDDIRENDERSTATETYPE enumeration

## -description

The render state type.

## -enum-fields

### -field D3DDDIRS_ZENABLE 

A [D3DZBUFFERTYPE](../d3d9types/ne-d3d9types-_d3dzbuffertype.md) depth-buffering state that can either be used to enable z-buffering, enable w-buffering, disable depth buffering. 

### -field D3DDDIRS_FILLMODE 

A [D3DFILLMODE](../d3d9types/ne-d3d9types-_d3dfillmode.md) enumeration that specifies the fill mode for primitives.

### -field D3DDDIRS_SHADEMODE 

A [D3DSHADEMODE](../d3d9types/ne-d3d9types-_d3dshademode.md) that specifies shading operations that the device can perform.

### -field D3DDDIRS_LINEPATTERN 

A line pattern.

### -field D3DDDIRS_ZWRITEENABLE 

TRUE to enable the application to write to the depth buffer. The default value is TRUE. This member enables an application to prevent the system from updating the depth buffer with new depth values. 

### -field D3DDDIRS_ALPHATESTENABLE 

TRUE to enable alpha tests.

### -field D3DDDIRS_LASTPIXEL 

FALSE to enable drawing the last pixel in a line or triangle. The default value is TRUE.

### -field D3DDDIRS_SRCBLEND 

A [D3DBLEND](../d3d9types/ne-d3d9types-_d3dblend.md) enumeration type. The default value is D3DBLEND_ONE.

### -field D3DDDIRS_DESTBLEND 

A [D3DBLEND](../d3d9types/ne-d3d9types-_d3dblend.md) enumeration type. The default value is D3DBLEND_ZERO.

### -field D3DDDIRS_CULLMODE 

A [D3DCULL](../d3d9types/ne-d3d9types-_d3dcull.md) enumerated type that specifies how back-facing triangles are culled, if at all. The default value is D3DCULL_CCW. 

### -field D3DDDIRS_ZFUNC 

A [D3DCMPFUNC](../d3d9types/ne-d3d9types-_d3dcmpfunc.md) enumerated type that enables an application to accept or reject a pixel, based on its distance from the camera. The default value is D3DCMP_LESSEQUAL.

The depth value of the pixel is compared with the depth-buffer value. If the depth value of the pixel passes the comparison function, the pixel is written. 
The depth value is written to the depth buffer only if the render state is TRUE. 

Software rasterizers and many hardware accelerators work faster if the depth test fails, because there is no need to filter and modulate the texture if the pixel is not going to be rendered. 

### -field D3DDDIRS_ALPHAREF 

A value that specifies a reference alpha value against which pixels are tested when alpha-testing is enabled. This is an 8-bit value placed in the low 8 bits of the DWORD render-state value. Values can range from 0x00000000 through 0x000000FF.

### -field D3DDDIRS_ALPHAFUNC 

A [D3DCMPFUNC](../d3d9types/ne-d3d9types-_d3dcmpfunc.md) enumerated type that enables an application to accept or reject a pixel, based on its alpha value. The default value is D3DCMP_ALWAYS.

### -field D3DDDIRS_DITHERENABLE 

TRUE to enable dithering. The default value is FALSE.

### -field D3DDDIRS_ALPHABLENDENABLE 

TRUE to enable alpha blending.

### -field D3DDDIRS_FOGENABLE 

TRUE to enable fog blending.

### -field D3DDDIRS_SPECULARENABLE 

TRUE to enable specular.

### -field D3DDDIRS_ZVISIBLE 

Not supported.

### -field D3DDDIRS_FOGCOLOR 

A [D3DCOLORVALUE](../d3d9types/ns-d3d9types-_d3dcolorvalue.md) value that indicates the diffuse color that is emitted by the light. The default value is 0. 

### -field D3DDDIRS_FOGTABLEMODE 

A [D3DFOGMODE](../d3d9types/ne-d3d9types-_d3dfogmode.md) that contains the fog formula to be used for pixel fog.

### -field D3DDDIRS_FOGSTART 

Depth at which pixel or vertex fog effects begin for linear fog mode. Depth is specified in world space for vertex fog, and either device space [0.0, 1.0] or world space for pixel fog. For pixel fog, these values are in device space when the system uses z for fog calculations, and world-space when the system is using eye-relative fog (w-fog).

### -field D3DDDIRS_FOGEND 

Depth at which pixel or vertex fog effects end for linear fog mode. Depth is specified in world space for vertex fog, and either device space [0.0, 1.0] or world space for pixel fog. For pixel fog, these values are in device space when the system uses z for fog calculations, and world-space when the system is using eye-relative fog (w-fog). 

### -field D3DDDIRS_FOGDENSITY 

The fog density.

### -field D3DDDIRS_EDGEANTIALIAS 

Not supported.

### -field D3DDDIRS_COLORKEYENABLE 

TRUE to enable source colorkeyed textures.

### -field D3DDDIRS_OLDALPHABLENDENABLE 

For internal use. TRUE to enable source colorkeyed textures.

### -field D3DDDIRS_ZBIAS 

Integer value in the range 0 through 16 that causes polygons that are physically coplanar to appear separate. Polygons with a high z-bias value appear in front of polygons with a low value, without requiring sorting for drawing order. Polygons with a value of 1 appear in front of polygons with a value of 0, and so on. The default value is 0. 

### -field D3DDDIRS_RANGEFOGENABLE 

TRUE to enable range-based vertex fog. The default value is FALSE, in which case the system uses depth-based fog. In range-based fog, the distance of an object from the viewer is used to compute fog effects, not the depth of the object (that is, the z-coordinate) in the scene. In range-based fog, all fog methods work as usual, except that they use range instead of depth in the computations. 

Range is the correct factor to use for fog computations, but depth is commonly used instead because range is expensive to compute and depth is generally already available. Using depth to calculate fog has the undesirable effect of having the fogginess of peripheral objects change as the viewer's eye moves — in this case, the depth changes, and the range remains constant. 
Because no hardware currently supports per-pixel range-based fog, range correction is offered only for vertex fog. 

### -field D3DDDIRS_TRANSLUCENTSORTINDEPENDENT 

A BOOL to enable sort-independent transparency.

### -field D3DDDIRS_STENCILENABLE 

TRUE to enable stenciling, or FALSE to disable stenciling. The default value is FALSE.

### -field D3DDDIRS_STENCILFAIL 

A [D3DSTENCILOP](../d3d9types/ne-d3d9types-_d3dstencilop.md) stencil operation to perform if the stencil test fails. The default value is D3DSTENCILOP_KEEP. 

### -field D3DDDIRS_STENCILZFAIL 

A [D3DSTENCILOP](../d3d9types/ne-d3d9types-_d3dstencilop.md) stencil operation to perform if the stencil test passes and the depth test (z-test) fails. The default value is D3DSTENCILOP_KEEP.

### -field D3DDDIRS_STENCILPASS 

A [D3DSTENCILOP](../d3d9types/ne-d3d9types-_d3dstencilop.md) stencil operation to perform if both the stencil and the depth (z) tests pass. The default value is D3DSTENCILOP_KEEP.

### -field D3DDDIRS_STENCILFUNC 

A [D3DSTENCILOP](../d3d9types/ne-d3d9types-_d3dstencilop.md) comparison function for the stencil test. The default value is D3DCMP_ALWAYS. 

The comparison function is used to compare the reference value to a stencil buffer entry. This comparison applies only to the bits in the reference value and stencil buffer entry that are set in the stencil mask (set by the D3DRS_STENCILMASK render state). If TRUE, the stencil test passes. 

### -field D3DDDIRS_STENCILREF 

Integer reference value for the stencil test. The default value is 0.

### -field D3DDDIRS_STENCILMASK 

Mask applied to the reference value and each stencil buffer entry to determine the significant bits for the stencil test. The default mask is 0xFFFFFFFF.

### -field D3DDDIRS_STENCILWRITEMASK 

Write mask applied to values written into the stencil buffer. The default mask is 0xFFFFFFFF.

### -field D3DDDIRS_TEXTUREFACTOR 

A [D3DCOLORVALUE](../d3d9types/ns-d3d9types-_d3dcolorvalue.md) color used for multiple-texture blending.

### -field D3DDDIRS_SCENECAPTURE 

Specifies either begin scene information or end scene information for geometric data captured within a frame.

### -field D3DDDIRS_STIPPLEPATTERN00 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN01 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN02 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN03 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN04 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN05 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN06 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN07 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN08 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN09 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN10 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN11 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN12 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN13 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN14 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN15 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN16 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN17 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN18 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN19 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN20 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN21 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN22 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN23 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN24 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN25 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN26 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN27 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN28 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN29 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN30 

A stipple pattern render state.

### -field D3DDDIRS_STIPPLEPATTERN31 

A stipple pattern render state.

### -field D3DDDIRS_WRAP0 

Texture-wrapping behavior for multiple sets of texture coordinates. Valid values for these render states can be any combination of the D3DWRAPCOORD_0 (or D3DWRAP_U), D3DWRAPCOORD_1 (or D3DWRAP_V), D3DWRAPCOORD_2 (or D3DWRAP_W), and D3DWRAPCOORD_3 flags. These cause the system to wrap in the direction of the first, second, third, and fourth dimensions, sometimes referred to at the s, t, r, and q directions, for a given texture. The default value for these render states is 0 (wrapping disabled in all directions). 

### -field D3DDDIRS_WRAP1 

See **D3DDDIRS_WRAP0**.

### -field D3DDDIRS_WRAP2 

See **D3DDDIRS_WRAP0**.

### -field D3DDDIRS_WRAP3 

See **D3DDDIRS_WRAP0**.

### -field D3DDDIRS_WRAP4 

See **D3DDDIRS_WRAP0**.

### -field D3DDDIRS_WRAP5 

See **D3DDDIRS_WRAP0**.

### -field D3DDDIRS_WRAP6 

See **D3DDDIRS_WRAP0**.

### -field D3DDDIRS_WRAP7 

See **D3DDDIRS_WRAP0**.

### -field D3DDDIRS_CLIPPING 

TRUE to enable primitive clipping by Microsoft® Direct3D®, or FALSE to disable it. The default value is TRUE.

### -field D3DDDIRS_LIGHTING 

TRUE to enable Direct3D lighting, or FALSE to disable it. The default value is TRUE. Only vertices that include a vertex normal are properly lit; vertices that do not contain a normal employ a dot product of 0 in all lighting calculations.

### -field D3DDDIRS_AMBIENT 

A A [D3DCOLORVALUE](../d3d9types/ns-d3d9types-_d3dcolorvalue.md) that specifies the ambient light color. The default value is 0. 

### -field D3DDDIRS_FOGVERTEXMODE 

A [D3DFOGMODE](../d3d9types/ne-d3d9types-_d3dfogmode.md) fog formula to be used for vertex fog. The default value is D3DFOG_NONE. 

### -field D3DDDIRS_COLORVERTEX 

TRUE to enable per-vertex color, or FALSE to disable it. The default value is TRUE. Enabling per-vertex color allows the system to include the color defined for individual vertices in its lighting calculations. 

### -field D3DDDIRS_LOCALVIEWER 

TRUE to enable camera-relative specular highlights, or FALSE to use orthogonal specular highlights. The default value is TRUE. Applications that use orthogonal projection should specify false.

### -field D3DDDIRS_NORMALIZENORMALS 

TRUE to enable automatic normalization of vertex normals, or FALSE to disable it. The default value is FALSE. Enabling this feature causes the system to normalize the vertex normals for vertices after transforming them to camera space, which can be computationally expensive.

### -field D3DDDIRS_COLORKEYBLENDENABLE 

Indicates whether the color key is blend enaable.

### -field D3DDDIRS_DIFFUSEMATERIALSOURCE 

A [D3DMATERIALCOLORSOURCE](../d3d9types/ne-d3d9types-_d3dmaterialcolorsource.md) that specifies the diffuse color source for lighting calculations. The default value is D3DMCS_COLOR1. The value for this render state is used only if the D3DRS_COLORVERTEX render state is set to TRUE. 

### -field D3DDDIRS_SPECULARMATERIALSOURCE 

A D3DMATERIALCOLORSOURCE that specifies the specular color source for lighting calculations. The default value is D3DMCS_COLOR2. 

### -field D3DDDIRS_AMBIENTMATERIALSOURCE 

A D3DMATERIALCOLORSOURCE that specifies the ambient color source for lighting calculations. The default value is D3DMCS_COLOR2. 

### -field D3DDDIRS_EMISSIVEMATERIALSOURCE 

A D3DMATERIALCOLORSOURCE that specifies the emissive color source for lighting calculations. The default value is D3DMCS_MATERIAL. 

### -field D3DDDIRS_VERTEXBLEND 

Not supported.

### -field D3DDDIRS_CLIPPLANEENABLE 

Enables or disables user-defined clipping planes. Valid values are any DWORD in which the status of each bit (set or not set) toggles the activation state of a corresponding user-defined clipping plane. The least significant bit (bit 0) controls the first clipping plane at index 0, and subsequent bits control the activation of clipping planes at higher indexes. If a bit is set, the system applies the appropriate clipping plane during scene rendering. The default value is 0. 

### -field D3DDDIRS_SOFTWAREVERTEXPROCESSING 

A BOOL value that enables applications to query and select hardware or software vertex processing. 

### -field D3DDDIRS_POINTSIZE 

Float value that specifies the size to use for point size computation in cases where point size is not specified for each vertex. This value is not used when the vertex contains point size. 

### -field D3DDDIRS_POINTSIZE_MIN 

Float value that specifies the minimum size of point primitives. Point primitives are clamped to this size during rendering. Setting this to values smaller than 1.0 results in points dropping out when the point does not cover a pixel center. The default value is 1.0f. The range for this value is greater than or equal to 0.0f. 

### -field D3DDDIRS_POINTSPRITEENABLE 

Not supported.

### -field D3DDDIRS_POINTSCALEENABLE 

A BOOL value that controls computation of size for point primitives. When TRUE, the point size is interpreted as a camera space value and is scaled by the distance function and the frustum to viewport Y axis scaling to compute the final screen space point size. When FALSE, the point size is interpreted as screen space and used directly. The default value is FALSE.

### -field D3DDDIRS_POINTSCALE_A 

A float value that controls for distance-based size attenuation for point primitives. Active only when D3DRS_POINTSCALEENABLE is TRUE. The default value is 1.0f. The range for this value is greater than or equal to 0.0f. 

### -field D3DDDIRS_POINTSCALE_B 

Float value that controls for distance-based size attenuation for point primitives. Active only when D3DRS_POINTSCALEENABLE is TRUE. The default value is 0.0f. The range for this value is greater than or equal to 0.0f. 

### -field D3DDDIRS_POINTSCALE_C 

Float value that controls for distance-based size attenuation for point primitives. Active only when D3DRS_POINTSCALEENABLE is TRUE. The default value is 0.0f. The range for this value is greater than or equal to 0.0f. 

### -field D3DDDIRS_MULTISAMPLEANTIALIAS 

A BOOL value that determines how individual samples are computed when using a multisample render target buffer. When set to TRUE, the multiple samples are computed so that full-scene antialiasing is performed by sampling at different sample positions for each multiple sample. When set to FALSE, the multiple samples are all written with the same sample value — sampled at the pixel center, which allows non-antialiased rendering to a multisample buffer. This render state has no effect when rendering to a single sample buffer. The default value is TRUE.

### -field D3DDDIRS_MULTISAMPLEMASK 

Each bit in this mask, starting at the LSB, controls modification of one of the samples in a multisample render target. Thus, for an 8-sample render target, the low byte contains the 8 write enables for each of the 8 samples. This render state has no effect when rendering to a single sample buffer. The default value is 0xFFFFFFFF. 

This render state enables use of a multisample buffer as an accumulation buffer, doing multipass rendering of geometry where each pass updates a subset of samples. 

### -field D3DDDIRS_PATCHEDGESTYLE 

A BOOL used to indicate whether patch edges will use float style tessellation.

### -field D3DDDIRS_PATCHSEGMENTS 

Not supported.

### -field D3DDDIRS_DEBUGMONITORTOKEN 

A token used for debugging only. 

### -field D3DDDIRS_POINTSIZE_MAX 

The float point size max threshold.

### -field D3DDDIRS_INDEXEDVERTEXBLENDENABLE 

A BOOL value that is always set to FALSE.

### -field D3DDDIRS_COLORWRITEENABLE 

A UINT value that enables a per-channel write for the render target color buffer. A set bit results in the color channel being updated during 3-D rendering. A clear bit results in the color channel being unaffected. This functionality is available if the D3DPMISCCAPS_COLORWRITEENABLE capabilities bit is set in the PrimitiveMiscCaps member of the D3DCAPS8 structure for the device. This render state does not affect the clear operation. The default value is 0x0000000F. 

Valid values for this render state can be any combination of the D3DCOLORWRITEENABLE_ALPHA, D3DCOLORWRITEENABLE_BLUE, D3DCOLORWRITEENABLE_GREEN, or D3DCOLORWRITEENABLE_RED flags. 

### -field D3DDDIRS_DELETERTPATCH 

Delete RT patch.

### -field D3DDDIRS_TWEENFACTOR 

A float that represents the tween factor.

### -field D3DDDIRS_BLENDOP 

A [D3DBLENDOP](../d3d9types/ne-d3d9types-_d3dblendop.md) setting value that is used to select the arithmetic operation applied when the alpha blending render state, D3DRS_ALPHABLENDENABLE, is set to TRUE. The default value is D3DBLENDOP_ADD. 

If the D3DPMISCCAPS_BLENDOP device capability is not supported, then D3DBLENDOP_ADD is performed. 

### -field D3DDDIRS_POSITIONDEGREE 

An NPatch (a high-order patched surface) position interpolation degree. Values can be D3DDEGREE_LINEAR or D3DDEGREE_CUBIC (default).

### -field D3DDDIRS_NORMALDEGREE 

An NPatch normal interpolation degree. Values can be D3DDEGREE_LINEAR (default) or D3DDEGREE_QUADRATIC.

### -field D3DDDIRS_SCISSORTESTENABLE 
### -field D3DDDIRS_SLOPESCALEDEPTHBIAS 
### -field D3DDDIRS_ANTIALIASEDLINEENABLE 
### -field D3DDDIRS_MINTESSELLATIONLEVEL 
### -field D3DDDIRS_MAXTESSELLATIONLEVEL 
### -field D3DDDIRS_ADAPTIVETESS_X 
### -field D3DDDIRS_ADAPTIVETESS_Y 
### -field D3DDDIRS_ADAPTIVETESS_Z 
### -field D3DDDIRS_ADAPTIVETESS_W 
### -field D3DDDIRS_ENABLEADAPTIVETESSELLATION 
### -field D3DDDIRS_TWOSIDEDSTENCILMODE 
### -field D3DDDIRS_CCW_STENCILFAIL 
### -field D3DDDIRS_CCW_STENCILZFAIL 
### -field D3DDDIRS_CCW_STENCILPASS 
### -field D3DDDIRS_CCW_STENCILFUNC 
### -field D3DDDIRS_COLORWRITEENABLE1 
### -field D3DDDIRS_COLORWRITEENABLE2 
### -field D3DDDIRS_COLORWRITEENABLE3 
### -field D3DDDIRS_BLENDFACTOR 
### -field D3DDDIRS_SRGBWRITEENABLE 
### -field D3DDDIRS_DEPTHBIAS 
### -field D3DDDIRS_WRAP8 
### -field D3DDDIRS_WRAP9 
### -field D3DDDIRS_WRAP10 
### -field D3DDDIRS_WRAP11 
### -field D3DDDIRS_WRAP12 
### -field D3DDDIRS_WRAP13 
### -field D3DDDIRS_WRAP14 
### -field D3DDDIRS_WRAP15 
### -field D3DDDIRS_SEPARATEALPHABLENDENABLE 
### -field D3DDDIRS_SRCBLENDALPHA 
### -field D3DDDIRS_DESTBLENDALPHA 
### -field D3DDDIRS_BLENDOPALPHA 
### -field D3DDDIRS_FORCE_DWORD 

## -remarks

## -see-also
