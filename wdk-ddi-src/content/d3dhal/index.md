---
UID: NA:d3dhal
ms.assetid: 3950cb86-9a27-30dd-bc8a-034bfa07b5c9
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# D3Dhal.h header



This header is used by Display. For more information, see
- [Display](../_display/index.md)

D3Dhal.h contain these programming interfaces:


## Callback functions

| Title   | Description   |
| ---- |:---- |
| [LPD3DHAL_CONTEXTCREATECB callback](nc-d3dhal-lpd3dhal_contextcreatecb.md) | The D3dContextCreate function creates a context. |
| [LPD3DHAL_CONTEXTDESTROYCB callback](nc-d3dhal-lpd3dhal_contextdestroycb.md) | The D3dContextDestroy function deletes the specified context. |
| [LPD3DHAL_DRAWPRIMITIVES2CB callback](nc-d3dhal-lpd3dhal_drawprimitives2cb.md) | The D3dDrawPrimitives2 function renders primitives and returns the updated render state. |
| [LPD3DHAL_VALIDATETEXTURESTAGESTATECB callback](nc-d3dhal-lpd3dhal_validatetexturestagestatecb.md) | The D3dValidateTextureStageState function returns the number of passes where the hardware can perform the blending operations specified in the current state. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_D3DDeviceDesc_V1 structure](ns-d3dhal-_d3ddevicedesc_v1.md) | Obsolete in DirectX 8.0 and later versions; see Remarks. The D3DDEVICEDESC_V1 structure describes the 3D capabilities of a device. |
| [_D3DDeviceDesc_V2 structure](ns-d3dhal-_d3ddevicedesc_v2.md) | The D3DDEVICEDESC_V2 structure contains fields that are already reported in the D3DHAL_D3DEXTENDEDCAPS structure when responding to the GUID_D3DExtendedCaps GUID in DdGetDriverInfo. |
| [_D3DDeviceDesc_V3 structure](ns-d3dhal-_d3ddevicedesc_v3.md) | The D3DDEVICEDESC_V3 structure contains fields that are already reported in the D3DHAL_D3DEXTENDEDCAPS structure when responding to the GUID_D3DExtendedCaps GUID in DdGetDriverInfo. |
| [_D3DHAL_CALLBACKS structure](ns-d3dhal-_d3dhal_callbacks.md) | D3DHAL_CALLBACKS is one of several callback structures that describe the Direct3D support provided by the driver. |
| [_D3DHAL_CALLBACKS3 structure](ns-d3dhal-_d3dhal_callbacks3.md) | D3DHAL_CALLBACKS3 is one of several callback structures that describe the Direct3D support provided by the driver. |
| [_D3DHAL_CLIPPEDTRIANGLEFAN structure](ns-d3dhal-_d3dhal_clippedtrianglefan.md) | DirectX 8.0 and later versions only. |
| [_D3DHAL_CONTEXTCREATEDATA structure](ns-d3dhal-_d3dhal_contextcreatedata.md) | The D3DHAL_CONTEXTCREATEDATA structure contains all of the information that the D3dContextCreate function requires to create a new context. |
| [_D3DHAL_CONTEXTDESTROYDATA structure](ns-d3dhal-_d3dhal_contextdestroydata.md) | The D3DHAL_CONTEXTDESTROYDATA structure contains the information that the D3dContextDestroy function requires to delete a context. |
| [_D3DHAL_D3DEXTENDEDCAPS structure](ns-d3dhal-_d3dhal_d3dextendedcaps.md) | D3DHAL_D3DEXTENDEDCAPS describes additional 3D capabilities of the driver. |
| [_D3DHAL_DP2ADDDIRTYBOX structure](ns-d3dhal-_d3dhal_dp2adddirtybox.md) | DirectX 8.1 and later versions only. D3DHAL_DP2ADDDIRTYBOX is used to specify that a portion of a 3D resource--a volume texture--was dirtied in system memory. Therefore, this volume must be reloaded into video memory before being used. |
| [_D3DHAL_DP2ADDDIRTYRECT structure](ns-d3dhal-_d3dhal_dp2adddirtyrect.md) | DirectX 8.1 and later versions only. D3DHAL_DP2ADDDIRTYRECT is used to specify that a portion of a 2D resource--a 2D texture or cube texture--was dirtied in system memory. Therefore, this 2D texture must be reloaded into video memory before being used. |
| [_D3DHAL_DP2BLT structure](ns-d3dhal-_d3dhal_dp2blt.md) | DirectX 9.0 and later versions only. D3DHAL_DP2BLT is used for two dimensional surface blts when D3dDrawPrimitives2 responds to the D3DDP2OP_BLT command token. |
| [_D3DHAL_DP2BUFFERBLT structure](ns-d3dhal-_d3dhal_dp2bufferblt.md) | DirectX 8.0 and later versions only. D3DHAL_DP2BUFFERBLT is used for vertex or index buffer blts when D3dDrawPrimitives2 responds to the D3DDP2OP_BUFFERBLT command token. |
| [_D3DHAL_DP2CLEAR structure](ns-d3dhal-_d3dhal_dp2clear.md) | D3DHAL_DP2CLEAR contains all of the information that the driver needs to perform hardware-assisted clearing on the rendering target, depth buffer or stencil buffer. |
| [_D3DHAL_DP2COLORFILL structure](ns-d3dhal-_d3dhal_dp2colorfill.md) | DirectX 9.0 and later versions only. D3DHAL_DP2COLORFILL is used for color-fill operations when D3dDrawPrimitives2 responds to the D3DDP2OP_COLORFILL command token. |
| [_D3DHAL_DP2COMMAND structure](ns-d3dhal-_d3dhal_dp2command.md) | One or more D3DHAL_DP2COMMAND structures are parsed from the command buffer by the D3dDrawPrimitives2 callback, which uses the information it receives to draw one or more primitives. |
| [_D3DHAL_DP2CREATELIGHT structure](ns-d3dhal-_d3dhal_dp2createlight.md) | The D3DHAL_DP2CREATELIGHT structure is used to create a light for D3dDrawPrimitives2. |
| [_D3DHAL_DP2CREATEPIXELSHADER structure](ns-d3dhal-_d3dhal_dp2createpixelshader.md) | DirectX 8.0 and later versions only. The D3DHAL_DP2CREATEPIXELSHADER structure is used to create a pixel shader when a D3DDP2OP_CREATEPIXELSHADER opcode is received by D3dDrawPrimitives2. |
| [_D3DHAL_DP2CREATEQUERY structure](ns-d3dhal-_d3dhal_dp2createquery.md) | DirectX 9.0 and later versions only. |
| [_D3DHAL_DP2CREATEVERTEXSHADER structure](ns-d3dhal-_d3dhal_dp2createvertexshader.md) | DirectX 8.0 and later versions only. The D3DHAL_DP2CRED3dDrawPrimitives2ATEVERTEXSHADER structure is used to create a vertex shader when a D3DDP2OP_CREATEVERTEXSHADER opcode is received by . |
| [_D3DHAL_DP2CREATEVERTEXSHADERDECL structure](ns-d3dhal-_d3dhal_dp2createvertexshaderdecl.md) | DirectX 9.0 and later versions only. The D3DHAL_DP2CREATEVERTEXSHADERDECL structure is used to create a vertex shader declaration when a D3DDP2OP_CREATEVERTEXSHADERDECL opcode is received by D3dDrawPrimitives2. |
| [_D3DHAL_DP2CREATEVERTEXSHADERFUNC structure](ns-d3dhal-_d3dhal_dp2createvertexshaderfunc.md) | DirectX 9.0 and later versions only. The D3DHAL_DP2CREATEVERTEXSHADERFUNC structure is used to create a vertex shader code object when a D3DDP2OP_CREATEVERTEXSHADERFUNC opcode is received by D3dDrawPrimitives2. |
| [_D3DHAL_DP2DELETEQUERY structure](ns-d3dhal-_d3dhal_dp2deletequery.md) | DirectX 9.0 and later versions only. |
| [_D3DHAL_DP2DRAWINDEXEDPRIMITIVE structure](ns-d3dhal-_d3dhal_dp2drawindexedprimitive.md) | DirectX 8.0 and later versions only. |
| [_D3DHAL_DP2DRAWINDEXEDPRIMITIVE2 structure](ns-d3dhal-_d3dhal_dp2drawindexedprimitive2.md) | DirectX 8.0 and later versions only. |
| [_D3DHAL_DP2DRAWPRIMITIVE structure](ns-d3dhal-_d3dhal_dp2drawprimitive.md) | DirectX 8.0 and later versions only. D3DHAL_DRAWPRIMITIVE is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_DRAWPRIMITIVE, and is used to render a primitive. |
| [_D3DHAL_DP2DRAWPRIMITIVE2 structure](ns-d3dhal-_d3dhal_dp2drawprimitive2.md) | DirectX 8.0 and later versions only. D3DHAL_DRAWPRIMITIVE2 is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_DRAWPRIMITIVE2, and is used to render a primitive. |
| [_D3DHAL_DP2DRAWRECTPATCH structure](ns-d3dhal-_d3dhal_dp2drawrectpatch.md) | DirectX 8.0 and later versions only. |
| [_D3DHAL_DP2DRAWTRIPATCH structure](ns-d3dhal-_d3dhal_dp2drawtripatch.md) | DirectX 8.0 and later versions only. |
| [_D3DHAL_DP2EXT structure](ns-d3dhal-_d3dhal_dp2ext.md) | The D3DHAL_DP2EXT structure's use has yet to be defined. |
| [_D3DHAL_DP2GENERATEMIPSUBLEVELS structure](ns-d3dhal-_d3dhal_dp2generatemipsublevels.md) | DirectX 9.0 and later versions only. The D3DHAL_DP2GENERATEMIPSUBLEVELS structure is used to inform the driver to automatically generate the sublevels of a given MIP-map texture using a given filter type. |
| [_D3DHAL_DP2INDEXEDLINELIST structure](ns-d3dhal-_d3dhal_dp2indexedlinelist.md) | D3DHAL_DP2INDEXEDLINELIST is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_INDEXEDLINELIST, and is used to render the lines using vertex indices. |
| [_D3DHAL_DP2INDEXEDLINESTRIP structure](ns-d3dhal-_d3dhal_dp2indexedlinestrip.md) | D3DHAL_DP2INDEXEDLINESTRIP is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_INDEXEDLINESTRIP, and is used to render a sequence of connected line segments using vertex indices. |
| [_D3DHAL_DP2INDEXEDTRIANGLEFAN structure](ns-d3dhal-_d3dhal_dp2indexedtrianglefan.md) | D3DHAL_DP2INDEXEDTRIANGLEFAN is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_INDEXEDTRIANGLEFAN, and is used to render a sequence of connected triangles using vertex indices. All of the triangles share a common vertex. |
| [_D3DHAL_DP2INDEXEDTRIANGLELIST structure](ns-d3dhal-_d3dhal_dp2indexedtrianglelist.md) | One or more D3DHAL_DP2INDEXEDTRIANGLELIST structures are parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_INDEXEDTRIANGLELIST, and are used to render a sequence of unconnected triangles using vertex indices. |
| [_D3DHAL_DP2INDEXEDTRIANGLELIST2 structure](ns-d3dhal-_d3dhal_dp2indexedtrianglelist2.md) | One or more D3DHAL_DP2INDEXEDTRIANGLELIST2 structures are parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_INDEXEDTRIANGLELIST2, and are used to render a sequence of unconnected triangles using vertex indices. |
| [_D3DHAL_DP2INDEXEDTRIANGLESTRIP structure](ns-d3dhal-_d3dhal_dp2indexedtrianglestrip.md) | One or more D3DHAL_DP2INDEXEDTRIANGLESTRIP structures are parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_INDEXEDTRIANGLESTRIP, and are used to render strips of connected triangles using vertex indices. |
| [_D3DHAL_DP2ISSUEQUERY structure](ns-d3dhal-_d3dhal_dp2issuequery.md) | DirectX 9.0 and later versions only. |
| [_D3DHAL_DP2LINELIST structure](ns-d3dhal-_d3dhal_dp2linelist.md) | One D3DHAL_DP2LINELIST structure is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_LINELIST, and is used to render unconnected line segments. |
| [_D3DHAL_DP2LINESTRIP structure](ns-d3dhal-_d3dhal_dp2linestrip.md) | One D3DHAL_DP2LINESTRIP structure is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_LINESTRIP, and is used to render the specified connected line segments. |
| [_D3DHAL_DP2MULTIPLYTRANSFORM structure](ns-d3dhal-_d3dhal_dp2multiplytransform.md) | DirectX 8.0 and later versions only. The D3DHAL_DP2MULTIPLYTRANSFORM structure is used to modify the transform matrix for D3dDrawPrimitives2. |
| [_D3DHAL_DP2PIXELSHADER structure](ns-d3dhal-_d3dhal_dp2pixelshader.md) | DirectX 8.0 and later versions only. The D3DHAL_DP2PIXELSHADER structure is used to set the current pixel shader, or delete a pixel shader, depending on the opcode received (D3DDP2OP_SETPIXELSHADER or D3DDP2OP_DELETEPIXELSHADER) by D3dDrawPrimitives2. |
| [_D3DHAL_DP2POINTS structure](ns-d3dhal-_d3dhal_dp2points.md) | One or more D3DHAL_DP2POINTS structures are parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_POINTS, and are used to render the specified points. |
| [_D3DHAL_DP2RENDERSTATE structure](ns-d3dhal-_d3dhal_dp2renderstate.md) | One or more D3DHAL_DP2RENDERSTATE structures are parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_RENDERSTATE, and are used to set the appropriate render state. |
| [_D3DHAL_DP2RESPONSE structure](ns-d3dhal-_d3dhal_dp2response.md) | DirectX 9.0 and later versions only. |
| [_D3DHAL_DP2RESPONSEQUERY structure](ns-d3dhal-_d3dhal_dp2responsequery.md) | DirectX 9.0 and later versions only. |
| [_D3DHAL_DP2SETCLIPPLANE structure](ns-d3dhal-_d3dhal_dp2setclipplane.md) | The D3DHAL_SETCLIPPLANE structure allows user defined clip planes to be used in world space. |
| [_D3DHAL_DP2SETDEPTHSTENCIL structure](ns-d3dhal-_d3dhal_dp2setdepthstencil.md) | DirectX 9.0 and later versions only. The D3DHAL_DP2SETDEPTHSTENCIL structure is used to map a new depth buffer in the driver's current context when the D3DDP2OP_SETDEPTHSTENCIL operation code is received by D3dDrawPrimitives2. |
| [_D3DHAL_DP2SETINDICES structure](ns-d3dhal-_d3dhal_dp2setindices.md) | DirectX 8.0 and later versions only. The D3DHAL_DP2SETINDICES structure is used to set the current index buffer for D3dDrawPrimitives2. |
| [_D3DHAL_DP2SETLIGHT structure](ns-d3dhal-_d3dhal_dp2setlight.md) | The D3DHAL_DP2SETLIGHT structure allows lights to be set for D3dDrawPrimitives2. |
| [_D3DHAL_DP2SETPALETTE structure](ns-d3dhal-_d3dhal_dp2setpalette.md) | The D3DHAL_DP2SETPALETTE structure is used to associate a palette with a texture when a driver responds to D3DDP2OP_SETPALETTE in D3dDrawPrimitives2. |
| [_D3DHAL_DP2SETPIXELSHADERCONST structure](ns-d3dhal-_d3dhal_dp2setpixelshaderconst.md) | DirectX 8.0 and later versions only. The D3DHAL_DP2SETPIXELSHADERCONST structure is used to set one or more of the pixel shader constant registers when the D3DDP2OP_SETPIXELSHADERCONST opcode is received by D3dDrawPrimitives2. |
| [_D3DHAL_DP2SETPRIORITY structure](ns-d3dhal-_d3dhal_dp2setpriority.md) | The D3DHAL_DP2SETPRIORITY structure is used to inform the driver of the priority of the texture specified by the handle dwDDDestSurface. |
| [_D3DHAL_DP2SETRENDERTARGET structure](ns-d3dhal-_d3dhal_dp2setrendertarget.md) | The D3DHAL_DP2SETRENDERTARGET structure is used with the D3DDP2OP_SETRENDERTARGET opcode to map a new rendering target surface and depth buffer in the current context. |
| [_D3DHAL_DP2SETRENDERTARGET2 structure](ns-d3dhal-_d3dhal_dp2setrendertarget2.md) | The D3DHAL_DP2SETRENDERTARGET2 structure is used with the D3DDP2OP_SETRENDERTARGET2 opcode to map a portion of a rendering target surface and depth buffer in the current context. |
| [_D3DHAL_DP2SETSTREAMSOURCE structure](ns-d3dhal-_d3dhal_dp2setstreamsource.md) | DirectX 8.0 and later versions only. The D3DHAL_DP2SETSTREAMSOURCE structure is used to bind a vertex stream source to a vertex buffer for D3dDrawPrimitives2. |
| [_D3DHAL_DP2SETSTREAMSOURCE2 structure](ns-d3dhal-_d3dhal_dp2setstreamsource2.md) | DirectX 9.0 and later versions only. The D3DHAL_DP2SETSTREAMSOURCE2 structure is used to bind a portion of a vertex stream source to a vertex buffer for D3dDrawPrimitives2. |
| [_D3DHAL_DP2SETSTREAMSOURCEFREQ structure](ns-d3dhal-_d3dhal_dp2setstreamsourcefreq.md) | DirectX 9.0 and later versions only. The D3DHAL_DP2SETSTREAMSOURCEFREQ structure is used to set the frequency divisor of a stream source that is bound to a vertex buffer for D3dDrawPrimitives2. |
| [_D3DHAL_DP2SETSTREAMSOURCEUM structure](ns-d3dhal-_d3dhal_dp2setstreamsourceum.md) | DirectX 8.0 and later versions only. The D3DHAL_DP2SETSTREAMSOURCEUM structure is used to bind a vertex stream source to a user memory buffer for D3dDrawPrimitives2. |
| [_D3DHAL_DP2SETTEXLOD structure](ns-d3dhal-_d3dhal_dp2settexlod.md) | The D3DHAL_DP2SETTEXLOD structure is used to set the level of detail (LOD) for MIP maps when the D3DDP2OP_SETTEXLOD command is sent to D3dDrawPrimitives2. |
| [_D3DHAL_DP2SETTRANSFORM structure](ns-d3dhal-_d3dhal_dp2settransform.md) | D3DHAL_DP2SETTRANSFORM structure is used to specify the transform state and matrix for D3dDrawPrimitives2. |
| [_D3DHAL_DP2SETVERTEXSHADERCONST structure](ns-d3dhal-_d3dhal_dp2setvertexshaderconst.md) | DirectX 8.0 and later versions only. The D3DHAL_DP2SETVERTEXSHADERCONST structure is used to set one or more of the vertex shader constant registers when the D3DDP2OP_SETVERTEXSHADERCONST opcode is received by D3dDrawPrimitives2. |
| [_D3DHAL_DP2STARTVERTEX structure](ns-d3dhal-_d3dhal_dp2startvertex.md) | A D3DHAL_DP2STARTVERTEX structure follows certain D3DHAL_DP2COMMAND structures in the command buffer, and indicates the offset in the vertex buffer for the first vertex to use in D3dDrawPrimitives2. |
| [_D3DHAL_DP2STATESET structure](ns-d3dhal-_d3dhal_dp2stateset.md) | The D3DHAL_DP2STATESET structure is used to inform the driver about stateset operations to perform. |
| [_D3DHAL_DP2SURFACEBLT structure](ns-d3dhal-_d3dhal_dp2surfaceblt.md) | DirectX 9.0 and later versions only. D3DHAL_DP2SURFACEBLT is used for two dimensional system memory to video memory surface blts when D3dDrawPrimitives2 responds to the D3DDP2OP_SURFACEBLT command token. |
| [_D3DHAL_DP2TEXBLT structure](ns-d3dhal-_d3dhal_dp2texblt.md) | The D3DHAL_DP2TEXBLT structure is used for texture blts when D3dDrawPrimitives2 responds to the D3DDP2OP_TEXBLT command token. |
| [_D3DHAL_DP2TEXTURESTAGESTATE structure](ns-d3dhal-_d3dhal_dp2texturestagestate.md) | One or more D3DHAL_DP2TEXTURESTAGESTATE structures are parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_TEXTURESTAGESTATE, and are used to set the appropriate texture stage state. |
| [_D3DHAL_DP2TRIANGLEFAN structure](ns-d3dhal-_d3dhal_dp2trianglefan.md) | One D3DHAL_DP2TRIANGLEFAN structure is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_TRIANGLEFAN, and is used to render a triangle fan. |
| [_D3DHAL_DP2TRIANGLEFAN_IMM structure](ns-d3dhal-_d3dhal_dp2trianglefan_imm.md) | One D3DHAL_DP2TRIANGLEFAN_IMM structure is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_TRIANGLEFAN_IMM, and is used to render a triangle fan. |
| [_D3DHAL_DP2TRIANGLELIST structure](ns-d3dhal-_d3dhal_dp2trianglelist.md) | One D3DHAL_DP2TRIANGLELIST structure is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_TRIANGLELIST, and is used to render the specified unconnected triangles. |
| [_D3DHAL_DP2TRIANGLESTRIP structure](ns-d3dhal-_d3dhal_dp2trianglestrip.md) | One D3DHAL_DP2TRIANGLESTRIP structure is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_TRIANGLESTRIP, and is used to render the specified connected triangle strip. |
| [_D3DHAL_DP2UPDATEPALETTE structure](ns-d3dhal-_d3dhal_dp2updatepalette.md) | The D3DHAL_DP2UPDATEPALETTE structure alters the palette that is used for palletized textures. |
| [_D3DHAL_DP2VERTEXSHADER structure](ns-d3dhal-_d3dhal_dp2vertexshader.md) | DirectX 8.0 and later versions only. The D3DHAL_DP2VERTEXSHADER structure sets the current vertex shader, or deletes a vertex shader, depending on the opcode received (D3DDP2OP_SETVERTEXSHADER or D3DDP2OP_DELETEVERTEXSHADER) by D3dDrawPrimitives2. |
| [_D3DHAL_DP2VIEWPORTINFO structure](ns-d3dhal-_d3dhal_dp2viewportinfo.md) | The D3DHAL_DP2VIEWPORTINFO structure is used to inform guard-band aware drivers of the view clipping rectangle. The clipping rectangle is specified by the members dwX, dwY, dwWidth and dwHeight. |
| [_D3DHAL_DP2VOLUMEBLT structure](ns-d3dhal-_d3dhal_dp2volumeblt.md) | DirectX 8.0 and later versions only. The D3DHAL_DP2VOLUMEBLT structure is used for volume texture blts when D3dDrawPrimitives2 responds to the D3DDP2OP_VOLUMEBLT command token. |
| [_D3DHAL_DP2WINFO structure](ns-d3dhal-_d3dhal_dp2winfo.md) | The D3DHAL_DP2WINFO structure is used to inform the driver of the w-range to be used for w-buffering. |
| [_D3DHAL_DP2ZRANGE structure](ns-d3dhal-_d3dhal_dp2zrange.md) | The D3DHAL_DP2ZRANGE structure specifies z-range minimum and maximum in D3dDrawPrimitives2. |
| [_D3DHAL_DRAWPRIMITIVES2DATA structure](ns-d3dhal-_d3dhal_drawprimitives2data.md) | The D3DHAL_DRAWPRIMITIVES2DATA structure contains the information required by the D3dDrawPrimitives2 function to render primitives. |
| [_D3DHAL_GLOBALDRIVERDATA structure](ns-d3dhal-_d3dhal_globaldriverdata.md) | The D3DHAL_GLOBALDRIVERDATA structure specifies the 3D capabilities of the driver and its device. |
| [_D3DHAL_VALIDATETEXTURESTAGESTATEDATA structure](ns-d3dhal-_d3dhal_validatetexturestagestatedata.md) | The D3DHAL_VALIDATETEXTURESTAGESTATEDATA structure contains the information required for the driver to determine and return its ability to support multitexturing using the current state. |
| [_DD_DEFERRED_AGP_AWARE_DATA structure](ns-d3dhal-_dd_deferred_agp_aware_data.md) | DirectX 8.0 and later versions and NT-based operating systems only. DD_DEFERRED_AGP_AWARE_DATA is the data structure pointed to by the lpvData field of DD_GETDRIVERINFODATA for D3DGDI2_TYPE_DEFERRED_AGP_AWARE notifications. |
| [_DD_DXVERSION structure](ns-d3dhal-_dd_dxversion.md) | DirectX 8.0 and later versions only. DD_DXVERSION describes the current DirectX runtime version. |
| [_DD_FREE_DEFERRED_AGP_DATA structure](ns-d3dhal-_dd_free_deferred_agp_data.md) | DirectX 8.0 and later versions and NT-based operating systems only. DD_FREE_DEFERRED_AGP_DATA is the data structure pointed to by the lpvData field of DD_GETDRIVERINFODATA for D3DGDI2_TYPE_DEFER_AGP_FREES and D3DGDI2_TYPE_FREE_DEFERRED_AGP notifications. |
| [_DD_GETADAPTERGROUPDATA structure](ns-d3dhal-_dd_getadaptergroupdata.md) | DirectX 9.0 and later versions only. DD_GETADAPTERGROUPDATA is the data structure pointed to by the lpvData field of DD_GETDRIVERINFODATA for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETADAPTERGROUP. |
| [_DD_GETD3DQUERYCOUNTDATA structure](ns-d3dhal-_dd_getd3dquerycountdata.md) | DirectX 9.0 and later versions only. DD_GETD3DQUERYCOUNTDATA is the data structure pointed to by the lpvData field of DD_GETDRIVERINFODATA for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETD3DQUERYCOUNT. |
| [_DD_GETD3DQUERYDATA structure](ns-d3dhal-_dd_getd3dquerydata.md) | DirectX 9.0 and later versions only. DD_GETD3DQUERYDATA is the data structure pointed to by the lpvData field of DD_GETDRIVERINFODATA for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETD3DQUERY. |
| [_DD_GETDDIVERSIONDATA structure](ns-d3dhal-_dd_getddiversiondata.md) | DirectX 9.0 and later versions only. DD_GETDDIVERSIONDATA is the data structure pointed to by the lpvData field of DD_GETDRIVERINFODATA for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETDDIVERSION. |
| [_DD_GETDRIVERINFO2DATA structure](ns-d3dhal-_dd_getdriverinfo2data.md) | DirectX 8.0 and later versions only. DD_GETDRIVERINFO2DATA is passed in the lpvData member of the DD_GETDRIVERINFODATA structure when GUID_GetDriverInfo2 is specified in the guidInfo member of DD_GETDRIVERINFODATA in a DdGetDriverInfo call. |
| [_DD_GETEXTENDEDMODECOUNTDATA structure](ns-d3dhal-_dd_getextendedmodecountdata.md) | DirectX 9.0 and later versions only. DD_GETEXTENDEDMODECOUNTDATA is the data structure pointed to by the lpvData field of DD_GETDRIVERINFODATA for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETEXTENDEDMODECOUNT. |
| [_DD_GETEXTENDEDMODEDATA structure](ns-d3dhal-_dd_getextendedmodedata.md) | DirectX 9.0 and later versions only. DD_GETEXTENDEDMODEDATA is the data structure pointed to by the lpvData field of DD_GETDRIVERINFODATA for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETEXTENDEDMODE. |
| [_DD_GETFORMATCOUNTDATA structure](ns-d3dhal-_dd_getformatcountdata.md) | DirectX 8.0 and later versions only. DD_GETFORMATCOUNTDATA is the data structure pointed to by the lpvData field of DD_GETDRIVERINFODATA for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETFORMATCOUNT. |
| [_DD_GETFORMATDATA structure](ns-d3dhal-_dd_getformatdata.md) | DD_GETFORMATDATA is the data structure pointed to by the lpvData field of DD_GETDRIVERINFODATA for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETFORMAT. |
| [_DD_MULTISAMPLEQUALITYLEVELSDATA structure](ns-d3dhal-_dd_multisamplequalitylevelsdata.md) | DirectX 9.0 and later versions only. DD_MULTISAMPLEQUALITYLEVELSDATA is the data structure pointed to by the lpvData field of DD_GETDRIVERINFODATA for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETMULTISAMPLEQUALITYLEVELS. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_D3DHAL_DP2OPERATION enumeration](ne-d3dhal-_d3dhal_dp2operation.md) | The D3DHAL_DP2OPERATION enumerated type specifies the D3dDrawPrimitives2 operation in the bCommand member of the D3DHAL_DP2COMMAND structure. |
