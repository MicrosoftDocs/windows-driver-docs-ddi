---
UID: NC:d3dhal.LPD3DHAL_DRAWPRIMITIVES2CB
title: LPD3DHAL_DRAWPRIMITIVES2CB (d3dhal.h)
description: The D3dDrawPrimitives2 function renders primitives and returns the updated render state.
old-location: display\d3ddrawprimitives2.htm
tech.root: display
ms.assetid: 6128ff7a-0d2c-48df-8b5e-cab33c5a74f5
ms.date: 05/10/2018
keywords: ["LPD3DHAL_DRAWPRIMITIVES2CB callback function"]
ms.keywords: D3dDrawPrimitives2, D3dDrawPrimitives2 callback function [Display Devices], LPD3DHAL_DRAWPRIMITIVES2CB, LPD3DHAL_DRAWPRIMITIVES2CB callback, d3dfncs_5f3743b4-be3f-4216-883a-af5103a38c7a.xml, d3dhal/D3dDrawPrimitives2, display.d3ddrawprimitives2
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Desktop
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
req.typenames: 
f1_keywords:
 - LPD3DHAL_DRAWPRIMITIVES2CB
 - d3dhal/LPD3DHAL_DRAWPRIMITIVES2CB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dhal.h
api_name:
 - D3dDrawPrimitives2
---

# LPD3DHAL_DRAWPRIMITIVES2CB callback function


## -description

The <b>D3dDrawPrimitives2</b> function renders primitives and returns the updated render state.

## -parameters

### -param Arg1

*pdp* [in]

Points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_drawprimitives2data">D3DHAL_DRAWPRIMITIVES2DATA</a> structure that contains the information required for the driver to render one or more primitives.

## -returns

<b>D3dDrawPrimitives2</b> returns one of the following callback codes:

## -remarks

<b>D3dDrawPrimitives2</b> must be implemented in Microsoft Direct3D drivers.

The driver must do the following:

<ul>
<li>
Ensure that the context handle specified by the <b>dwhContext</b> member of the D3DHAL_DRAWPRIMITIVES2DATA structure at <i>pdp</i> is valid.

</li>
<li>
Check that a flip to the drawing surface associated with the context is not in progress. If the drawing surface is involved in a flip, the driver should set the <b>ddrval</b> member of D3DHAL_DRAWPRIMITIVES2DATA to DDERR_WASSTILLDRAWING and return DDHAL_DRIVER_HANDLED.

</li>
<li>
Determine the location of the first <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a> structure by adding the number of bytes in the <b>dwCommandOffset</b> member of D3DHAL_DRAWPRIMITIVES2DATA to the command buffer to which the <b>lpDDCommands</b> member of D3DHAL_DRAWPRIMITIVES2DATA points.

</li>
<li>
Determine the location of the first vertex in the vertex buffer. This should only be done if there is data in the vertex buffer; that is, when a D3DDP2OP_<i>Xxx</i> command token is received (except when the token is D3DDP2OP_LINELIST_IMM or D3DDP2OP_TRIANGLEFAN_IMM). These two opcodes indicate that the vertex data is passed immediately in the command stream, rather than in a vertex buffer. So, assuming there is data in the vertex buffer, if the vertex buffer is in user memory, the first vertex is <b>dwVertexOffset</b> bytes into the buffer that <b>lpVertices</b> points to. Otherwise, the driver should apply <b>dwVertexOffset</b> to the memory associated with the <a href="https://docs.microsoft.com/windows/win32/api/ddrawint/ns-ddrawint-dd_surface_local">DD_SURFACE_LOCAL</a> structure to which <b>lpDDVertex</b> points. <b>dwVertexOffset</b>, <b>lpVertices</b>, and <b>lpDDVertex</b> are members of D3DHAL_DRAWPRIMITIVES2DATA.

