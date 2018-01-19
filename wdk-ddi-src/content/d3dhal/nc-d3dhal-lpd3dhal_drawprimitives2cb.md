---
UID: NC:d3dhal.LPD3DHAL_DRAWPRIMITIVES2CB
title: LPD3DHAL_DRAWPRIMITIVES2CB
author: windows-driver-content
description: The D3dDrawPrimitives2 function renders primitives and returns the updated render state.
old-location: display\d3ddrawprimitives2.htm
old-project: display
ms.assetid: 6128ff7a-0d2c-48df-8b5e-cab33c5a74f5
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DTRANSFORMCAPS, *LPD3DTRANSFORMCAPS, D3DTRANSFORMCAPS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3dDrawPrimitives2
req.alt-loc: d3dhal.h
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
req.typenames: *LPD3DTRANSFORMCAPS, D3DTRANSFORMCAPS
---

# LPD3DHAL_DRAWPRIMITIVES2CB callback



## -description
The <b>D3dDrawPrimitives2</b> function renders primitives and returns the updated render state.



## -prototype

````
LPD3DHAL_DRAWPRIMITIVES2CB D3dDrawPrimitives2;

DWORD APIENTRY D3dDrawPrimitives2(
  _In_ LPD3DHAL_DRAWPRIMITIVES2DATA pdp
)
{ ... }
````


## -parameters

### -param pdp [in]

Points to a <a href="..\d3dhal\ns-d3dhal-_d3dhal_drawprimitives2data.md">D3DHAL_DRAWPRIMITIVES2DATA</a> structure that contains the information required for the driver to render one or more primitives.


## -returns
<b>D3dDrawPrimitives2</b> returns one of the following callback codes:
<dl>
<dt>
<a href="https://msdn.microsoft.com/da4cc7d7-6826-48aa-96c6-004e31fc3e3e">DDHAL_DRIVER_HANDLED</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/da4cc7d7-6826-48aa-96c6-004e31fc3e3e">DDHAL_DRIVER_NOTHANDLED</a>
</dt>
</dl>

## -remarks
<b>D3dDrawPrimitives2</b> must be implemented in Microsoft Direct3D drivers.

The driver must do the following:

Ensure that the context handle specified by the <b>dwhContext</b> member of the D3DHAL_DRAWPRIMITIVES2DATA structure at <i>pdp</i> is valid.

Check that a flip to the drawing surface associated with the context is not in progress. If the drawing surface is involved in a flip, the driver should set the <b>ddrval</b> member of D3DHAL_DRAWPRIMITIVES2DATA to DDERR_WASSTILLDRAWING and return DDHAL_DRIVER_HANDLED.

Determine the location of the first <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a> structure by adding the number of bytes in the <b>dwCommandOffset</b> member of D3DHAL_DRAWPRIMITIVES2DATA to the command buffer to which the <b>lpDDCommands</b> member of D3DHAL_DRAWPRIMITIVES2DATA points.

Determine the location of the first vertex in the vertex buffer. This should only be done if there is data in the vertex buffer; that is, when a D3DDP2OP_<i>Xxx</i> command token is received (except when the token is D3DDP2OP_LINELIST_IMM or D3DDP2OP_TRIANGLEFAN_IMM). These two opcodes indicate that the vertex data is passed immediately in the command stream, rather than in a vertex buffer. So, assuming there is data in the vertex buffer, if the vertex buffer is in user memory, the first vertex is <b>dwVertexOffset</b> bytes into the buffer that <b>lpVertices</b> points to. Otherwise, the driver should apply <b>dwVertexOffset</b> to the memory associated with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551733">DD_SURFACE_LOCAL</a> structure to which <b>lpDDVertex</b> points. <b>dwVertexOffset</b>, <b>lpVertices</b>, and <b>lpDDVertex</b> are members of D3DHAL_DRAWPRIMITIVES2DATA.

The driver does not need to probe for readability of the memory where the command and vertex buffers are stored. However, the driver must stay within the bounds specified by the <b>dwCommandLength</b> and <b>dwVertexLength</b> members of D3DHAL_DRAWPRIMITIVES2DATA.

