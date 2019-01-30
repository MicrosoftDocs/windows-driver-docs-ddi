---
UID: NE:d3d9types._D3DRENDERSTATETYPE
title: "_D3DRENDERSTATETYPE" (d3d9types.h)
description: The D3DRENDERSTATETYPE enumerated type lists a variety of attributes, or render states.
old-location: display\d3drenderstatetype.htm
tech.root: display
ms.assetid: 82978b22-1538-4da0-bcf2-c4c52d2e3429
ms.date: 05/10/2018
ms.keywords: D3DRENDERSTATETYPE, D3DRENDERSTATE_EVICTMANAGEDTEXTURES, D3DRENDERSTATE_SCENECAPTURE, D3DRS_DELETERTPATCH, D3DRS_MAXPIXELSHADERINST, D3DRS_MAXVERTEXSHADERINST, _D3DRENDERSTATETYPE, d3d9types/, d3d9types/D3DRENDERSTATE_EVICTMANAGEDTEXTURES, d3d9types/D3DRENDERSTATE_SCENECAPTURE, d3d9types/D3DRS_DELETERTPATCH, d3d9types/D3DRS_MAXPIXELSHADERINST, d3d9types/D3DRS_MAXVERTEXSHADERINST, d3denum_6b8d96f8-ff88-43c3-9850-a213d84d548f.xml, display.d3drenderstatetype, enumeration [Display Devices]
ms.topic: enum
req.header: d3d9types.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d9types.h
api_name:
-	D3DRENDERSTATETYPE
product:
- Windows
targetos: Windows
req.typenames: D3DRENDERSTATETYPE
---

# _D3DRENDERSTATETYPE enumeration


## -description


The D3DRENDERSTATETYPE enumerated type lists a variety of attributes, or render states. 
  The enumerators of D3DRENDERSTATETYPE that are used exclusively by drivers can specify either rendering information or a texture attribute. The following render states are used by display drivers:
  


## -enum-fields




### -field D3DRS_ZENABLE

A [D3DZBUFFERTYPE](ne-d3d9types-_d3dzbuffertype.md) enumeration type that represents the depth-buffering state. 

### -field D3DRS_FILLMODE

A [D3DFILLMODE](ne-d3d9types-_d3dfillmode.md) enumeration type.

### -field D3DRS_SHADEMODE

A [D3DSHADEMODE](ne-d3d9types-_d3dshademode.md) enumeration type. 

### -field D3DRS_ZWRITEENABLE

TRUE to enable the application to write to the depth buffer. The default value is TRUE. This member enables an application to prevent the system from updating the depth buffer with new depth values. If FALSE, depth comparisons are still made according to the render state D3DRS_ZFUNC, assuming that depth buffering is taking place, but depth values are not written to the buffer.

### -field D3DRS_ALPHATESTENABLE

TRUE to enable per pixel alpha testing. If the test passes, the pixel is processed by the frame buffer. Otherwise, all frame-buffer processing is skipped for the pixel.

### -field D3DRS_LASTPIXEL

The default value is TRUE, which enables drawing of the last pixel in a line. To prevent drawing of the last pixel, set this value to FALSE. 

### -field D3DRS_SRCBLEND

A [D3DBLEND](ne-d3d9types-_d3dblend.md) enumeration type.

### -field D3DRS_DESTBLEND

A D3DBLEND enumeration type.

### -field D3DRS_CULLMODE

A [D3DCULL](ne-d3d9types-_d3dcull.md) enumeration type that specifies how back-facing triangles are culled, if at all.

### -field D3DRS_ZFUNC

A [D3DCMPFUNC](ne-d3d9types-_d3dcmpfunc.md) enumeration type that enables an application to accept or reject a pixel, based on its distance from the camera.

The depth value of the pixel is compared with the depth-buffer value. If the depth value of the pixel passes the comparison function, the pixel is written.

The depth value is written to the depth buffer only if the render state is TRUE.

### -field D3DRS_ALPHAREF

Value that specifies a reference alpha value against which pixels are tested when alpha testing is enabled. This is an 8-bit value placed in the low 8 bits of the DWORD render-state value. Values can range from 0x00000000 through 0x000000FF. The default value is 0.

### -field D3DRS_ALPHAFUNC