</li>
<li>Check the <b>dwVertexType</b> member of D3DHAL_DRAWPRIMITIVES2DATA to ensure that the driver supports the requested <a href="https://docs.microsoft.com/windows-hardware/drivers/display/fvf--flexible-vertex-format-">FVF</a>. The driver should fail the call if any of the following conditions exist:<ul>
<li>Vertex coordinates are not specified; that is, if D3DFVF_XYZRHW is not set.</li>
<li>Normals are specified; that is, if D3DFVF_NORMAL is set.</li>
<li>Any of the reserved D3DFVF_RESERVED <i>x</i> bits are set.</li>
</ul>
</li>
<li>Process all of the commands in the command buffer sequentially. For each D3DHAL_DP2COMMAND structure, the driver should do the following:<ul>
<li>If the command is D3DDP2OP_RENDERSTATE, process the <b>wStateCount </b><a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2renderstate">D3DHAL_DP2RENDERSTATE</a> structures that follow in the command buffer, updating the driver state for each render state structure. When the D3DHALDP2_EXECUTEBUFFER flag is set, the driver should also reflect the state change in the array that <b>lpdwRStates</b> points to. <b>wStateCount </b> and <b>lpdwRStates</b> are members of D3DHAL_DRAWPRIMITIVES2DATA.</li>
<li>If the command is D3DDP2OP_TEXTURESTAGESTATE, process the <b>wStateCount </b><a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2texturestagestate">D3DHAL_DP2TEXTURESTAGESTATE</a> structures that follow in the command buffer, updating the driver's texture state associated with the specified texture stage for each texture state structure.</li>
<li>If the command is D3DDP2OP_VIEWPORTINFO, process the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2viewportinfo">D3DHAL_DP2VIEWPORTINFO</a> structure that follows in the command buffer, updating the viewport information stored in the driver's internal rendering context.</li>
<li>If the command is D3DDP2OP_WINFO, process the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2winfo">D3DHAL_DP2WINFO</a> structure that follows in the command buffer, updating the w-buffering information stored in the driver's internal rendering context.</li>
<li>Otherwise, process the D3DHAL_DP2<i>Xxx</i> primitive structures that follow the D3DDP2OP_<i>Xxx</i> primitive rendering command in the command buffer.</li>
<li>If the command is unknown, call the runtime's <b>D3dParseUnknownCommand</b> callback. The runtime provides this callback to the driver's <a href="https://docs.microsoft.com/windows/win32/api/ddrawint/nc-ddrawint-pdd_getdriverinfo">DdGetDriverInfo</a> callback with the GUID_D3DParseUnknownCommandCallback GUID. </li>
</ul>
</li>
</ul>
The driver does not need to probe for readability of the memory where the command and vertex buffers are stored. However, the driver must stay within the bounds specified by the <b>dwCommandLength</b> and <b>dwVertexLength</b> members of D3DHAL_DRAWPRIMITIVES2DATA.

If the driver must fail <b>D3dDrawPrimitives2</b>, it should fill in the <b>dwErrorOffset</b> member of D3DHAL_DRAWPRIMITIVES2DATA with the offset into the command buffer where the first unhandled D3DHAL_DP2COMMAND can be found.

<div class="alert"><b>Note</b>    The following comments are valid only for applications that are written using Microsoft DirectX 7.0 interfaces and that communicate with drivers through DirectX 8.0 and DirectX 8.1 runtimes.<p class="note">The following comments are not valid for applications that are written using DirectX 8.0 and later interfaces because such applications no longer use the concept of a current vertex buffer (that is, vertex data is no longer passed in via the <b>lpDDVertex</b> member of D3DHAL_DRAWPRIMITIVES2DATA). Therefore, with these applications, the driver's <b>D3dDrawPrimitives2</b> function should never cause rendering from a vertex buffer to stall even if the buffer is implicit or explicit and there is an outstanding lock on it. 

</div>
<div> </div>
If the driver is used with a DirectX 8.1 or later runtime, the driver's <b>D3dDrawPrimitives2</b> function should never cause rendering from the current vertex buffer (passed in via <b>lpDDVertex</b>) to stall if the buffer is implicit. If the buffer is explicit and there is an outstanding lock on it, the driver should stall at the end of its <b>D3dDrawPrimitives2</b> function if it does not rename the buffer (does not set D3DHALDP2_SWAPVERTEXBUFFER). If the driver renames the buffer, then the driver does not stall. DirectX 8.1 and later runtimes call the driver's <b>D3dDrawPrimitives2</b> function to render from a locked explicit vertex buffer only when necessary so performance is rarely affected. An implicit vertex buffer is created by the driver's <a href="https://docs.microsoft.com/windows/win32/api/ddrawint/nc-ddrawint-pdd_createsurface">CreateD3DBuffer</a> callback with only the DDSCAPS_EXECUTEBUFFER flag set. An explicit vertex buffer is created by the driver's <i>CreateD3DBuffer</i> callback with the DDSCAPS_EXECUTEBUFFER and DDSCAPS2_VERTEXBUFFER flags set. The explicit vertex buffer becomes locked by the driver's <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff568216(v=vs.85)">LockD3DBuffer</a> callback. 

