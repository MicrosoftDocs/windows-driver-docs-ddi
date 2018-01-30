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
ms.keywords: display.d3ddrawprimitives2, D3dDrawPrimitives2 callback function [Display Devices], D3dDrawPrimitives2, LPD3DHAL_DRAWPRIMITIVES2CB, LPD3DHAL_DRAWPRIMITIVES2CB, d3dhal/D3dDrawPrimitives2, d3dfncs_5f3743b4-be3f-4216-883a-af5103a38c7a.xml
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
-	UserDefined
apilocation:
-	d3dhal.h
apiname:
-	D3dDrawPrimitives2
product: Windows
targetos: Windows
req.typenames: D3DTRANSFORMCAPS, *LPD3DTRANSFORMCAPS
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




### -param LPD3DHAL_DRAWPRIMITIVES2DATA






#### - pdp [in]

Points to a <a href="..\d3dhal\ns-d3dhal-_d3dhal_drawprimitives2data.md">D3DHAL_DRAWPRIMITIVES2DATA</a> structure that contains the information required for the driver to render one or more primitives.


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
Determine the location of the first <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a> structure by adding the number of bytes in the <b>dwCommandOffset</b> member of D3DHAL_DRAWPRIMITIVES2DATA to the command buffer to which the <b>lpDDCommands</b> member of D3DHAL_DRAWPRIMITIVES2DATA points.

</li>
<li>
Determine the location of the first vertex in the vertex buffer. This should only be done if there is data in the vertex buffer; that is, when a D3DDP2OP_<i>Xxx</i> command token is received (except when the token is D3DDP2OP_LINELIST_IMM or D3DDP2OP_TRIANGLEFAN_IMM). These two opcodes indicate that the vertex data is passed immediately in the command stream, rather than in a vertex buffer. So, assuming there is data in the vertex buffer, if the vertex buffer is in user memory, the first vertex is <b>dwVertexOffset</b> bytes into the buffer that <b>lpVertices</b> points to. Otherwise, the driver should apply <b>dwVertexOffset</b> to the memory associated with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551733">DD_SURFACE_LOCAL</a> structure to which <b>lpDDVertex</b> points. <b>dwVertexOffset</b>, <b>lpVertices</b>, and <b>lpDDVertex</b> are members of D3DHAL_DRAWPRIMITIVES2DATA.

</li>
<li>Check the <b>dwVertexType</b> member of D3DHAL_DRAWPRIMITIVES2DATA to ensure that the driver supports the requested <a href="https://msdn.microsoft.com/206f4275-bcb8-4e8e-9c11-c6fb5d9c561d">FVF</a>. The driver should fail the call if any of the following conditions exist:<ul>
<li>Vertex coordinates are not specified; that is, if D3DFVF_XYZRHW is not set.</li>
<li>Normals are specified; that is, if D3DFVF_NORMAL is set.</li>
<li>Any of the reserved D3DFVF_RESERVED <i>x</i> bits are set.</li>
</ul>
</li>
<li>Process all of the commands in the command buffer sequentially. For each D3DHAL_DP2COMMAND structure, the driver should do the following:<ul>
<li>If the command is D3DDP2OP_RENDERSTATE, process the <b>wStateCount </b><a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2renderstate.md">D3DHAL_DP2RENDERSTATE</a> structures that follow in the command buffer, updating the driver state for each render state structure. When the D3DHALDP2_EXECUTEBUFFER flag is set, the driver should also reflect the state change in the array that <b>lpdwRStates</b> points to. <b>wStateCount </b> and <b>lpdwRStates</b> are members of D3DHAL_DRAWPRIMITIVES2DATA.</li>
<li>If the command is D3DDP2OP_TEXTURESTAGESTATE, process the <b>wStateCount </b><a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2texturestagestate.md">D3DHAL_DP2TEXTURESTAGESTATE</a> structures that follow in the command buffer, updating the driver's texture state associated with the specified texture stage for each texture state structure.</li>
<li>If the command is D3DDP2OP_VIEWPORTINFO, process the <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2viewportinfo.md">D3DHAL_DP2VIEWPORTINFO</a> structure that follows in the command buffer, updating the viewport information stored in the driver's internal rendering context.</li>
<li>If the command is D3DDP2OP_WINFO, process the <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2winfo.md">D3DHAL_DP2WINFO</a> structure that follows in the command buffer, updating the w-buffering information stored in the driver's internal rendering context.</li>
<li>Otherwise, process the D3DHAL_DP2<i>Xxx</i> primitive structures that follow the D3DDP2OP_<i>Xxx</i> primitive rendering command in the command buffer.</li>
<li>If the command is unknown, call the runtime's <b>D3dParseUnknownCommand</b> callback. The runtime provides this callback to the driver's <a href="https://msdn.microsoft.com/89a22163-a678-4c72-932a-ae4d17922e0b">DdGetDriverInfo</a> callback with the GUID_D3DParseUnknownCommandCallback GUID. </li>
</ul>
</li>
</ul>The driver does not need to probe for readability of the memory where the command and vertex buffers are stored. However, the driver must stay within the bounds specified by the <b>dwCommandLength</b> and <b>dwVertexLength</b> members of D3DHAL_DRAWPRIMITIVES2DATA.