A D3DCMPFUNC enumeration type that enables an application to accept or reject a pixel, based on its alpha value.

### -field D3DRS_DITHERENABLE

TRUE to enable dithering. The default value is FALSE.

### -field D3DRS_ALPHABLENDENABLE

TRUE to enable alpha-blended transparency. The default value is FALSE.

The type of alpha blending is determined by the D3DRS_SRCBLEND and D3DRS_DESTBLEND render states.

### -field D3DRS_FOGENABLE

TRUE to enable fog blending. The default value is FALSE. 

### -field D3DRS_SPECULARENABLE

TRUE to enable specular highlights. The default value is FALSE.
Specular highlights are calculated as though every vertex in the object being lit is at the object's origin. This gives the expected results as long as the object is modeled around the origin and the distance from the light to the object is relatively large. In other cases, the results as undefined.

When this member is set to TRUE, the specular color is added to the base color after the texture cascade but before alpha blending.

### -field D3DRS_FOGCOLOR

A [D3DCOLORVALUE](ns-d3d9types-_d3dcolorvalue.md) structure.

### -field D3DRS_FOGTABLEMODE

A [D3DFOGMODE](ne-d3d9types-_d3dfogmode.md) enumerated type that represents a fog formula to be used for pixel fog. 

### -field D3DRS_FOGSTART

Depth at which pixel or vertex fog effects begin for linear fog mode. The default value is 0.0f. Depth is specified in world space for vertex fog and either device space [0.0, 1.0] or world space for pixel fog. For pixel fog, these values are in device space when the system uses z for fog calculations and world-world space when the system is using eye-relative fog (w-fog). 

### -field D3DRS_FOGEND

Depth at which pixel or vertex fog effects end for linear fog mode. The default value is 1.0f. Depth is specified in world space for vertex fog and either device space [0.0, 1.0] or world space for pixel fog. For pixel fog, these values are in device space when the system uses z for fog calculations and in world space when the system is using eye-relative fog (w-fog).

### -field D3DRS_FOGDENSITY

Fog density for pixel or vertex fog used in the exponential fog modes (D3DFOG_EXP and D3DFOG_EXP2). Valid density values range from 0.0 through 1.0. 

### -field D3DRS_RANGEFOGENABLE

TRUE to enable range-based vertex fog. The default value is FALSE, in which case the system uses depth-based fog. In range-based fog, the distance of an object from the viewer is used to compute fog effects, not the depth of the object (that is, the z-coordinate) in the scene. In range-based fog, all fog methods work as usual, except that they use range instead of depth in the computations.

Range is the correct factor to use for fog computations, but depth is commonly used instead because range is time-consuming to compute and depth is generally already available. Using depth to calculate fog has the undesirable effect of having the fogginess of peripheral objects change as the viewer's eye moves - in this case, the depth changes and the range remains constant.

Because no hardware currently supports per-pixel range-based fog, range correction is offered only for vertex fog.

### -field D3DRS_STENCILENABLE

TRUE to enable stenciling, or FALSE to disable stenciling. The default value is FALSE. 

### -field D3DRS_STENCILFAIL

A [D3DSTENCILOP](ne-d3d9types-_d3dstencilop.md) enumeration type that specifies the stencil operation to perform if the stencil test fails. The default value is D3DSTENCILOP_KEEP.

### -field D3DRS_STENCILZFAIL

A D3DSTENCILOP enumeration type that specifies the stencil operation to perform if the stencil test passes and the depth test (z-test) fails. 

### -field D3DRS_STENCILPASS

A D3DSTENCILOP enumeration type that specifies the stencil operation to perform if both the stencil and the depth (z) tests pass.

### -field D3DRS_STENCILFUNC

The comparison function is used to compare the reference value to a stencil buffer entry. This comparison applies only to the bits in the reference value and stencil buffer entry that are set in the stencil mask (set by the D3DRS_STENCILMASK render state). If TRUE, the stencil test passes.

### -field D3DRS_STENCILREF

An int reference value for the stencil test. The default value is 0.

### -field D3DRS_STENCILMASK

Mask applied to the reference value and each stencil buffer entry to determine the significant bits for the stencil test. The default mask is 0xFFFFFFFF.

### -field D3DRS_STENCILWRITEMASK

