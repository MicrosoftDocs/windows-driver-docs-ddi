---
UID: NE:d3d9types._D3DRENDERSTATETYPE
title: "_D3DRENDERSTATETYPE"
author: windows-driver-content
description: The D3DRENDERSTATETYPE enumerated type lists a variety of attributes, or render states.
old-location: display\d3drenderstatetype.htm
old-project: display
ms.assetid: 82978b22-1538-4da0-bcf2-c4c52d2e3429
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DRENDERSTATETYPE, D3DRENDERSTATE_EVICTMANAGEDTEXTURES, D3DRENDERSTATE_SCENECAPTURE, D3DRS_DELETERTPATCH, D3DRS_MAXPIXELSHADERINST, D3DRS_MAXVERTEXSHADERINST, _D3DRENDERSTATETYPE, d3d9types/, d3d9types/D3DRENDERSTATE_EVICTMANAGEDTEXTURES, d3d9types/D3DRENDERSTATE_SCENECAPTURE, d3d9types/D3DRS_DELETERTPATCH, d3d9types/D3DRS_MAXPIXELSHADERINST, d3d9types/D3DRS_MAXVERTEXSHADERINST, d3denum_6b8d96f8-ff88-43c3-9850-a213d84d548f.xml, display.d3drenderstatetype, enumeration [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
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
product: Windows
targetos: Windows
req.typenames: D3DRENDERSTATETYPE
---

# _D3DRENDERSTATETYPE enumeration


## -description


The D3DRENDERSTATETYPE enumerated type lists a variety of attributes, or render states. 
  The enumerators of D3DRENDERSTATETYPE that are used exclusively by drivers can specify either rendering information or a texture attribute. The following render states are used by display drivers:
  


## -enum-fields




### -field D3DRS_ZENABLE


### -field D3DRS_FILLMODE


### -field D3DRS_SHADEMODE


### -field D3DRS_ZWRITEENABLE


### -field D3DRS_ALPHATESTENABLE


### -field D3DRS_LASTPIXEL


### -field D3DRS_SRCBLEND


### -field D3DRS_DESTBLEND


### -field D3DRS_CULLMODE


### -field D3DRS_ZFUNC


### -field D3DRS_ALPHAREF


### -field D3DRS_ALPHAFUNC


### -field D3DRS_DITHERENABLE


### -field D3DRS_ALPHABLENDENABLE


### -field D3DRS_FOGENABLE


### -field D3DRS_SPECULARENABLE


### -field D3DRS_FOGCOLOR


### -field D3DRS_FOGTABLEMODE


### -field D3DRS_FOGSTART


### -field D3DRS_FOGEND


### -field D3DRS_FOGDENSITY


### -field D3DRS_RANGEFOGENABLE


### -field D3DRS_STENCILENABLE


### -field D3DRS_STENCILFAIL


### -field D3DRS_STENCILZFAIL


### -field D3DRS_STENCILPASS


### -field D3DRS_STENCILFUNC


### -field D3DRS_STENCILREF


### -field D3DRS_STENCILMASK


### -field D3DRS_STENCILWRITEMASK


### -field D3DRS_TEXTUREFACTOR


### -field D3DRS_WRAP0


### -field D3DRS_WRAP1


### -field D3DRS_WRAP2


### -field D3DRS_WRAP3


### -field D3DRS_WRAP4


### -field D3DRS_WRAP5


### -field D3DRS_WRAP6


### -field D3DRS_WRAP7


### -field D3DRS_CLIPPING


### -field D3DRS_LIGHTING


### -field D3DRS_AMBIENT


### -field D3DRS_FOGVERTEXMODE


### -field D3DRS_COLORVERTEX


### -field D3DRS_LOCALVIEWER


### -field D3DRS_NORMALIZENORMALS


### -field D3DRS_DIFFUSEMATERIALSOURCE


### -field D3DRS_SPECULARMATERIALSOURCE


### -field D3DRS_AMBIENTMATERIALSOURCE


### -field D3DRS_EMISSIVEMATERIALSOURCE


### -field D3DRS_VERTEXBLEND


### -field D3DRS_CLIPPLANEENABLE


### -field D3DRS_POINTSIZE


### -field D3DRS_POINTSIZE_MIN


### -field D3DRS_POINTSPRITEENABLE


### -field D3DRS_POINTSCALEENABLE


### -field D3DRS_POINTSCALE_A


### -field D3DRS_POINTSCALE_B


### -field D3DRS_POINTSCALE_C


### -field D3DRS_MULTISAMPLEANTIALIAS


### -field D3DRS_MULTISAMPLEMASK


### -field D3DRS_PATCHEDGESTYLE


### -field D3DRS_DEBUGMONITORTOKEN


### -field D3DRS_POINTSIZE_MAX


### -field D3DRS_INDEXEDVERTEXBLENDENABLE


### -field D3DRS_COLORWRITEENABLE


### -field D3DRS_TWEENFACTOR


### -field D3DRS_BLENDOP


### -field D3DRS_POSITIONDEGREE


### -field D3DRS_NORMALDEGREE


### -field D3DRS_SCISSORTESTENABLE


### -field D3DRS_SLOPESCALEDEPTHBIAS


### -field D3DRS_ANTIALIASEDLINEENABLE


### -field D3DRS_MINTESSELLATIONLEVEL


### -field D3DRS_MAXTESSELLATIONLEVEL


### -field D3DRS_ADAPTIVETESS_X


### -field D3DRS_ADAPTIVETESS_Y


### -field D3DRS_ADAPTIVETESS_Z


### -field D3DRS_ADAPTIVETESS_W


### -field D3DRS_ENABLEADAPTIVETESSELLATION


### -field D3DRS_TWOSIDEDSTENCILMODE


### -field D3DRS_CCW_STENCILFAIL


### -field D3DRS_CCW_STENCILZFAIL


### -field D3DRS_CCW_STENCILPASS


### -field D3DRS_CCW_STENCILFUNC


### -field D3DRS_COLORWRITEENABLE1


### -field D3DRS_COLORWRITEENABLE2


### -field D3DRS_COLORWRITEENABLE3


### -field D3DRS_BLENDFACTOR


### -field D3DRS_SRGBWRITEENABLE


### -field D3DRS_DEPTHBIAS


### -field D3DRS_WRAP8


### -field D3DRS_WRAP9


### -field D3DRS_WRAP10


### -field D3DRS_WRAP11


### -field D3DRS_WRAP12


### -field D3DRS_WRAP13


### -field D3DRS_WRAP14


### -field D3DRS_WRAP15


### -field D3DRS_SEPARATEALPHABLENDENABLE


### -field D3DRS_SRCBLENDALPHA


### -field D3DRS_DESTBLENDALPHA


### -field D3DRS_BLENDOPALPHA


### -field D3DRS_FORCE_DWORD




#### - D3DRENDERSTATE_EVICTMANAGEDTEXTURES

 Determines whether textures are evicted from memory.
The driver uses a BOOL data type without a default value to detect whether to evict.

This render state determines whether the driver evicts textures that it manages (as opposed to textures managed by the Direct3D runtime) from video memory. If the render state value is <b>TRUE</b>, the driver evicts the textures. Otherwise, the driver does not evict those textures.


#### - D3DRENDERSTATE_SCENECAPTURE

Specifies either begin scene information or end scene information for geometric data captured within a frame.
The driver uses a BOOL data type with a default value of <b>TRUE</b> to detect scene-capture information.

The driver responds to D3DRENDERSTATE_SCENECAPTURE first with <b>TRUE</b> for begin scene information and next with <b>FALSE</b> for end scene information to capture geometric data within a frame.
See the <i>permedia2</i> sample driver that ships with the Windows Driver Development Kit (DDK) for an example implementation.
Using the D3DRENDERSTATE_SCENECAPTURE render state in a <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a> call replaces the legacy <b>D3DHALCallbacks</b>-&gt;<i>D3dSceneCapture</i> callback routine.

Care must be taken in updating a driver that implements the legacy <b>D3DHALCallbacks</b>-&gt;<i>D3dSceneCapture</i> callback routine to one using the D3DRENDERSTATE_SCENECAPTURE render state. The <i>D3dSceneCapture</i> callback routine uses the constants D3DHAL_SCENE_CAPTURE_START and D3DHAL_SCENE_CAPTURE_END to indicate, respectively, the beginning and end of a scene. The values of these constants are, respectively, 0 and 1. If you use these constants in place of <b>TRUE</b> and <b>FALSE</b> in this render state, the meaning will be the exact opposite of what you intend.


#### - D3DRS_DELETERTPATCH

<b>DirectX 8.0 and later versions only.</b>

Deletes either a rectangular or triangular patch from memory. 
The driver uses a DWORD data type without a default value to detect the patch to delete.

This render state notifies the driver that a patch is to be deleted. The value of this render state is the handle to the patch affected. All cached information should be freed and the handle should be removed from the driver's patch handle table. This render state is not visible to applications but is generated internally when an application calls the <b>DeletePatch</b> function. This render state is sent to the driver only when patches are deleted by <b>DeletePatch</b> explicitly. All other patches should be cleaned up when the device is destroyed.


#### - D3DRS_MAXPIXELSHADERINST

<b>DirectX 9.0 and later versions only.</b>

Determines the maximum number of instructions that the pixel shader assembler can execute.

The driver uses a DWORD data type with a default value of D3DINFINITEINSTRUCTIONS (0xffffffff) to report the maximum number of pixel-shader instructions.
This maximum number depends on the version of the pixel shader that the display device supports as shown in the following table.

<table>
<tr>
<th>Version</th>
<th>Maximum number</th>
</tr>
<tr>
<td>earlier than 2_0</td>
<td>0</td>
</tr>
<tr>
<td>2_0</td>
<td>From 96 to D3DINFINITEINSTRUCTIONS</td>
</tr>
<tr>
<td>3_0 and later</td>
<td>From 2¹⁶ (0x0000ffff) to D3DINFINITEINSTRUCTIONS</td>
</tr>
</table>
 

D3DINFINITEINSTRUCTIONS represents a virtually unlimited amount.

Valid values for this render state are numbers that are powers of 2; if the driver sets any other integer, the runtime uses the next nearest power of 2 number.

The runtime sets the <b>MaxVShaderInstructionsExecuted</b> member of the D3DCAPS9 structure to this maximum number.


#### - D3DRS_MAXVERTEXSHADERINST

<b>DirectX 9.0 and later versions only.</b>

Determines the maximum number of instructions that the vertex shader assembler can execute.

The driver uses a DWORD data type with a default value of D3DINFINITEINSTRUCTIONS (0xffffffff) to report the maximum number of vertex-shader instructions.
This maximum number depends on the version of the vertex shader that the display device supports as shown in the following table.

<table>
<tr>
<th>Version</th>
<th>Maximum number</th>
</tr>
<tr>
<td>earlier than 2_0</td>
<td>0</td>
</tr>
<tr>
<td>2_0 and later</td>
<td>From 2¹⁶ (0x0000ffff) to D3DINFINITEINSTRUCTIONS</td>
</tr>
</table>
 

D3DINFINITEINSTRUCTIONS represents a virtually unlimited amount.

Valid values for this render state are numbers that are powers of 2; if the driver sets any other integer, the runtime uses the next nearest power of 2 number.

The runtime sets the <b>MaxVShaderInstructionsExecuted</b> member of the D3DCAPS9 structure to this maximum number.


## -remarks



The driver uses these render states when it performs graphics rendering. Only render states that are specific to drivers are included in the Windows Driver Kit (WDK) documentation. The render states accessible to DirectX applications are included in the DirectX SDK documentation. These application-level render states include such characteristics as whether alpha blending is enabled, whether dithering is enabled, whether Direct3D lighting is used, and the type of shading to be used. 

To update a particular render state, Direct3D stores information about the render state, and then calls the driver's <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a> callback routine. The information provided to the driver enables it to:

<ul>
<li>
Determine that it should update one or more render states.

</li>
<li>
Identify which render states to update, and what the new render state values should be.

</li>
</ul>
Note that for certain render states to be honored, the driver must have previously set capability flags in the relevant member of the D3DPRIMCAPS structure.

In order to indicate a specific render state update, Direct3D inserts a <a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a> structure into the command buffer, setting the <b>bCommand</b> member of this structure to D3DDP2OP_RENDERSTATE (see the description for D3DDP2OP_RENDERSTATE in <a href="https://msdn.microsoft.com/library/windows/hardware/ff545678">D3DHAL_DP2OPERATION</a>), and setting the <b>wStateCount</b> member of the same structure to the number of render states to be updated.

Immediately following the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a> structure, Direct3D inserts one <a href="https://msdn.microsoft.com/library/windows/hardware/ff545705">D3DHAL_DP2RENDERSTATE</a> structure into the command buffer for each render state to be updated. The <b>RenderState</b> member of this structure identifies the render state to be changed; the new value of this render state is specified in either the <b>dwState</b> member (for DWORD values) or the <b>fState</b> member (for D3DVALUE values).

The following figure shows a portion of the command buffer containing a D3DDP2OP_RENDERSTATE command and two D3DHAL_DP2RENDERSTATE structures. The first of the three structures indicates that two render states are to be updated. The second structure indicates that the D3DRENDERSTATE_FILLMODE render state is to be changed to D3DFILL_SOLID. The third structure indicates that the D3DRENDERSTATE_SHADEMODE render state should be updated to D3DSHADE_GOURAUD.

<img alt="Figure showing a command buffer with a D3DDP2OP_RENDERSTATE command and two D3DHAL_DP2RENDERSTATE structures" src="images/dp2rs.png"/>
<b>
     Additional Notes</b>

See the D3DTEXTURESTAGESTATETYPE, D3DTEXTUREOP, and D3DTEXTUREFILTER enumerated types in the DirectX SDK documentation for complete listings of all of the enabled render state types.

Some changes have been made to the D3DRENDERSTATETYPE enumerated type for DirectX 5.0 and beyond. D3DRENDERSTATE_BLENDENABLE has been removed completely although it is defined as D3DRENDERSTATE_ALPHABLENDENABLE in the <i>d3dtypes.h</i> header file. See D3DRENDERSTATE_COLORKEYENABLE for an explanation. The 128 integer values in the interval [128, 255] are reserved for texture coordinate wrap flags. These are constructed with the D3DWRAP_U and D3DWRAP_V macros. Using a flags word preserves forward compatibility with texture coordinates of higher dimension than 2D.

Multitexture macro ops and D3DRENDERSTATE_TEXTUREFACTOR override all of the per-texture stage blending controls (COLOR{OP,ARG1,ARG2} &amp; ALPHA{OP,ARG1,ARG2}).



