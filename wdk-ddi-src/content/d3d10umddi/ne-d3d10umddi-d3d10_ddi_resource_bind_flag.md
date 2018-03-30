---
UID: NE:d3d10umddi.D3D10_DDI_RESOURCE_BIND_FLAG
title: D3D10_DDI_RESOURCE_BIND_FLAG
author: windows-driver-content
description: Identifies how a resource is bound.
old-location: display\d3d10_ddi_resource_bind_flag.htm
old-project: display
ms.assetid: 1c911435-5a55-4b92-9c65-3116d98f8ecf
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D10_DDI_BIND_CONSTANT_BUFFER, D3D10_DDI_BIND_DEPTH_STENCIL, D3D10_DDI_BIND_INDEX_BUFFER, D3D10_DDI_BIND_MASK, D3D10_DDI_BIND_PIPELINE_MASK, D3D10_DDI_BIND_PRESENT, D3D10_DDI_BIND_RENDER_TARGET, D3D10_DDI_BIND_SHADER_RESOURCE, D3D10_DDI_BIND_STREAM_OUTPUT, D3D10_DDI_BIND_VERTEX_BUFFER, D3D10_DDI_RESOURCE_BIND_FLAG, D3D10_DDI_RESOURCE_BIND_FLAG enumeration [Display Devices], D3D11_DDI_BIND_CAPTURE, D3D11_DDI_BIND_DECODER, D3D11_DDI_BIND_MASK, D3D11_DDI_BIND_PIPELINE_MASK, D3D11_DDI_BIND_UNORDERED_ACCESS, D3D11_DDI_BIND_VIDEO_ENCODER, UMDisplayDriver_Dx10param_Structs_bb674d0e-4e3d-42ce-9216-2937f466b1f5.xml, d3d10umddi/D3D10_DDI_BIND_CONSTANT_BUFFER, d3d10umddi/D3D10_DDI_BIND_DEPTH_STENCIL, d3d10umddi/D3D10_DDI_BIND_INDEX_BUFFER, d3d10umddi/D3D10_DDI_BIND_MASK, d3d10umddi/D3D10_DDI_BIND_PIPELINE_MASK, d3d10umddi/D3D10_DDI_BIND_PRESENT, d3d10umddi/D3D10_DDI_BIND_RENDER_TARGET, d3d10umddi/D3D10_DDI_BIND_SHADER_RESOURCE, d3d10umddi/D3D10_DDI_BIND_STREAM_OUTPUT, d3d10umddi/D3D10_DDI_BIND_VERTEX_BUFFER, d3d10umddi/D3D10_DDI_RESOURCE_BIND_FLAG, d3d10umddi/D3D11_DDI_BIND_CAPTURE, d3d10umddi/D3D11_DDI_BIND_DECODER, d3d10umddi/D3D11_DDI_BIND_MASK, d3d10umddi/D3D11_DDI_BIND_PIPELINE_MASK, d3d10umddi/D3D11_DDI_BIND_UNORDERED_ACCESS, d3d10umddi/D3D11_DDI_BIND_VIDEO_ENCODER, display.d3d10_ddi_resource_bind_flag
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	d3d10umddi.h
api_name:
-	D3D10_DDI_RESOURCE_BIND_FLAG
product: Windows
targetos: Windows
req.typenames: D3D10_DDI_RESOURCE_BIND_FLAG, D3D10_DDI_RESOURCE_BIND_FLAG
---

# D3D10_DDI_RESOURCE_BIND_FLAG enumeration


## -description


Identifies how a resource is bound.


## -enum-fields




### -field D3D10_DDI_BIND_VERTEX_BUFFER

The resource can be bound as a vertex buffer in a call to the driver's <a href="https://msdn.microsoft.com/3d5a7ea1-08c2-4594-93bc-97b985cd16dc">IaSetVertexBuffers</a> function. 


### -field D3D10_DDI_BIND_INDEX_BUFFER

The resource can be bound as an index buffer in a call to the driver's <a href="https://msdn.microsoft.com/042ebb72-b794-4cb8-9d81-bd52a785f1e0">IaSetIndexBuffer</a> function. 


### -field D3D10_DDI_BIND_CONSTANT_BUFFER


      The resource can be bound as a constant buffer. 
     


### -field D3D10_DDI_BIND_SHADER_RESOURCE

The resource can be bound as a shader resource in a call to the <a href="https://msdn.microsoft.com/b5cd87bb-7a08-444c-9120-d7ab79e512c5">GsSetShaderResources</a>, <a href="https://msdn.microsoft.com/e30aabdd-52b7-40c0-bb92-50cbabdc5e1f">PsSetShaderResources</a>, or <a href="https://msdn.microsoft.com/4d432517-97f0-441f-ac49-0416ac19b319">VsSetShaderResources</a> function.