Write mask applied to values written into the stencil buffer. The default mask is 0xFFFFFFFF.

### -field D3DRS_TEXTUREFACTOR

Color used for multiple-texture blending with the D3DTA_TFACTOR texture-blending argument or the D3DTOP_BLENDFACTORALPHA texture-blending operation. 

### -field D3DRS_WRAP0

Texture-wrapping behavior for multiple sets of texture coordinates. Valid values for this render state can be any combination of the D3DWRAPCOORD_0 (or D3DWRAP_U), D3DWRAPCOORD_1 (or D3DWRAP_V), D3DWRAPCOORD_2 (or D3DWRAP_W), and D3DWRAPCOORD_3 flags. These cause the system to wrap in the direction of the first, second, third, and fourth dimensions, sometimes referred to as the s, t, r, and q directions, for a given texture. The default value for this render state is 0 (wrapping disabled in all directions).

### -field D3DRS_WRAP1

See D3DRS_WRAP0.

### -field D3DRS_WRAP2

See D3DRS_WRAP0.

### -field D3DRS_WRAP3

See D3DRS_WRAP0.

### -field D3DRS_WRAP4

See D3DRS_WRAP0.

### -field D3DRS_WRAP5

See D3DRS_WRAP0.

### -field D3DRS_WRAP6

See D3DRS_WRAP0.

### -field D3DRS_WRAP7

See D3DRS_WRAP0.

### -field D3DRS_CLIPPING

TRUE to enable primitive clipping by Direct3D, or FALSE to disable it. The default value is TRUE.

### -field D3DRS_LIGHTING

TRUE to enable Direct3D lighting, or FALSE to disable it. The default value is TRUE. Only vertices that include a vertex normal are properly lit; vertices that do not contain a normal employ a dot product of 0 in all lighting calculations.

### -field D3DRS_AMBIENT

Ambient light color.

### -field D3DRS_FOGVERTEXMODE

Fog formula to be used for vertex fog.

### -field D3DRS_COLORVERTEX

TRUE to enable per-vertex color or FALSE to disable it. The default value is TRUE. Enabling per-vertex color allows the system to include the color defined for individual vertices in its lighting calculations.

### -field D3DRS_LOCALVIEWER

TRUE to enable camera-relative specular highlights, or FALSE to use orthogonal specular highlights. The default value is TRUE. Applications that use orthogonal projection should specify FALSE.

### -field D3DRS_NORMALIZENORMALS

TRUE to enable automatic normalization of vertex normals, or FALSE to disable it. The default value is FALSE. Enabling this feature causes the system to normalize the vertex normals for vertices after transforming them to camera space, which can be computationally time-consuming.

### -field D3DRS_DIFFUSEMATERIALSOURCE

Diffuse color source for lighting calculations. 

### -field D3DRS_SPECULARMATERIALSOURCE

Specular color source for lighting calculations. 

### -field D3DRS_AMBIENTMATERIALSOURCE

Ambient color source for lighting calculations. 

### -field D3DRS_EMISSIVEMATERIALSOURCE

Emissive color source for lighting calculations. 

### -field D3DRS_VERTEXBLEND

Number of matrices to use to perform geometry blending, if any. 

### -field D3DRS_CLIPPLANEENABLE

Enables or disables user-defined clipping planes. Valid values are any DWORD in which the status of each bit (set or not set) toggles the activation state of a corresponding user-defined clipping plane. The least significant bit (bit 0) controls the first clipping plane at index 0, and subsequent bits control the activation of clipping planes at higher indexes. If a bit is set, the system applies the appropriate clipping plane during scene rendering. The default value is 0.

### -field D3DRS_POINTSIZE

A float value that specifies the size to use for point size computation in cases where point size is not specified for each vertex. This value is not used when the vertex contains point size. This value is in screen space units if D3DRS_POINTSCALEENABLE is FALSE; otherwise this value is in world space units. The default value is the value a driver returns. If a driver returns 0 or 1, the default value is 64, which allows software point size emulation. 

### -field D3DRS_POINTSIZE_MIN

A float value that specifies the minimum size of point primitives. Point primitives are clamped to this size during rendering. Setting this to values smaller than 1.0 results in points dropping out when the point does not cover a pixel center and antialiasing is disabled or being rendered with reduced intensity when antialiasing is enabled. The default value is 1.0f. The range for this value is greater than or equal to 0.0f.