If the driver must fail <b>D3dDrawPrimitives2</b>, it should fill in the <b>dwErrorOffset</b> member of D3DHAL_DRAWPRIMITIVES2DATA with the offset into the command buffer where the first unhandled D3DHAL_DP2COMMAND can be found.
<div class="alert"><b>Note</b>    The following comments are valid only for applications that are written using Microsoft DirectX 7.0 interfaces and that communicate with drivers through DirectX 8.0 and DirectX 8.1 runtimes.<p class="note">The following comments are not valid for applications that are written using DirectX 8.0 and later interfaces because such applications no longer use the concept of a current vertex buffer (that is, vertex data is no longer passed in via the <b>lpDDVertex</b> member of D3DHAL_DRAWPRIMITIVES2DATA). Therefore, with these applications, the driver's <b>D3dDrawPrimitives2</b> function should never cause rendering from a vertex buffer to stall even if the buffer is implicit or explicit and there is an outstanding lock on it. 

</div><div> </div>If the driver is used with a DirectX 8.1 or later runtime, the driver's <b>D3dDrawPrimitives2</b> function should never cause rendering from the current vertex buffer (passed in via <b>lpDDVertex</b>) to stall if the buffer is implicit. If the buffer is explicit and there is an outstanding lock on it, the driver should stall at the end of its <b>D3dDrawPrimitives2</b> function if it does not rename the buffer (does not set D3DHALDP2_SWAPVERTEXBUFFER). If the driver renames the buffer, then the driver does not stall. DirectX 8.1 and later runtimes call the driver's <b>D3dDrawPrimitives2</b> function to render from a locked explicit vertex buffer only when necessary so performance is rarely affected. An implicit vertex buffer is created by the driver's <a href="https://msdn.microsoft.com/8b012e65-b78b-41a4-ac05-d9be015b6ed8">CreateD3DBuffer</a> callback with only the DDSCAPS_EXECUTEBUFFER flag set. An explicit vertex buffer is created by the driver's <i>CreateD3DBuffer</i> callback with the DDSCAPS_EXECUTEBUFFER and DDSCAPS2_VERTEXBUFFER flags set. The explicit vertex buffer becomes locked by the driver's <a href="https://msdn.microsoft.com/8e0714df-1ac8-448c-9f0f-d361640c133a">LockD3DBuffer</a> callback. 

If the driver is used with a DirectX 8.0 runtime, the driver should sometimes stall when rendering from an implicit current vertex buffer to prevent synchronization issues and resulting corruption. In addition, the DirectX 8.0 runtime calls the driver's <b>D3dDrawPrimitives2</b> function to render from a locked explicit current vertex buffer more often then really necessary so performance is degraded. The following are stalling workarounds for a driver that is used with a DirectX 8.0 runtime:
<ul>
<li>
The driver should stall when it transitions between rendering user-memory primitives (identified by D3DHALDP2_USERMEMVERTICES) and rendering from an implicit current vertex buffer only if it does not rename the buffer (does not set D3DHALDP2_SWAPVERTEXBUFFER).