### -field D3D10_DDI_BIND_STREAM_OUTPUT

The resource can be bound as a stream output.


### -field D3D10_DDI_BIND_RENDER_TARGET

The resource can be bound as a render target.


### -field D3D10_DDI_BIND_DEPTH_STENCIL


      The resource can be bound as a depth-stencil buffer.
     


### -field D3D10_DDI_BIND_PIPELINE_MASK

A mask value that indicates the valid bitfields in a bitwise <b>OR</b> combination of the first seven values from this enumeration.


### -field D3D10_DDI_BIND_PRESENT

The resource can be used in a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff569179">PresentDXGI</a> function (that is, the resource can be used as a back buffer).


### -field D3D10_DDI_BIND_MASK

A mask value that indicates the valid bitfields in a bitwise <b>OR</b> combination of the Direct3D version 10 values from this enumeration.


### -field D3D11_DDI_BIND_UNORDERED_ACCESS

The resource can be bound as an unordered-access buffer.

Supported starting with Windows 8.

The resource can be bound as an unordered-access buffer.

Supported starting with Windows 7.


### -field D3D11_DDI_BIND_DECODER

The resource is a two-dimensional (2-D) texture that is filled by the video decoder engine.

This value cannot be used simultaneously with the <b>D3D10_DDI_BIND_RENDER_TARGET</b> enumeration value.

Supported starting with Windows 8.


### -field D3D11_DDI_BIND_VIDEO_ENCODER

The resource is used as an input for a hardware-encode Media Foundation Transform (MFT).

This value cannot be used simultaneously with these values from this enumeration:<ul>
<li><b>D3D11_DDI_BIND_CONSTANT_BUFFER</b></li>
<li><b>D3D11_DDI_BIND_DEPTH_STENCIL</b></li>
<li><b>D3D11_DDI_BIND_INDEX_BUFFER</b></li>
<li><b>D3D11_DDI_BIND_VERTEX_BUFFER</b></li>
</ul>


Supported starting with Windows 8.


### -field D3D11_DDI_BIND_CAPTURE

The 2-D texture is used to receive data from the capture interface.

This value cannot be used simultaneously with these values from this enumeration:<ul>
<li><b>D3D11_DDI_BIND_CONSTANT_BUFFER</b></li>
<li><b>D3D11_DDI_BIND_DECODER</b></li>
<li><b>D3D11_DDI_BIND_DEPTH_STENCIL</b></li>
<li><b>D3D11_DDI_BIND_INDEX_BUFFER</b></li>
<li><b>D3D11_DDI_BIND_RENDER_TARGET</b></li>
<li><b>D3D11_DDI_BIND_STREAM_OUTPUT</b></li>
<li><b>D3D11_DDI_BIND_UNORDERED_ACCESS</b></li>
<li><b>D3D11_DDI_BIND_VERTEX_BUFFER</b></li>
</ul>


Supported starting with Windows 8.


### -field D3D11_DDI_BIND_PIPELINE_MASK

A mask value that indicates the valid bitfields in a bitwise <b>OR</b> combination of the first nine values from this enumeration.

Supported starting with Windows 8.

A mask value that indicates the valid bitfields in a bitwise <b>OR</b> combination of the first nine values from this enumeration.

Supported starting with Windows 7.


### -field D3D11_DDI_BIND_MASK

A mask value that indicates the valid bitfields in a bitwise <b>OR</b> combination of the Direct3D version 11 and version 10 values from this enumeration.

Supported starting with Windows 8.

A mask value that indicates the valid bitfields in a bitwise <b>OR</b> combination of the Direct3D version 11 and version 10 values from this enumeration.

Supported starting with Windows 7.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541697">D3D10DDIARG_CREATERESOURCE</a>



<a href="https://msdn.microsoft.com/b5cd87bb-7a08-444c-9120-d7ab79e512c5">GsSetShaderResources</a>



<a href="https://msdn.microsoft.com/042ebb72-b794-4cb8-9d81-bd52a785f1e0">IaSetIndexBuffer</a>



<a href="https://msdn.microsoft.com/3d5a7ea1-08c2-4594-93bc-97b985cd16dc">IaSetVertexBuffers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569179">PresentDXGI</a>



<a href="https://msdn.microsoft.com/e30aabdd-52b7-40c0-bb92-50cbabdc5e1f">PsSetShaderResources</a>



<a href="https://msdn.microsoft.com/4d432517-97f0-441f-ac49-0416ac19b319">VsSetShaderResources</a>
 

 