### -field D3DRS_POINTSPRITEENABLE

When TRUE, texture coordinates of point primitives are set so that full textures are mapped on each point. When FALSE, the vertex texture coordinates are used for the entire point. The default value is FALSE. You can achieve DirectX 7 style single-pixel points by setting D3DRS_POINTSCALEENABLE to FALSE and D3DRS_POINTSIZE to 1.0, which are the default values.

### -field D3DRS_POINTSCALEENABLE

A bool value that controls computation of size for point primitives. When TRUE, the point size is interpreted as a camera space value and is scaled by the distance function and the frustum to viewport y-axis scaling to compute the final screen-space point size. When FALSE, the point size is interpreted as screen space and used directly. The default value is FALSE.

### -field D3DRS_POINTSCALE_A

A float value that controls for distance-based size attenuation for point primitives. Active only when D3DRS_POINTSCALEENABLE is TRUE. The default value is 1.0f. The range for this value is greater than or equal to 0.0f. 

### -field D3DRS_POINTSCALE_B

A float value that controls for distance-based size attenuation for point primitives. Active only when D3DRS_POINTSCALEENABLE is TRUE. The default value is 0.0f. The range for this value is greater than or equal to 0.0f. 

### -field D3DRS_POINTSCALE_C

A float value that controls for distance-based size attenuation for point primitives. Active only when D3DRS_POINTSCALEENABLE is TRUE. The default value is 0.0f. The range for this value is greater than or equal to 0.0f.

### -field D3DRS_MULTISAMPLEANTIALIAS

A bool value that determines how individual samples are computed when using a multisample render-target buffer. When set to TRUE, the multiple samples are computed so that full-scene antialiasing is performed by sampling at different sample positions for each multiple sample. When set to FALSE, the multiple samples are all written with the same sample value, sampled at the pixel center, which allows non-antialiased rendering to a multisample buffer. This render state has no effect when rendering to a single sample buffer. The default value is TRUE.

### -field D3DRS_MULTISAMPLEMASK

Each bit in this mask, starting at the least significant bit (LSB), controls modification of one of the samples in a multisample render target. Thus, for an 8-sample render target, the low byte contains the eight write enables for each of the eight samples. This render state has no effect when rendering to a single sample buffer. The default value is 0xFFFFFFFF.

This render state enables use of a multisample buffer as an accumulation buffer, doing multipass rendering of geometry where each pass updates a subset of samples.
If there are n multisamples and k enabled samples, the resulting intensity of the rendered image should be k/n. Each component RGB of every pixel is factored by k/n.

### -field D3DRS_PATCHEDGESTYLE

Sets whether patch edges will use float style tessellation.

### -field D3DRS_DEBUGMONITORTOKEN

Set only for debugging the monitor. 

### -field D3DRS_POINTSIZE_MAX

A float value that specifies the maximum size to which point sprites will be clamped. The value must be less than or equal to the MaxPointSize member of D3DCAPS9 and greater than or equal to D3DRS_POINTSIZE_MIN. The default value is 64.0. 

### -field D3DRS_INDEXEDVERTEXBLENDENABLE

A bool value that enables or disables indexed vertex blending. The default value is FALSE. When set to TRUE, indexed vertex blending is enabled. When set to FALSE, indexed vertex blending is disabled. If this render state is enabled, the user must pass matrix indices as a packed DWORDwith every vertex. When the render state is disabled and vertex blending is enabled through the D3DRS_VERTEXBLEND state, it is equivalent to having matrix indices 0, 1, 2, 3 in every vertex.

### -field D3DRS_COLORWRITEENABLE

UINT value that enables a per-channel write for the render-target color buffer. A set bit results in the color channel being updated during 3D rendering. A clear bit results in the color channel being unaffected. 

### -field D3DRS_TWEENFACTOR

A float value that controls the tween factor. 

### -field D3DRS_BLENDOP

Value used to select the arithmetic operation applied when the alpha blending render state, D3DRS_ALPHABLENDENABLE, is set to TRUE. 

If the D3DPMISCCAPS_BLENDOP device capability is not supported, then D3DBLENDOP_ADD is performed.