If the driver is used with a DirectX 8.0 runtime, the driver should sometimes stall when rendering from an implicit current vertex buffer to prevent synchronization issues and resulting corruption. In addition, the DirectX 8.0 runtime calls the driver's <b>D3dDrawPrimitives2</b> function to render from a locked explicit current vertex buffer more often then really necessary so performance is degraded. The following are stalling workarounds for a driver that is used with a DirectX 8.0 runtime:

<ul>
<li>
The driver should stall when it transitions between rendering user-memory primitives (identified by D3DHALDP2_USERMEMVERTICES) and rendering from an implicit current vertex buffer only if it does not rename the buffer (does not set D3DHALDP2_SWAPVERTEXBUFFER).

The following example shows when <b>D3dDrawPrimitives2</b> should stall on an implicit current vertex buffer:

```cpp
DrawPrimitives2(p*, D3DHALDP2_USERMEMVERTICES); // Do not stall
DrawPrimitives2(Implicit VB, 0); // Stall 
```

The following example shows when <b>D3dDrawPrimitives2</b> should not stall on an implicit current vertex buffer:

```cpp
DrawPrimitives2(p*, D3DHALDP2_USERMEMVERTICES); // Do not stall
DrawPrimitives2(Explicit VB, 0); // Do not stall if not locked
DrawPrimitives2(Explicit VB, D3DHALDP2_SWAPVERTEXBUFFER); // Do not stall whether locked
DrawPrimitives2(Implicit VB, 0); // Do not stall whether locked
DrawPrimitives2(Implicit VB, 0); // Do not stall whether locked
DrawPrimitives2(p*, D3DHALDP2_USERMEMVERTICES); // Do not stall
DrawPrimitives2(Implicit VB, D3DHALDP2_SWAPVERTEXBUFFER); // Do not stall because D3DHALDP2_SWAPVERTEXBUFFER is set
```

If the runtime sets the D3DHALDP2_REQCOMMANDBUFSIZE flag, then the driver is not required to stall. By coincidence, the DirectX 8.0 runtime also sets D3DHALDP2_REQCOMMANDBUFSIZE when it most commonly renders from a locked explicit current vertex buffer. The driver can therefore improve performance by not stalling when it detects D3DHALDP2_REQCOMMANDBUFSIZE while rendering from a locked explicit current vertex buffer.

The following example shows when <b>D3dDrawPrimitives2</b> should stall on an explicit current vertex buffer:

```cpp
DrawPrimitives2(Explicit VB, 0); // Stall when locked (happens rarely)
```

The following example shows when <b>D3dDrawPrimitives2</b> should not stall on an explicit current vertex buffer:

```cpp
DrawPrimitives2(Explicit VB, D3DHALDP2_REQCOMMANDBUFSIZE); // Do not stall whether locked
DrawPrimitives2(Explicit VB, D3DHALDP2_SWAPVERTEXBUFFER); // Do not stall whether locked
DrawPrimitives2(Explicit VB, D3DHALDP2_SWAPVERTEXBUFFER | D3DHALDP2_REQCOMMANDBUFSIZE); // Do not stall
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2indexedlinelist">D3DHAL_DP2INDEXEDLINELIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2indexedlinestrip">D3DHAL_DP2INDEXEDLINESTRIP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2indexedtrianglefan">D3DHAL_DP2INDEXEDTRIANGLEFAN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2indexedtrianglelist">D3DHAL_DP2INDEXEDTRIANGLELIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2indexedtrianglestrip">D3DHAL_DP2INDEXEDTRIANGLESTRIP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2linelist">D3DHAL_DP2LINELIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2linestrip">D3DHAL_DP2LINESTRIP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2points">D3DHAL_DP2POINTS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2trianglefan">D3DHAL_DP2TRIANGLEFAN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2trianglelist">D3DHAL_DP2TRIANGLELIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2trianglestrip">D3DHAL_DP2TRIANGLESTRIP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/display/fvf--flexible-vertex-format-">FVF</a>