The following example shows when <b>D3dDrawPrimitives2</b> should stall on an implicit current vertex buffer:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>DrawPrimitives2(p*, D3DHALDP2_USERMEMVERTICES); // Do not stall
DrawPrimitives2(Implicit VB, 0); // Stall </pre>
</td>
</tr>
</table></span></div>
The following example shows when <b>D3dDrawPrimitives2</b> should not stall on an implicit current vertex buffer:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>DrawPrimitives2(p*, D3DHALDP2_USERMEMVERTICES); // Do not stall
DrawPrimitives2(Explicit VB, 0); // Do not stall if not locked
DrawPrimitives2(Explicit VB, D3DHALDP2_SWAPVERTEXBUFFER); // Do not stall whether locked
DrawPrimitives2(Implicit VB, 0); // Do not stall whether locked
DrawPrimitives2(Implicit VB, 0); // Do not stall whether locked
DrawPrimitives2(p*, D3DHALDP2_USERMEMVERTICES); // Do not stall
DrawPrimitives2(Implicit VB, D3DHALDP2_SWAPVERTEXBUFFER); // Do not stall because D3DHALDP2_SWAPVERTEXBUFFER is set</pre>
</td>
</tr>
</table></span></div>
</li>
<li>
If the runtime sets the D3DHALDP2_REQCOMMANDBUFSIZE flag, then the driver is not required to stall. By coincidence, the DirectX 8.0 runtime also sets D3DHALDP2_REQCOMMANDBUFSIZE when it most commonly renders from a locked explicit current vertex buffer. The driver can therefore improve performance by not stalling when it detects D3DHALDP2_REQCOMMANDBUFSIZE while rendering from a locked explicit current vertex buffer.

The following example shows when <b>D3dDrawPrimitives2</b> should stall on an explicit current vertex buffer:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>DrawPrimitives2(Explicit VB, 0); // Stall when locked (happens rarely)</pre>
</td>
</tr>
</table></span></div>
The following example shows when <b>D3dDrawPrimitives2</b> should not stall on an explicit current vertex buffer:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>DrawPrimitives2(Explicit VB, D3DHALDP2_REQCOMMANDBUFSIZE); // Do not stall whether locked
DrawPrimitives2(Explicit VB, D3DHALDP2_SWAPVERTEXBUFFER); // Do not stall whether locked
DrawPrimitives2(Explicit VB, D3DHALDP2_SWAPVERTEXBUFFER | D3DHALDP2_REQCOMMANDBUFSIZE); // Do not stall</pre>
</td>
</tr>
</table></span></div>
</li>
</ul>


## -see-also

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2indexedtrianglefan.md">D3DHAL_DP2INDEXEDTRIANGLEFAN</a>

<a href="https://msdn.microsoft.com/206f4275-bcb8-4e8e-9c11-c6fb5d9c561d">FVF</a>

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2trianglelist.md">D3DHAL_DP2TRIANGLELIST</a>

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2trianglestrip.md">D3DHAL_DP2TRIANGLESTRIP</a>

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2points.md">D3DHAL_DP2POINTS</a>

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2linelist.md">D3DHAL_DP2LINELIST</a>

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2indexedlinelist.md">D3DHAL_DP2INDEXEDLINELIST</a>

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2indexedtrianglelist.md">D3DHAL_DP2INDEXEDTRIANGLELIST</a>

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2indexedlinestrip.md">D3DHAL_DP2INDEXEDLINESTRIP</a>

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2indexedtrianglestrip.md">D3DHAL_DP2INDEXEDTRIANGLESTRIP</a>

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2trianglefan.md">D3DHAL_DP2TRIANGLEFAN</a>

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2linestrip.md">D3DHAL_DP2LINESTRIP</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20LPD3DHAL_DRAWPRIMITIVES2CB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