### -field D3DRS_POSITIONDEGREE

N-patch position interpolation degree. The values can be D3DDEGREE_CUBIC (default) or D3DDEGREE_LINEAR. 

### -field D3DRS_NORMALDEGREE

N-patch normal interpolation degree. The values can be D3DDEGREE_LINEAR (default) or D3DDEGREE_QUADRATIC. 

### -field D3DRS_SCISSORTESTENABLE

TRUE to enable scissor testing and FALSE to disable it. The default value is FALSE.

### -field D3DRS_SLOPESCALEDEPTHBIAS

Used to determine how much bias can be applied to co-planar primitives to reduce z-fighting. The default value is 0.

### -field D3DRS_ANTIALIASEDLINEENABLE

TRUE to enable line antialiasing, FALSE to disable line antialiasing. The default value is FALSE.

### -field D3DRS_MINTESSELLATIONLEVEL

Minimum tessellation level. The default value is 1.0f.

### -field D3DRS_MAXTESSELLATIONLEVEL

Maximum tessellation level. The default value is 1.0f.

### -field D3DRS_ADAPTIVETESS_X

Amount to adaptively tessellate, in the x direction. Default value is 0.0f. 

### -field D3DRS_ADAPTIVETESS_Y

Amount to adaptively tessellate, in the y direction. Default value is 0.0f. 

### -field D3DRS_ADAPTIVETESS_Z

Amount to adaptively tessellate, in the z direction. Default value is 1.0f. 

### -field D3DRS_ADAPTIVETESS_W

Amount to adaptively tessellate, in the w direction. Default value is 0.0f. 

### -field D3DRS_ENABLEADAPTIVETESSELLATION

TRUE to enable adaptive tessellation, FALSE to disable it. 

### -field D3DRS_TWOSIDEDSTENCILMODE

TRUE enables two-sided stenciling, FALSE disables it. The default value is FALSE. The application should set D3DRS_CULLMODE to D3DCULL_NONE to enable two-sided stencil mode. If the triangle winding order is clockwise, the D3DRS_STENCIL* operations will be used. If the winding order is counterclockwise, the D3DRS_CCW_STENCIL* operations will be used.

### -field D3DRS_CCW_STENCILFAIL

Stencil operation to perform if CCW stencil test fails.

### -field D3DRS_CCW_STENCILZFAIL

Stencil operation to perform if CCW stencil test passes and z-test fails.

### -field D3DRS_CCW_STENCILPASS

Stencil operation to perform if both CCW stencil and z-tests pass.

### -field D3DRS_CCW_STENCILFUNC

The comparison function. CCW stencil test passes if ((ref & mask) stencil function (stencil & mask)) is TRUE. 

### -field D3DRS_COLORWRITEENABLE1

Additional ColorWriteEnable values for the devices. 

### -field D3DRS_COLORWRITEENABLE2

Additional ColorWriteEnable values for the devices.

### -field D3DRS_COLORWRITEENABLE3

Additional ColorWriteEnable values for the devices.

### -field D3DRS_BLENDFACTOR

A constant blend-factor during alpha blending.

### -field D3DRS_SRGBWRITEENABLE

Enable render-target writes to be gamma corrected to sRGB. The format must expose D3DUSAGE_SRGBWRITE. The default value is 0.

### -field D3DRS_DEPTHBIAS

A floating-point value that is used for comparison of depth values.

### -field D3DRS_WRAP8

See D3DRS_WRAP0.

### -field D3DRS_WRAP9

See D3DRS_WRAP0.

### -field D3DRS_WRAP10

See D3DRS_WRAP0.

### -field D3DRS_WRAP11

See D3DRS_WRAP0.

### -field D3DRS_WRAP12

See D3DRS_WRAP0.

### -field D3DRS_WRAP13

See D3DRS_WRAP0.

### -field D3DRS_WRAP14

See D3DRS_WRAP0.

### -field D3DRS_WRAP15

See D3DRS_WRAP0.

### -field D3DRS_SEPARATEALPHABLENDENABLE

TRUE enables the separate blend mode for the alpha channel. The default value is FALSE.

When set to FALSE, the render-target blending factors and operations applied to alpha are forced to be the same as those defined for color. This mode is effectively hardwired to FALSE on implementations that don't set the cap D3DPMISCCAPS_SEPARATEALPHABLEND. 