If the driver must fail <b>D3dDrawPrimitives2</b>, it should fill in the <b>dwErrorOffset</b> member of D3DHAL_DRAWPRIMITIVES2DATA with the offset into the command buffer where the first unhandled D3DHAL_DP2COMMAND can be found.
<p class="note">The following comments are not valid for applications that are written using DirectX 8.0 and later interfaces because such applications no longer use the concept of a current vertex buffer (that is, vertex data is no longer passed in via the <b>lpDDVertex</b> member of D3DHAL_DRAWPRIMITIVES2DATA). Therefore, with these applications, the driver's <b>D3dDrawPrimitives2</b> function should never cause rendering from a vertex buffer to stall even if the buffer is implicit or explicit and there is an outstanding lock on it. 

If the driver is used with a DirectX 8.1 or later runtime, the driver's <b>D3dDrawPrimitives2</b> function should never cause rendering from the current vertex buffer (passed in via <b>lpDDVertex</b>) to stall if the buffer is implicit. If the buffer is explicit and there is an outstanding lock on it, the driver should stall at the end of its <b>D3dDrawPrimitives2</b> function if it does not rename the buffer (does not set D3DHALDP2_SWAPVERTEXBUFFER). If the driver renames the buffer, then the driver does not stall. DirectX 8.1 and later runtimes call the driver's <b>D3dDrawPrimitives2</b> function to render from a locked explicit vertex buffer only when necessary so performance is rarely affected. An implicit vertex buffer is created by the driver's <a href="https://msdn.microsoft.com/8b012e65-b78b-41a4-ac05-d9be015b6ed8">CreateD3DBuffer</a> callback with only the DDSCAPS_EXECUTEBUFFER flag set. An explicit vertex buffer is created by the driver's <i>CreateD3DBuffer</i> callback with the DDSCAPS_EXECUTEBUFFER and DDSCAPS2_VERTEXBUFFER flags set. The explicit vertex buffer becomes locked by the driver's <a href="https://msdn.microsoft.com/8e0714df-1ac8-448c-9f0f-d361640c133a">LockD3DBuffer</a> callback. 

If the driver is used with a DirectX 8.0 runtime, the driver should sometimes stall when rendering from an implicit current vertex buffer to prevent synchronization issues and resulting corruption. In addition, the DirectX 8.0 runtime calls the driver's <b>D3dDrawPrimitives2</b> function to render from a locked explicit current vertex buffer more often then really necessary so performance is degraded. The following are stalling workarounds for a driver that is used with a DirectX 8.0 runtime:

The driver should stall when it transitions between rendering user-memory primitives (identified by D3DHALDP2_USERMEMVERTICES) and rendering from an implicit current vertex buffer only if it does not rename the buffer (does not set D3DHALDP2_SWAPVERTEXBUFFER).

The following example shows when <b>D3dDrawPrimitives2</b> should stall on an implicit current vertex buffer:

The following example shows when <b>D3dDrawPrimitives2</b> should not stall on an implicit current vertex buffer:

If the runtime sets the D3DHALDP2_REQCOMMANDBUFSIZE flag, then the driver is not required to stall. By coincidence, the DirectX 8.0 runtime also sets D3DHALDP2_REQCOMMANDBUFSIZE when it most commonly renders from a locked explicit current vertex buffer. The driver can therefore improve performance by not stalling when it detects D3DHALDP2_REQCOMMANDBUFSIZE while rendering from a locked explicit current vertex buffer.

The following example shows when <b>D3dDrawPrimitives2</b> should stall on an explicit current vertex buffer:

The following example shows when <b>D3dDrawPrimitives2</b> should not stall on an explicit current vertex buffer:


## -see-also
<dl>
<dt>
<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2indexedlinelist.md">D3DHAL_DP2INDEXEDLINELIST</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2indexedlinestrip.md">D3DHAL_DP2INDEXEDLINESTRIP</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2indexedtrianglefan.md">D3DHAL_DP2INDEXEDTRIANGLEFAN</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2indexedtrianglelist.md">D3DHAL_DP2INDEXEDTRIANGLELIST</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2indexedtrianglestrip.md">D3DHAL_DP2INDEXEDTRIANGLESTRIP</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2linelist.md">D3DHAL_DP2LINELIST</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2linestrip.md">D3DHAL_DP2LINESTRIP</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2points.md">D3DHAL_DP2POINTS</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2trianglefan.md">D3DHAL_DP2TRIANGLEFAN</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2trianglelist.md">D3DHAL_DP2TRIANGLELIST</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2trianglestrip.md">D3DHAL_DP2TRIANGLESTRIP</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/206f4275-bcb8-4e8e-9c11-c6fb5d9c561d">FVF</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20LPD3DHAL_DRAWPRIMITIVES2CB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