### -field D3DRS_SRCBLENDALPHA

This value is ignored unless D3DRS_SEPARATEALPHABLENDENABLE is TRUE.

### -field D3DRS_DESTBLENDALPHA

This value is ignored unless D3DRS_SEPARATEALPHABLENDENABLE is TRUE. 

### -field D3DRS_BLENDOPALPHA

Value used to select the arithmetic operation applied to separate alpha blending when the render state, D3DRS_SEPARATEALPHABLENDENABLE, is set to TRUE.

### -field D3DRS_FORCE_DWORD

Forces this enumeration to compile to 32 bits in size. Without this value, some compilers would allow this enumeration to compile to a size other than 32 bits. This value is not used.



## -remarks

These render states are for internal use only:


#### D3DRENDERSTATE_EVICTMANAGEDTEXTURES

 Determines whether textures are evicted from memory.
The driver uses a BOOL data type without a default value to detect whether to evict.

This render state determines whether the driver evicts textures that it manages (as opposed to textures managed by the Direct3D runtime) from video memory. If the render state value is <b>TRUE</b>, the driver evicts the textures. Otherwise, the driver does not evict those textures.


#### D3DRENDERSTATE_SCENECAPTURE

Specifies either begin scene information or end scene information for geometric data captured within a frame.
The driver uses a BOOL data type with a default value of <b>TRUE</b> to detect scene-capture information.

The driver responds to D3DRENDERSTATE_SCENECAPTURE first with <b>TRUE</b> for begin scene information and next with <b>FALSE</b> for end scene information to capture geometric data within a frame.
See the <i>permedia2</i> sample driver that ships with the Windows Driver Development Kit (DDK) for an example implementation.
Using the D3DRENDERSTATE_SCENECAPTURE render state in a <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a> call replaces the legacy <b>D3DHALCallbacks</b>-&gt;<i>D3dSceneCapture</i> callback routine.

Care must be taken in updating a driver that implements the legacy <b>D3DHALCallbacks</b>-&gt;<i>D3dSceneCapture</i> callback routine to one using the D3DRENDERSTATE_SCENECAPTURE render state. The <i>D3dSceneCapture</i> callback routine uses the constants D3DHAL_SCENE_CAPTURE_START and D3DHAL_SCENE_CAPTURE_END to indicate, respectively, the beginning and end of a scene. The values of these constants are, respectively, 0 and 1. If you use these constants in place of <b>TRUE</b> and <b>FALSE</b> in this render state, the meaning will be the exact opposite of what you intend.


#### D3DRS_DELETERTPATCH

<b>DirectX 8.0 and later versions only.</b>

Deletes either a rectangular or triangular patch from memory. 
The driver uses a DWORD data type without a default value to detect the patch to delete.

This render state notifies the driver that a patch is to be deleted. The value of this render state is the handle to the patch affected. All cached information should be freed and the handle should be removed from the driver's patch handle table. This render state is not visible to applications but is generated internally when an application calls the <b>DeletePatch</b> function. This render state is sent to the driver only when patches are deleted by <b>DeletePatch</b> explicitly. All other patches should be cleaned up when the device is destroyed.


#### D3DRS_MAXPIXELSHADERINST

<b>DirectX 9.0 and later versions only.</b>

Determines the maximum number of instructions that the pixel shader assembler can execute.

The driver uses a DWORD data type with a default value of D3DINFINITEINSTRUCTIONS (0xffffffff) to report the maximum number of pixel-shader instructions.
This maximum number depends on the version of the pixel shader that the display device supports as shown in the following table.

|Version|Maximum number|
|--- |--- |
|earlier than 2_0|0|
|2_0|From 96 to D3DINFINITEINSTRUCTIONS|
|3_0 and later|From 2¹⁶ (0x0000ffff) to D3DINFINITEINSTRUCTIONS|
 

D3DINFINITEINSTRUCTIONS represents a virtually unlimited amount.

Valid values for this render state are numbers that are powers of 2; if the driver sets any other integer, the runtime uses the next nearest power of 2 number.

The runtime sets the <b>MaxVShaderInstructionsExecuted</b> member of the D3DCAPS9 structure to this maximum number.


#### D3DRS_MAXVERTEXSHADERINST

<b>DirectX 9.0 and later versions only.</b>

Determines the maximum number of instructions that the vertex shader assembler can execute.

The driver uses a DWORD data type with a default value of D3DINFINITEINSTRUCTIONS (0xffffffff) to report the maximum number of vertex-shader instructions.
This maximum number depends on the version of the vertex shader that the display device supports as shown in the following table.

|Version|Maximum number|
|--- |--- |
|earlier than 2_0|0|
|2_0 and later|From 2¹⁶ (0x0000ffff) to D3DINFINITEINSTRUCTIONS|
 

D3DINFINITEINSTRUCTIONS represents a virtually unlimited amount.

Valid values for this render state are numbers that are powers of 2; if the driver sets any other integer, the runtime uses the next nearest power of 2 number.

The runtime sets the <b>MaxVShaderInstructionsExecuted</b> member of the D3DCAPS9 structure to this maximum number.


The driver uses these render states when it performs graphics rendering. Only render states that are specific to drivers are included in the Windows Driver Kit (WDK) documentation. The render states accessible to DirectX applications are included in the DirectX SDK documentation. These application-level render states include such characteristics as whether alpha blending is enabled, whether dithering is enabled, whether Direct3D lighting is used, and the type of shading to be used. 

To update a particular render state, Direct3D stores information about the render state, and then calls the driver's <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a> callback routine. The information provided to the driver enables it to:

* Determine that it should update one or more render states.

* Identify which render states to update, and what the new render state values should be.


Note that for certain render states to be honored, the driver must have previously set capability flags in the relevant member of the D3DPRIMCAPS structure.

In order to indicate a specific render state update, Direct3D inserts a <a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a> structure into the command buffer, setting the <b>bCommand</b> member of this structure to D3DDP2OP_RENDERSTATE (see the description for D3DDP2OP_RENDERSTATE in <a href="https://msdn.microsoft.com/library/windows/hardware/ff545678">D3DHAL_DP2OPERATION</a>), and setting the <b>wStateCount</b> member of the same structure to the number of render states to be updated.

Immediately following the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a> structure, Direct3D inserts one <a href="https://msdn.microsoft.com/library/windows/hardware/ff545705">D3DHAL_DP2RENDERSTATE</a> structure into the command buffer for each render state to be updated. The <b>RenderState</b> member of this structure identifies the render state to be changed; the new value of this render state is specified in either the <b>dwState</b> member (for DWORD values) or the <b>fState</b> member (for D3DVALUE values).

The following figure shows a portion of the command buffer containing a D3DDP2OP_RENDERSTATE command and two D3DHAL_DP2RENDERSTATE structures. The first of the three structures indicates that two render states are to be updated. The second structure indicates that the D3DRENDERSTATE_FILLMODE render state is to be changed to D3DFILL_SOLID. The third structure indicates that the D3DRENDERSTATE_SHADEMODE render state should be updated to D3DSHADE_GOURAUD.

<img alt="Figure showing a command buffer with a D3DDP2OP_RENDERSTATE command and two D3DHAL_DP2RENDERSTATE structures" src="images/dp2rs.png"/>

<b>Additional Notes</b>

See the D3DTEXTURESTAGESTATETYPE, D3DTEXTUREOP, and D3DTEXTUREFILTER enumerated types in the DirectX SDK documentation for complete listings of all of the enabled render state types.

Some changes have been made to the D3DRENDERSTATETYPE enumerated type for DirectX 5.0 and beyond. D3DRENDERSTATE_BLENDENABLE has been removed completely although it is defined as D3DRENDERSTATE_ALPHABLENDENABLE in the <i>d3dtypes.h</i> header file. See D3DRENDERSTATE_COLORKEYENABLE for an explanation. The 128 integer values in the interval [128, 255] are reserved for texture coordinate wrap flags. These are constructed with the D3DWRAP_U and D3DWRAP_V macros. Using a flags word preserves forward compatibility with texture coordinates of higher dimension than 2D.

Multitexture macro ops and D3DRENDERSTATE_TEXTUREFACTOR override all of the per-texture stage blending controls (COLOR{OP,ARG1,ARG2} &amp; ALPHA{OP,ARG1,ARG2}).



