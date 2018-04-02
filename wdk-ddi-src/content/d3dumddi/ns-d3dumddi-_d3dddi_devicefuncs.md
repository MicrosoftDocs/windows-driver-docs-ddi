---
UID: NS:d3dumddi._D3DDDI_DEVICEFUNCS
title: "_D3DDDI_DEVICEFUNCS"
author: windows-driver-content
description: The D3DDDI_DEVICEFUNCS structure contains functions that the user-mode display driver can implement to render graphics primitives and process state changes.
old-location: display\d3dddi_devicefuncs.htm
old-project: display
ms.assetid: 7345cd67-c10c-46f0-bd56-6f18929f4aa6
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDI_DEVICEFUNCS, D3DDDI_DEVICEFUNCS structure [Display Devices], D3D_other_Structs_108deb18-33e2-4a62-9d10-777352fbdd27.xml, _D3DDDI_DEVICEFUNCS, d3dumddi/D3DDDI_DEVICEFUNCS, display.d3dddi_devicefuncs
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
api_name:
-	D3DDDI_DEVICEFUNCS
product: Windows
targetos: Windows
req.typenames: D3DDDI_DEVICEFUNCS
---

# _D3DDDI_DEVICEFUNCS structure


## -description


The D3DDDI_DEVICEFUNCS structure contains functions that the user-mode display driver can implement to render graphics primitives and process state changes.


## -struct-fields




### -field pfnSetRenderState

A pointer to the driver <a href="https://msdn.microsoft.com/22fb67f7-cc28-4f10-950d-1379769ddf89">SetRenderState</a> function that updates the render state.


### -field pfnUpdateWInfo

A pointer to the driver <a href="https://msdn.microsoft.com/e9cd87b9-3958-4b10-895d-480e03ebea76">UpdateWInfo</a> function that updates the w range for w buffering.


### -field pfnValidateDevice

A pointer to the driver <a href="https://msdn.microsoft.com/058696e0-be4a-45f3-b3e8-55abccdce3ce">ValidateDevice</a> function that returns the number of passes in which the hardware can perform the blending operations that are specified in the current state. 


### -field pfnSetTextureStageState

A pointer to the driver <a href="https://msdn.microsoft.com/56b9d7bf-1036-4ad1-a0fb-4d7154b50b27">SetTextureStageState</a> function that updates the state of a texture at a particular stage in a multiple-texture group.


### -field pfnSetTexture

A pointer to the driver <a href="https://msdn.microsoft.com/b2ed86c5-cd4f-4aaa-a062-4c7ae4e088df">SetTexture</a> function that sets a texture to a particular stage in a multiple-texture group.


### -field pfnSetPixelShader

A pointer to the driver <a href="https://msdn.microsoft.com/b7ffd96d-086e-445a-89cf-6f34a5b8a5d4">SetPixelShader</a> function that sets the current pixel shader.


### -field pfnSetPixelShaderConst

A pointer to the driver <a href="https://msdn.microsoft.com/02710936-28df-4c8f-aa1e-bdff01155608">SetPixelShaderConst</a> function that sets one or more pixel shader constant registers with float values.


### -field pfnSetStreamSourceUm

A pointer to the driver <a href="https://msdn.microsoft.com/75a70801-0338-45ed-a691-5f84202575d5">SetStreamSourceUM</a> function that binds a vertex stream source to a user memory buffer.


### -field pfnSetIndices

A pointer to the driver <a href="https://msdn.microsoft.com/5348b3f9-78c5-4915-ba68-296d6f9f916c">SetIndices</a> function that sets the current index buffer.


### -field pfnSetIndicesUm

A pointer to the driver <a href="https://msdn.microsoft.com/9ca38004-8953-4416-8552-c76813192561">SetIndicesUM</a> function that binds an index buffer to a user memory buffer.


### -field pfnDrawPrimitive

A pointer to the driver <a href="https://msdn.microsoft.com/1a6de2b0-cab0-4fcf-be1b-a8cc1c1f79e9">DrawPrimitive</a> function that draws nonindexed primitives in which the Microsoft Direct3D runtime has not transformed the vertex data.


### -field pfnDrawIndexedPrimitive

A pointer to the driver <a href="https://msdn.microsoft.com/12bb6274-d042-43bb-b9f5-1417f42da729">DrawIndexedPrimitive</a> function that draws indexed primitives in which the Direct3D runtime has not transformed the vertex data.


### -field pfnDrawRectPatch

A pointer to the driver <a href="https://msdn.microsoft.com/c0e3046c-f2af-4406-ac5a-c3e44f40b1fd">DrawRectPatch</a> function that draws a new or cached rectangular patch or updates the specification of a previously defined patch.


### -field pfnDrawTriPatch

A pointer to the driver <a href="https://msdn.microsoft.com/98e5f2c5-2795-4226-b5c0-9498b37c22df">DrawTriPatch</a> function that draws a new or cached triangular patch or updates the specification of a previously defined patch.


### -field pfnDrawPrimitive2

A pointer to the driver <a href="https://msdn.microsoft.com/a81080f0-fbb3-4616-9324-642b60befcb3">DrawPrimitive2</a> function that draws nonindexed primitives in which the Direct3D runtime has transformed the vertex data.


### -field pfnDrawIndexedPrimitive2

A pointer to the driver <a href="https://msdn.microsoft.com/f12af70c-a6f2-42da-be62-1cfeb90b6239">DrawIndexedPrimitive2</a> function that draws indexed primitives in which the Direct3D runtime has transformed the vertex data.


### -field pfnVolBlt

A pointer to the driver <a href="https://msdn.microsoft.com/249a55a3-f2cf-4838-8a0f-b7108a17cd78">VolBlt</a> function that performs a bit-block transfer (bitblt) from a source volume texture to a destination volume texture.


### -field pfnBufBlt

A pointer to the driver <a href="https://msdn.microsoft.com/d75f3fad-3bcd-44ad-9bd5-f61f5346cf8d">BufBlt</a> function that performs a bitblt from a source vertex or index buffer to a destination vertex or index buffer.


### -field pfnTexBlt

A pointer to the driver <a href="https://msdn.microsoft.com/1ddfd822-7a43-4976-a153-ba862d6dfd82">TexBlt</a> function that performs a bitblt from a source texture to a destination texture.


### -field pfnStateSet

A pointer to the driver <a href="https://msdn.microsoft.com/2c298de6-a3d9-45c7-ab60-dc9124eed1bb">StateSet</a> function that performs a state-set operation.


### -field pfnSetPriority

A pointer to the driver <a href="https://msdn.microsoft.com/61ac2d28-7aed-4796-8d09-591db936013b">SetPriority</a> function that sets the eviction-from-memory priority for a managed texture.


### -field pfnClear

A pointer to the driver <a href="https://msdn.microsoft.com/library/windows/hardware/hh406339">Clear</a> function that performs hardware-assisted clearing on the rendering target, depth buffer, or stencil buffer.


### -field pfnUpdatePalette

A pointer to the driver <a href="https://msdn.microsoft.com/7c22e0c9-cc24-4398-88b7-c91855cbc731">UpdatePalette</a> function that updates a texture palette.


### -field pfnSetPalette

A pointer to the driver <a href="https://msdn.microsoft.com/5d1c8c2d-7886-4876-b48e-1e6b252ae8f7">SetPalette</a> function that sets the palette for a texture.


### -field pfnSetVertexShaderConst

A pointer to the driver <a href="https://msdn.microsoft.com/2dbde343-b10a-4357-a2b7-d6b1b1b868f2">SetVertexShaderConst</a> function that sets one or more vertex shader constant registers with float values.


### -field pfnMultiplyTransform

A pointer to the driver <a href="https://msdn.microsoft.com/69d94062-5655-4d49-a116-7fa7e2b51a91">MultiplyTransform</a> function that multiplies a current transform.


### -field pfnSetTransform

A pointer to the driver <a href="https://msdn.microsoft.com/0e989ea4-3693-4c0b-86a5-96b865a0193f">SetTransform</a> function that sets up a transform.


### -field pfnSetViewport

A pointer to the driver <a href="https://msdn.microsoft.com/ef0847a3-d4f5-4a9e-a041-1b8f8523fdf7">SetViewport</a> function that informs guard-band aware drivers of the view-clipping rectangle.


### -field pfnSetZRange

A pointer to the driver <a href="https://msdn.microsoft.com/29ccde7c-801c-4e90-bc39-8581f262cc65">SetZRange</a> function that informs the driver about the range of z values.


### -field pfnSetMaterial

A pointer to the driver <a href="https://msdn.microsoft.com/e1273478-a450-44fa-95d5-ee86cb3a46b2">SetMaterial</a> function that sets the material properties that devices on the system use to create the required effect during rendering.


### -field pfnSetLight

A pointer to the driver <a href="https://msdn.microsoft.com/28e3992e-a636-47e2-a5a6-5da06d276b5c">SetLight</a> function that sets properties for a light source.


### -field pfnCreateLight

A pointer to the driver <a href="https://msdn.microsoft.com/4649b1d1-6fd3-48fb-b25f-1228851bb682">CreateLight</a> function that creates a light source.


### -field pfnDestroyLight

A pointer to the driver <a href="https://msdn.microsoft.com/dbc86e4d-a002-4270-a3c4-02d16972c921">DestroyLight</a> function that deactivates a light source.


### -field pfnSetClipPlane

A pointer to the driver <a href="https://msdn.microsoft.com/99edfc35-23a5-41e0-8705-7dffba564c10">SetClipPlane</a> function that sets a clip plane.


### -field pfnGetInfo

A pointer to the driver <a href="https://msdn.microsoft.com/library/windows/hardware/hh451309">GetInfo</a> function that retrieves information about the device.


### -field pfnLock

A pointer to the driver <a href="https://msdn.microsoft.com/e2289073-d46a-4a12-8de7-30400e04cc22">Lock</a> function that locks a resource or a surface within the resource.


### -field pfnUnlock

A pointer to the driver <a href="https://msdn.microsoft.com/23cc9c64-99d4-4602-a1b0-234fe7fcc3da">Unlock</a> function that unlocks a resource or a surface within the resource that the <a href="https://msdn.microsoft.com/e2289073-d46a-4a12-8de7-30400e04cc22">Lock</a> function previously locked.


### -field pfnCreateResource

A pointer to the driver <a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a> function that creates a resource.


### -field pfnDestroyResource

A pointer to the driver <a href="https://msdn.microsoft.com/1af85315-4367-49de-9453-eef62c838c97">DestroyResource</a> function that releases the resource that the <a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a> function created.


### -field pfnSetDisplayMode

A pointer to the driver <a href="https://msdn.microsoft.com/d0e409fe-1c64-4468-b52e-b0ede39f6601">SetDisplayMode</a> function that sets a surface for displaying.


### -field pfnPresent

A pointer to the driver <a href="https://msdn.microsoft.com/e90683b4-64b6-4018-96a5-b50118df3367">Present</a> function that requests that the source surface be displayed by either copying or flipping. 


### -field pfnFlush

A pointer to the user-mode display driver <a href="https://msdn.microsoft.com/library/windows/hardware/hh463886">Flush</a> function that submits outstanding hardware commands that are in the hardware command buffer to the display miniport driver.


### -field pfnCreateVertexShaderFunc

A pointer to the driver <a href="https://msdn.microsoft.com/e986d37a-6039-4bc4-b5e8-6c4d4d7adedd">CreateVertexShaderFunc</a> function that converts the vertex shader code into a hardware-specific format and associates this code with the given shader handle.


### -field pfnDeleteVertexShaderFunc

A pointer to the driver <a href="https://msdn.microsoft.com/780fc47c-bbb9-400a-a2f3-cdce4a18072f">DeleteVertexShaderFunc</a> function that cleans up driver-side resources that are associated with vertex shader code.


### -field pfnSetVertexShaderFunc

A pointer to the driver <a href="https://msdn.microsoft.com/2cea4812-7eba-4558-9c2e-30de460be21f">SetVertexShaderFunc</a> function that sets the vertex shader code so that all of the subsequent drawing operations use that code.


### -field pfnCreateVertexShaderDecl

A pointer to the driver <a href="https://msdn.microsoft.com/00c53e81-93db-46b8-b65c-c8d62059452a">CreateVertexShaderDecl</a> function that converts the vertex shader declaration into a hardware-specific format and associates this declaration with the given shader handle.


### -field pfnDeleteVertexShaderDecl

A pointer to the driver <a href="https://msdn.microsoft.com/8c16cd27-83f9-4474-9031-edfea0ba665b">DeleteVertexShaderDecl</a> function that cleans up driver-side resources that are associated with the vertex shader declaration.


### -field pfnSetVertexShaderDecl

A pointer to the driver <a href="https://msdn.microsoft.com/6387d632-78e2-4594-a58a-b11b2e831cc0">SetVertexShaderDecl</a> function that sets the vertex shader declaration so that all of the subsequent drawing operations use that declaration.


### -field pfnSetVertexShaderConstI

A pointer to the driver <a href="https://msdn.microsoft.com/c245cfbd-0368-4a49-96a7-ac4cd14e2f5a">SetVertexShaderConstI</a> function that sets one or more vertex shader constant registers with integer values.


### -field pfnSetVertexShaderConstB

A pointer to the driver <a href="https://msdn.microsoft.com/41ca823e-4370-4cba-9129-067e25a43a69">SetVertexShaderConstB</a> function that sets one or more vertex shader constant registers with Boolean values.


### -field pfnSetScissorRect

A pointer to the driver <a href="https://msdn.microsoft.com/779fd7ff-e4d6-45b4-8164-186e9cb89513">SetScissorRect</a> function that marks a portion of a render target to which rendering is restricted.


### -field pfnSetStreamSource

A pointer to the driver <a href="https://msdn.microsoft.com/669dbabc-91fb-40f9-a034-11c3c2e70436">SetStreamSource</a> function that binds a portion of a vertex stream source to a vertex buffer.


### -field pfnSetStreamSourceFreq

A pointer to the driver <a href="https://msdn.microsoft.com/92cb270c-1548-4239-81cd-5b3483769fc8">SetStreamSourceFreq</a> function that sets the frequency divisor of a stream source that is bound to a vertex buffer.


### -field pfnSetConvolutionKernelMono

A pointer to the driver <a href="https://msdn.microsoft.com/b560352f-ca4e-4f03-88ac-13ec080834aa">SetConvolutionKernelMono</a> function that sets the monochrome convolution kernel.


### -field pfnComposeRects

A pointer to the driver <a href="https://msdn.microsoft.com/b6a6b549-7590-4b27-b759-631fa62a76d2">ComposeRects</a> function that composes rectangular areas.


### -field pfnBlt

A pointer to the driver <a href="https://msdn.microsoft.com/e87576c6-0173-4d8e-bbaf-b82e2907140a">Blt</a> function that copies the contents of a source surface to a destination surface.


### -field pfnColorFill

A pointer to the driver <a href="https://msdn.microsoft.com/c120421d-6a10-4d37-b936-98dac75e236b">ColorFill</a> function that fills a rectangular area on a surface with a particular A8R8G8B8 color.


### -field pfnDepthFill

A pointer to the driver <a href="https://msdn.microsoft.com/fc889cc0-d71d-4a81-8fa5-894c676ac110">DepthFill</a> function that fills a depth buffer with a pixel value that is specified in native format.


### -field pfnCreateQuery

A pointer to the driver <a href="https://msdn.microsoft.com/ac63b77b-2704-4d5b-bf1d-9d85e8a1e336">CreateQuery</a> function that creates driver-side resources for a query that the Direct3D runtime subsequently issues for processing.


### -field pfnDestroyQuery

A pointer to the driver <a href="https://msdn.microsoft.com/c4cef278-1771-4903-a5cf-85674463aff8">DestroyQuery</a> function that releases resources for the query that the <a href="https://msdn.microsoft.com/ac63b77b-2704-4d5b-bf1d-9d85e8a1e336">CreateQuery</a> function created.


### -field pfnIssueQuery

A pointer to the driver <a href="https://msdn.microsoft.com/e31b2b6a-3721-472a-8044-6516a8419ad3">IssueQuery</a> function that processes the query that the <a href="https://msdn.microsoft.com/ac63b77b-2704-4d5b-bf1d-9d85e8a1e336">CreateQuery</a> function created.


### -field pfnGetQueryData

A pointer to the driver <a href="https://msdn.microsoft.com/64daec14-8e16-4df3-bb0c-27760223b86c">GetQueryData</a> function that retrieves information about a query.


### -field pfnSetRenderTarget

A pointer to the driver <a href="https://msdn.microsoft.com/067378bd-a2d8-4c83-9436-531519eadaa3">SetRenderTarget</a> function that sets the render target surface in the driver's context.


### -field pfnSetDepthStencil

A pointer to the driver <a href="https://msdn.microsoft.com/7c4b01c8-2376-4956-9b18-649647c19b2b">SetDepthStencil</a> function that sets the depth buffer in the driver's context.


### -field pfnGenerateMipSubLevels

A pointer to the driver <a href="https://msdn.microsoft.com/86567fc1-cf66-4709-a6e1-6b24408df963">GenerateMipSubLevels</a> function that regenerates the sublevels of a MIP-map texture.


### -field pfnSetPixelShaderConstI

A pointer to the driver <a href="https://msdn.microsoft.com/fafc046e-0595-4901-bfb1-70bd980388bc">SetPixelShaderConstI</a> function that sets one or more pixel shader constant registers with integer values.


### -field pfnSetPixelShaderConstB

A pointer to the driver <a href="https://msdn.microsoft.com/6f7c8932-9332-4ff2-89ab-2f9a66783326">SetPixelShaderConstB</a> function that sets one or more pixel shader constant registers with Boolean values.


### -field pfnCreatePixelShader

A pointer to the driver <a href="https://msdn.microsoft.com/b80a1823-6d91-440f-89e4-f7248579cc8f">CreatePixelShader</a> function that converts the pixel shader code into a hardware-specific format and associates this code with a shader handle.


### -field pfnDeletePixelShader

A pointer to the driver <a href="https://msdn.microsoft.com/bc987531-d402-4f3b-a4e2-d71fe97f5400">DeletePixelShader</a> function that cleans up driver-side resources that are associated with pixel shader code.


### -field pfnCreateDecodeDevice

A pointer to the driver <a href="https://msdn.microsoft.com/4d9a062a-2fdf-4e55-a335-c03c5d5665ff">CreateDecodeDevice</a> function that creates a representation of a Microsoft DirectX Video Acceleration (VA) decode device from supplied parameters.


### -field pfnDestroyDecodeDevice

A pointer to the driver <a href="https://msdn.microsoft.com/3685e58b-8d67-4b01-a8a0-8a794d653637">DestroyDecodeDevice</a> function that releases resources for a DirectX VA decode device.


### -field pfnSetDecodeRenderTarget

A pointer to the driver <a href="https://msdn.microsoft.com/d522b0f3-ca9c-4e79-96ad-ea9477858ef4">SetDecodeRenderTarget</a> function that sets the render target for decoding. <i>SetDecodeRenderTarget</i> can be called only outside of a <a href="https://msdn.microsoft.com/3e6153aa-7b21-429d-8908-1ff3a4d25e17">DecodeBeginFrame</a>/<a href="https://msdn.microsoft.com/6e8d3280-6ddc-4593-9208-c4f0c9ff254c">DecodeEndFrame</a> block.


### -field pfnDecodeBeginFrame

A pointer to the driver <a href="https://msdn.microsoft.com/3e6153aa-7b21-429d-8908-1ff3a4d25e17">DecodeBeginFrame</a> function that indicates that decoding of a frame can begin.


### -field pfnDecodeEndFrame

A pointer to the driver <a href="https://msdn.microsoft.com/6e8d3280-6ddc-4593-9208-c4f0c9ff254c">DecodeEndFrame</a> function that indicates that frame decoding operations must be completed.


### -field pfnDecodeExecute

A pointer to the driver <a href="https://msdn.microsoft.com/e12496c0-e3e4-437e-9f84-a30ee99b4541">DecodeExecute</a> function that performs a DirectX VA decode operation. <i>DecodeExecute</i> must be called inside a <a href="https://msdn.microsoft.com/3e6153aa-7b21-429d-8908-1ff3a4d25e17">DecodeBeginFrame</a>/<a href="https://msdn.microsoft.com/6e8d3280-6ddc-4593-9208-c4f0c9ff254c">DecodeEndFrame</a> block.


### -field pfnDecodeExtensionExecute

A pointer to the driver <a href="https://msdn.microsoft.com/522a552a-4588-4dd1-b81f-73ccd4a1c0aa">DecodeExtensionExecute</a> function that performs a nonstandard DirectX VA decode operation. <i>DecodeExtensionExecute</i> must be called inside a <a href="https://msdn.microsoft.com/3e6153aa-7b21-429d-8908-1ff3a4d25e17">DecodeBeginFrame</a>/<a href="https://msdn.microsoft.com/6e8d3280-6ddc-4593-9208-c4f0c9ff254c">DecodeEndFrame</a> block.


### -field pfnCreateVideoProcessDevice

A pointer to the driver <a href="https://msdn.microsoft.com/3149c7d9-0bf7-4355-8f15-821cf6b92f0a">CreateVideoProcessDevice</a> function that creates a representation of a DirectX VA video processing device from supplied parameters.


### -field pfnDestroyVideoProcessDevice

A pointer to the driver <a href="https://msdn.microsoft.com/dc0f8dba-afdd-47f4-ba7f-72c510e80052">DestroyVideoProcessDevice</a> function that releases resources for a DirectX VA video processing device.


### -field pfnVideoProcessBeginFrame

A pointer to the driver <a href="https://msdn.microsoft.com/1b7b1774-3144-4929-83d8-c52a7de6936d">VideoProcessBeginFrame</a> function that indicates that video processing of a frame can begin.


### -field pfnVideoProcessEndFrame

A pointer to the driver <a href="https://msdn.microsoft.com/a5be6834-bb27-4da0-8802-25a9ca58c101">VideoProcessEndFrame</a> function that indicates that video processing operations must be completed.


### -field pfnSetVideoProcessRenderTarget

A pointer to the driver <a href="https://msdn.microsoft.com/8aa7e23e-f52e-4252-9f22-56ce523f6cba">SetVideoProcessRenderTarget</a> function that sets the render target for video processing. <i>SetVideoProcessRenderTarget</i> can be called only outside of a <a href="https://msdn.microsoft.com/1b7b1774-3144-4929-83d8-c52a7de6936d">VideoProcessBeginFrame</a>/<a href="https://msdn.microsoft.com/a5be6834-bb27-4da0-8802-25a9ca58c101">VideoProcessEndFrame</a> block.


### -field pfnVideoProcessBlt

A pointer to the driver <a href="https://msdn.microsoft.com/719465dd-4547-491c-ab30-ae63bba1b72c">VideoProcessBlt</a> function that processes DirectX VA video. <i>VideoProcessBlt</i> must be called inside a <a href="https://msdn.microsoft.com/1b7b1774-3144-4929-83d8-c52a7de6936d">VideoProcessBeginFrame</a>/<a href="https://msdn.microsoft.com/a5be6834-bb27-4da0-8802-25a9ca58c101">VideoProcessEndFrame</a> block.


### -field pfnCreateExtensionDevice

A pointer to the driver <a href="https://msdn.microsoft.com/7e6dbb70-2e74-4ddb-a504-2c8145af99d9">CreateExtensionDevice</a> function that creates a representation of a DirectX VA extension device from supplied parameters.


### -field pfnDestroyExtensionDevice

A pointer to the driver <a href="https://msdn.microsoft.com/8c4bcab3-b903-4f39-aab0-7efb3b18d068">DestroyExtensionDevice</a> function that releases resources for a DirectX VA extension device.


### -field pfnExtensionExecute

A pointer to the driver <a href="https://msdn.microsoft.com/a3f73651-bfff-48fa-aa61-477b8af7fa07">ExtensionExecute</a> function that performs an operation that is specific to the given DirectX VA extension device.


### -field pfnCreateOverlay

A pointer to the driver <a href="https://msdn.microsoft.com/761377ff-95a6-426b-8372-3f347870f9c4">CreateOverlay</a> function that allocates overlay hardware and makes the overlay visible.


### -field pfnUpdateOverlay

A pointer to the driver <a href="https://msdn.microsoft.com/80d7cc5c-51d8-4b91-9581-b073f9b0e68a">UpdateOverlay</a> function that reconfigures or moves an overlay that is being displayed.


### -field pfnFlipOverlay

A pointer to the driver <a href="https://msdn.microsoft.com/8490ebdd-f993-4c77-b6da-d57ef5e5d05f">FlipOverlay</a> function that causes the overlay hardware to start displaying the new allocation.


### -field pfnGetOverlayColorControls

A pointer to the driver <a href="https://msdn.microsoft.com/23b15bb5-4394-406b-8869-f9d1e4e2b539">GetOverlayColorControls</a> function that retrieves color-control settings for an overlay.


### -field pfnSetOverlayColorControls

A pointer to the driver <a href="https://msdn.microsoft.com/c2723c57-44eb-4866-9381-a3a341996989">SetOverlayColorControls</a> function that changes color-control settings for an overlay.


### -field pfnDestroyOverlay

A pointer to the driver <a href="https://msdn.microsoft.com/63004d19-e2cd-462c-8fa5-ea4dd6e29735">DestroyOverlay</a> function that disables the overlay hardware and frees the overlay handle.


### -field pfnDestroyDevice

A pointer to the driver <a href="https://msdn.microsoft.com/a3c158c2-6c0d-4da0-80f4-569971b10673">DestroyDevice</a> function that releases resources for the display device.


### -field pfnQueryResourceResidency

A pointer to the driver <a href="https://msdn.microsoft.com/5b9a2a59-b2d1-468e-998b-902bc2a75cb3">QueryResourceResidency</a> function that determines the residency of resources.


### -field pfnOpenResource

A pointer to the driver <a href="https://msdn.microsoft.com/e3f5cec2-391b-40f9-8a4b-afe6b8de2954">OpenResource</a> function that informs the driver that a shared resource is opened.


### -field pfnGetCaptureAllocationHandle

A pointer to the driver <a href="https://msdn.microsoft.com/fb12a12b-6fb7-46d4-aa71-4c88d34d6ff9">GetCaptureAllocationHandle</a> function that maps the given capture resource to an allocation.


### -field pfnCaptureToSysMem

A pointer to the driver <a href="https://msdn.microsoft.com/ea2b5338-81cf-4114-bb07-16e8ff4d2b95">CaptureToSysMem</a> function that copies a capture buffer to a video memory surface.


### -field pfnLockAsync

A pointer to the driver <a href="https://msdn.microsoft.com/c8f76ebe-947a-45e4-abbc-f6020da929e8">LockAsync</a> function that locks a resource or a surface within the resource.


### -field pfnUnlockAsync

A pointer to the driver <a href="https://msdn.microsoft.com/6af04c22-e559-4328-a20a-034b443fddc6">UnlockAsync</a> function that unlocks a resource or a surface within the resource that the <a href="https://msdn.microsoft.com/c8f76ebe-947a-45e4-abbc-f6020da929e8">LockAsync</a> function previously locked.


### -field pfnRename

A pointer to the driver <a href="https://msdn.microsoft.com/60f733e1-d376-4372-b1cc-39508b3a98e5">Rename</a> function that renames, with a new allocation, a resource or a surface within the resource.


### -field pfnCreateVideoProcessor

A pointer to the driver <a href="https://msdn.microsoft.com/68a7c394-4b0f-4446-a54b-5aee6cf8a913">CreateVideoProcessor</a> function that creates a video processor.


### -field pfnSetVideoProcessBltState

A pointer to the driver <a href="https://msdn.microsoft.com/6796372c-279d-427c-a2a4-9b7c99494f53">SetVideoProcessBltState</a> function that sets the state of a bitblt for a video processor. 


### -field pfnGetVideoProcessBltStatePrivate

A pointer to the driver <a href="https://msdn.microsoft.com/bb4c04cf-0125-47bf-8fc8-88d807e7b6ad">GetVideoProcessBltStatePrivate</a> function that retrieves the state data of a private bitblt for a video processor. 


### -field pfnSetVideoProcessStreamState

A pointer to the driver <a href="https://msdn.microsoft.com/b48fbe58-056a-4c3b-8e1e-c65515c21ee4">SetVideoProcessStreamState</a> function that sets the state of a stream for a video processor. 


### -field pfnGetVideoProcessStreamStatePrivate

A pointer to the driver <a href="https://msdn.microsoft.com/0503b382-8ed3-461e-906f-27953ac5f757">GetVideoProcessStreamStatePrivate</a> function that retrieves the private stream-state data for a video processor. 


### -field pfnVideoProcessBltHD

A pointer to the driver <a href="https://msdn.microsoft.com/62451fc4-92cc-4553-80cc-0843cf734a62">VideoProcessBltHD</a> function that processes video input streams and composes to an output surface. 


### -field pfnDestroyVideoProcessor

A pointer to the driver <a href="https://msdn.microsoft.com/library/windows/hardware/hh451638">DestroyVideoProcessor</a> function that releases resources for a previously created video processor. 


### -field pfnCreateAuthenticatedChannel

A pointer to the driver <a href="https://msdn.microsoft.com/0a565bff-fc6f-41c1-a6fd-3a82dd0d7889">CreateAuthenticatedChannel</a> function that creates a channel that the Direct3D runtime and the driver can use to set and query protections. 


### -field pfnAuthenticatedChannelKeyExchange

A pointer to the driver <a href="https://msdn.microsoft.com/627f9689-1059-4f88-9005-9c7600dad686">AuthenticatedChannelKeyExchange</a> function that negotiates the session key. 


### -field pfnQueryAuthenticatedChannel

A pointer to the driver <a href="https://msdn.microsoft.com/13b65b5a-9512-4d67-b629-479bdd74674e">QueryAuthenticatedChannel</a> function that queries an authenticated channel for capability and state information. 


### -field pfnConfigureAuthenticatedChannel

A pointer to the driver <a href="https://msdn.microsoft.com/95485e96-fa4f-4c88-b88b-97b79f507abd">ConfigureAuthenticatedChannel</a> function that sets the state within an authenticated channel. 


### -field pfnDestroyAuthenticatedChannel

A pointer to the driver <a href="https://msdn.microsoft.com/library/windows/hardware/hh451630">DestroyAuthenticatedChannel</a> function that releases resources for an authenticated channel. 


### -field pfnCreateCryptoSession

A pointer to the driver <a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a> function that creates an encryption session. 


### -field pfnCryptoSessionKeyExchange

A pointer to the driver <a href="https://msdn.microsoft.com/f8055bb3-b8f1-47f5-9ae0-8e7a26989871">CryptoSessionKeyExchange</a> function that performs a key exchange during an encryption session. 


### -field pfnDestroyCryptoSession

A pointer to the driver <a href="https://msdn.microsoft.com/library/windows/hardware/hh451632">DestroyCryptoSession</a> function that releases resources for an encryption session. 


### -field pfnEncryptionBlt

A pointer to the driver <a href="https://msdn.microsoft.com/a92bfff7-8af6-48c3-9e7f-95b9426aaaf2">EncryptionBlt</a> function that performs an encrypted bitblt operation. 


### -field pfnGetPitch

A pointer to the driver <a href="https://msdn.microsoft.com/1a5721a3-c03f-4827-9626-c9b6af5059a1">GetPitch</a> function that retrieves the pitch of an encrypted surface. 


### -field pfnStartSessionKeyRefresh

A pointer to the driver <a href="https://msdn.microsoft.com/library/windows/hardware/hh451696">StartSessionKeyRefresh</a> function that sets the current video session to protected mode. 


### -field pfnFinishSessionKeyRefresh

A pointer to the driver <a href="https://msdn.microsoft.com/library/windows/hardware/hh451648">FinishSessionKeyRefresh</a> function that sets the current video session to unprotected mode. 


### -field pfnGetEncryptionBltKey

A pointer to the driver <a href="https://msdn.microsoft.com/library/windows/hardware/hh451660">GetEncryptionBltKey</a> function that retrieves the key of an encrypted bitblt session. 


### -field pfnDecryptionBlt

A pointer to the driver <a href="https://msdn.microsoft.com/1bfe2b9c-90f6-48bf-b0b3-30788ef94110">DecryptionBlt</a> function that writes data to a protected surface. 


### -field pfnResolveSharedResource

A pointer to the driver <a href="https://msdn.microsoft.com/8ad9130e-bade-4fd2-b345-b6361fd001ef">ResolveSharedResource</a> function that resolves a shared resource. 


### -field pfnVolBlt1

A pointer to the driver <a href="https://msdn.microsoft.com/81B9AB74-9CD1-4181-BE13-32D519069FD4">VolBlt1</a> function that performs a volume bit-block transfer (bitblt) operation.

Supported starting with Windows 8.


### -field pfnBufBlt1

A pointer to the driver <a href="https://msdn.microsoft.com/92F2AED7-935F-4E3E-934F-D6DF9AA87495">BufBlt1</a> function that performs a bit-block transfer (bitblt) operation.

Supported starting with Windows 8.


### -field pfnTexBlt1

A pointer to the driver <a href="https://msdn.microsoft.com/63EE8130-47E5-4976-8A72-1B11136B1192">TexBlt1</a> function that performs a texture bit-block transfer (bitblt) operation.

Supported starting with Windows 8.


### -field pfnDiscard

A pointer to the driver <a href="https://msdn.microsoft.com/F3EC7AAE-9DB8-43A1-B756-5F5C91F8372E">Discard</a>  function that discards (evicts) a set of subresources from video display memory.

Supported starting with Windows 8.


### -field pfnOfferResources

A pointer to the driver  <a href="https://msdn.microsoft.com/68551AD7-AC0C-4138-948F-33773F02DA41">OfferResources</a> function that requests that the user-mode display driver offer video memory resources for reuse.

Supported starting with Windows 8.


### -field pfnReclaimResources

A pointer to the driver <a href="https://msdn.microsoft.com/F0533DBB-CB18-4556-9871-2DF4CA719172">ReclaimResources</a> function that's called by the Direct3D runtime to reclaim video memory resources that it previously offered for reuse.

Supported starting with Windows 8.


### -field pfnCheckDirectFlipSupport

A pointer to the driver <a href="https://msdn.microsoft.com/BB909041-0194-4828-ACA2-E3F6B1974DBB">CheckDirectFlipSupport</a> function that's called by the DWM to verify that the user-mode driver supports Direct Flip operations.

Supported starting with Windows 8.


### -field pfnCreateResource2

A pointer to the driver <a href="https://msdn.microsoft.com/a8326707-cffc-4a20-ad3d-c7862661f513">CreateResource2</a> function that creates a resource.

Supported starting with Windows 8.


### -field pfnCheckMultiPlaneOverlaySupport

A pointer to the driver <a href="https://msdn.microsoft.com/A439E695-D374-439A-8A69-6D4E247FF134">pfnCheckMultiPlaneOverlaySupport (D3D)</a> function that's called by the Direct3D runtime to check the details on hardware support for multiplane overlays.

Supported starting with Windows 8.1.


### -field pfnPresentMultiPlaneOverlay

A pointer to the driver <a href="https://msdn.microsoft.com/3AC47977-A5F3-44A6-8F89-A1EA5E0BB6E4">pfnPresentMultiplaneOverlay (D3D)</a> function that's called by the Direct3D runtime to notify the user-mode display driver that an application finished rendering and requests that the driver display the source surface by either copying or flipping or that the driver perform a color-fill operation.

Supported starting with Windows 8.1.


### -field pfnReserved1

Reserved for system use. Do not use in your driver.

Supported starting with Windows 8.1.


### -field pfnFlush1

A pointer to the driver <a href="https://msdn.microsoft.com/6BAC104A-85CE-42FC-AE30-969B2FF6AFEF">pfnFlush1</a>  function that's called by the Direct3D runtime to submit outstanding hardware commands that are in the hardware command buffer to the display miniport driver.

Supported starting with Windows 8.1.


### -field pfnCheckCounterInfo

A pointer to the driver <a href="https://msdn.microsoft.com/98B8EE79-18D2-4C57-964B-74DB550C1330">pfnCheckCounterInfo</a>  function that's called by the Direct3D runtime to determine global information that's related to manipulating counters.

Supported starting with Windows 8.1.


### -field pfnCheckCounter

A pointer to the driver <a href="https://msdn.microsoft.com/3A8B040D-7B48-4CDB-985B-906AE1762E22">pfnCheckCounter</a>  function that's called by the Direct3D runtime to retrieve info that describes a counter.

Supported starting with Windows 8.1.


### -field pfnUpdateSubresourceUP

A pointer to the driver <a href="https://msdn.microsoft.com/5AF55FED-6FD6-41BE-A743-1E9D0EA51C9C">pfnUpdateSubresourceUP</a>  function that's called by the Direct3D runtime to update a destination subresource region from a source system-memory region.

Supported starting with Windows 8.1.


### -field pfnPresent1

A pointer to the driver <a href="https://msdn.microsoft.com/8BB8E85F-B081-422E-ACE1-C2312BA28B9F">pfnPresent1(D3D)</a>  function that notifies the user-mode display driver that an application finished rendering and  that all ownership of the shared resource is released, and that  requests that the driver display to the destination surface.

Supported starting with Windows 8.1.


### -field pfnCheckPresentDurationSupport

A pointer to the driver <a href="https://msdn.microsoft.com/4D3FC503-A502-41D3-AB76-5A2BEBE4C551">CheckPresentDurationSupport</a> function that's called by the Direct3D runtime to request that the user-mode display driver get hardware device capabilities for seamlessly switching to a new monitor refresh rate.

Supported starting with Windows 8.1.


### -field pfnSetMarker

A pointer to the driver <a href="https://msdn.microsoft.com/6D4DB988-D339-4B2F-A9B8-41B4FD21FE66">pfnSetMarker</a> function that notifies the user-mode display driver that it must generate a new time stamp if any GPU work has completed since the last call to <i>pfnSetMarker</i>.

Supported starting with Windows 8.1.


### -field pfnSetMarkerMode

A pointer to the driver <a href="https://msdn.microsoft.com/D45750D9-F722-4208-8D00-E14FD9C009CB">pfnSetMarkerMode</a> function that notifies the user-mode display driver that it should support a type of Event Tracing for Windows (ETW) marker event.

Supported starting with Windows 8.1.


### -field pfnTrimResidencySet

 


### -field pfnAcquireResource

 


### -field pfnReleaseResource

 




## -remarks



The following code, from D3dumddi.h, shows the function declarations for the functions that the members of <b>D3DDDI_DEVICEFUNCS</b> point to. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETRENDERSTATE)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_RENDERSTATE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_UPDATEWINFO)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_WINFO*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_VALIDATEDEVICE)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_VALIDATETEXTURESTAGESTATE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETTEXTURESTAGESTATE)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_TEXTURESTAGESTATE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETTEXTURE)(
        _In_ HANDLE hDevice, _In_ UINT, _In_ HANDLE);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETPIXELSHADER)(
        _In_ HANDLE hDevice, _In_ HANDLE);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETPIXELSHADERCONST)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETPIXELSHADERCONST*, _In_ CONST FLOAT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETSTREAMSOURCEUM)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETSTREAMSOURCEUM*, _In_ CONST VOID*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETINDICES)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETINDICES*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETINDICESUM)(
        _In_ HANDLE hDevice, _In_ UINT, _In_ CONST VOID*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DRAWPRIMITIVE)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_DRAWPRIMITIVE*, _In_opt_ CONST UINT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DRAWINDEXEDPRIMITIVE)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_DRAWINDEXEDPRIMITIVE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DRAWRECTPATCH)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_DRAWRECTPATCH*, _In_ CONST D3DDDIRECTPATCH_INFO*, _In_ CONST FLOAT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DRAWTRIPATCH)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_DRAWTRIPATCH*, _In_ CONST D3DDDITRIPATCH_INFO*, _In_ CONST FLOAT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DRAWPRIMITIVE2)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_DRAWPRIMITIVE2*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DRAWINDEXEDPRIMITIVE2)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_DRAWINDEXEDPRIMITIVE2*, _In_ UINT, _In_ CONST VOID*, _In_opt_ CONST UINT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_VOLBLT)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_VOLUMEBLT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_BUFBLT)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_BUFFERBLT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_TEXBLT)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_TEXBLT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_STATESET)(
        _In_ HANDLE hDevice, _In_ D3DDDIARG_STATESET*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETPRIORITY)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETPRIORITY*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CLEAR)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_CLEAR*, _In_ UINT, _In_ CONST RECT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_UPDATEPALETTE)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_UPDATEPALETTE*, _In_ CONST PALETTEENTRY*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETPALETTE)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETPALETTE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETVERTEXSHADERCONST)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETVERTEXSHADERCONST*, _In_ CONST VOID*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_MULTIPLYTRANSFORM)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_MULTIPLYTRANSFORM*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETTRANSFORM)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETTRANSFORM*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETVIEWPORT)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_VIEWPORTINFO*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETZRANGE)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_ZRANGE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETMATERIAL)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETMATERIAL*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETLIGHT)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETLIGHT*, _In_ CONST D3DDDI_LIGHT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CREATELIGHT)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_CREATELIGHT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DESTROYLIGHT)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_DESTROYLIGHT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETCLIPPLANE)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETCLIPPLANE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_GETINFO)(
        _In_ HANDLE hDevice, _In_ UINT, _Out_writes_bytes_(DevInfoSize)VOID*, _In_ UINT DevInfoSize);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_LOCK)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_LOCK*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_UNLOCK)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_UNLOCK*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_LOCKASYNC)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_LOCKASYNC*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_UNLOCKASYNC)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_UNLOCKASYNC*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_RENAME)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_RENAME*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CREATERESOURCE)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CREATERESOURCE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DESTROYRESOURCE)(
        _In_ HANDLE hDevice, _In_ HANDLE);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETDISPLAYMODE)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETDISPLAYMODE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_PRESENT)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_PRESENT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_FLUSH)(
        _In_ HANDLE hDevice);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CREATEVERTEXSHADERDECL)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CREATEVERTEXSHADERDECL*, _In_ CONST D3DDDIVERTEXELEMENT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETVERTEXSHADERDECL)(
        _In_ HANDLE hDevice, _In_ HANDLE);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DELETEVERTEXSHADERDECL)(
        _In_ HANDLE hDevice, _In_ HANDLE);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CREATEVERTEXSHADERFUNC)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CREATEVERTEXSHADERFUNC*, _In_ CONST UINT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETVERTEXSHADERFUNC)(
        _In_ HANDLE hDevice, _In_ HANDLE);
typedef _In_ HRESULT (APIENTRY *PFND3DDDI_DELETEVERTEXSHADERFUNC)(
        _In_ HANDLE hDevice, _In_ HANDLE);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETVERTEXSHADERCONSTI)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETVERTEXSHADERCONSTI*, _In_ CONST INT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETVERTEXSHADERCONSTB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETVERTEXSHADERCONSTB*, _In_ CONST BOOL*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETSCISSORRECT)(
        _In_ HANDLE hDevice, _In_ CONST RECT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETSTREAMSOURCE)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETSTREAMSOURCE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETSTREAMSOURCEFREQ)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETSTREAMSOURCEFREQ*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETCONVOLUTIONKERNELMONO)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETCONVOLUTIONKERNELMONO*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_COMPOSERECTS)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_COMPOSERECTS*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_BLT)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_BLT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_COLORFILL)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_COLORFILL*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DEPTHFILL)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_DEPTHFILL*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CREATEQUERY)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CREATEQUERY*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DESTROYQUERY)(
        _In_ HANDLE hDevice, _In_ CONST HANDLE);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_ISSUEQUERY)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_ISSUEQUERY*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_GETQUERYDATA)(
        _In_ HANDLE hDevice, _Inout_ CONST D3DDDIARG_GETQUERYDATA*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETRENDERTARGET)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETRENDERTARGET*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETDEPTHSTENCIL)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETDEPTHSTENCIL*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_GENERATEMIPSUBLEVELS)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_GENERATEMIPSUBLEVELS*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETPIXELSHADERCONSTI)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETPIXELSHADERCONSTI*, _In_ CONST INT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETPIXELSHADERCONSTB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETPIXELSHADERCONSTB*, _In_ CONST BOOL*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CREATEPIXELSHADER)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CREATEPIXELSHADER*, _In_ CONST UINT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DELETEPIXELSHADER)(
        _In_ HANDLE hDevice, _In_ HANDLE);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CREATEDECODEDEVICE)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CREATEDECODEDEVICE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DESTROYDECODEDEVICE)(
        _In_ HANDLE hDevice, _In_ HANDLE);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETDECODERENDERTARGET) (
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETDECODERENDERTARGET*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DECODEBEGINFRAME) (
        _In_ HANDLE hDevice, _In_ D3DDDIARG_DECODEBEGINFRAME*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DECODEENDFRAME) (
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_DECODEENDFRAME*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DECODEEXECUTE)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_DECODEEXECUTE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DECODEEXTENSIONEXECUTE)(
        _In_ HANDLE hDevice, _Inout_ CONST D3DDDIARG_DECODEEXTENSIONEXECUTE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CREATEVIDEOPROCESSDEVICE) (
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CREATEVIDEOPROCESSDEVICE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DESTROYVIDEOPROCESSDEVICE) (
        _In_ HANDLE hDevice, _In_ HANDLE hVideoProcessor);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_VIDEOPROCESSBEGINFRAME) (
        _In_ HANDLE hDevice, _In_ HANDLE hVideoProcess);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_VIDEOPROCESSENDFRAME) (
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_VIDEOPROCESSENDFRAME*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETVIDEOPROCESSRENDERTARGET) (
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETVIDEOPROCESSRENDERTARGET*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_VIDEOPROCESSBLT) (
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_VIDEOPROCESSBLT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CREATEEXTENSIONDEVICE) (
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CREATEEXTENSIONDEVICE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DESTROYEXTENSIONDEVICE) (
        _In_ HANDLE hDevice, _In_ HANDLE hExtension);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_EXTENSIONEXECUTE) (
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_EXTENSIONEXECUTE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DESTROYDEVICE)(
        _In_ HANDLE hDevice);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CREATEOVERLAY) (
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CREATEOVERLAY*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_UPDATEOVERLAY) (
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_UPDATEOVERLAY*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_FLIPOVERLAY) (
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_FLIPOVERLAY*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_GETOVERLAYCOLORCONTROLS) (
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_GETOVERLAYCOLORCONTROLS*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETOVERLAYCOLORCONTROLS) (
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETOVERLAYCOLORCONTROLS*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DESTROYOVERLAY) (
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_DESTROYOVERLAY*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_QUERYRESOURCERESIDENCY) (
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_QUERYRESOURCERESIDENCY*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_OPENRESOURCE) (
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_OPENRESOURCE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_GETCAPTUREALLOCATIONHANDLE)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_GETCAPTUREALLOCATIONHANDLE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CAPTURETOSYSMEM)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_CAPTURETOSYSMEM*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DXVAHD_CREATEVIDEOPROCESSOR)(
        _In_ HANDLE, _Inout_ D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DXVAHD_SETVIDEOPROCESSBLTSTATE)(
        _In_ HANDLE, _In_ CONST D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE)(
        _In_ HANDLE, _Inout_ D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DXVAHD_SETVIDEOPROCESSSTREAMSTATE)(
        _In_ HANDLE, _In_ CONST D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE)(
        _In_ HANDLE, _Inout_ D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DXVAHD_VIDEOPROCESSBLTHD)(
        _In_ HANDLE, _In_ CONST D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DXVAHD_DESTROYVIDEOPROCESSOR)(
        _In_ HANDLE, _In_ HANDLE);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CREATEAUTHENTICATEDCHANNEL)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CREATEAUTHENTICATEDCHANNEL*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_AUTHENTICATEDCHANNELKEYEXCHANGE)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_QUERYAUTHENTICATEDCHANNEL)(
        _In_ HANDLE hDevice, _Inout_ CONST D3DDDIARG_QUERYAUTHENTICATEDCHANNEL*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CONFIGUREAUTHENICATEDCHANNEL)(
        _In_ HANDLE hDevice, _Inout_ CONST D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DESTROYAUTHENTICATEDCHANNEL)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CREATECRYPTOSESSION)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CREATECRYPTOSESSION*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CRYPTOSESSIONKEYEXCHANGE)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DESTROYCRYPTOSESSION)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_DESTROYCRYPTOSESSION*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_ENCRYPTIONBLT)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_ENCRYPTIONBLT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_GETPITCH)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_GETPITCH*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_STARTSESSIONKEYREFRESH)(
        _In_ HANDLE hDevice, _Inout_ CONST D3DDDIARG_STARTSESSIONKEYREFRESH*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_FINISHSESSIONKEYREFRESH)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_FINISHSESSIONKEYREFRESH*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_GETENCRYPTIONBLTKEY)(
        _In_ HANDLE hDevice, _Inout_ CONST D3DDDIARG_GETENCRYPTIONBLTKEY*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DECRYPTIONBLT)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_DECRYPTIONBLT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_RESOLVESHAREDRESOURCE)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_RESOLVESHAREDRESOURCE*);
#if (D3D_UMD_INTERFACE_VERSION &gt;= D3D_UMD_INTERFACE_VERSION_WIN8)
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_VOLBLT1)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_VOLUMEBLT1*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_BUFBLT1)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_BUFFERBLT1*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_TEXBLT1)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_TEXBLT1*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DISCARD)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_DISCARD*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_OFFERRESOURCES)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_OFFERRESOURCES*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_RECLAIMRESOURCES)(
        _In_ HANDLE hDevice, _Inout_ CONST D3DDDIARG_RECLAIMRESOURCES*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CHECKDIRECTFLIPSUPPORT)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CHECKDIRECTFLIPSUPPORT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CREATERESOURCE2)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CREATERESOURCE2*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CHECKMULTIPLANEOVERLAYSUPPORT)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CHECKMULTIPLANEOVERLAYSUPPORT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_PRESENTMULTIPLANEOVERLAY)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_PRESENTMULTIPLANEOVERLAY*);
#if (D3D_UMD_INTERFACE_VERSION &gt;= D3D_UMD_INTERFACE_VERSION_WDDM1_3)
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_FLUSH1)(
        _In_ HANDLE hDevice, UINT /*D3DDDI_FLUSH_FLAGS*/ FlushFlags);
typedef VOID ( APIENTRY* PFND3DDDI_CHECKCOUNTERINFO )(
        _In_ HANDLE hDevice, _Out_ D3DDDIARG_COUNTER_INFO* );
typedef _Check_return_ HRESULT ( APIENTRY* PFND3DDDI_CHECKCOUNTER )(
        _In_ HANDLE hDevice, _In_ D3DDDIQUERYTYPE, _Out_ D3DDDI_COUNTER_TYPE*, _Out_ UINT*,
        _Out_writes_to_opt_(*pNameLength, *pNameLength) LPSTR,
        _Inout_opt_ UINT* pNameLength,
        _Out_writes_to_opt_(*pUnitsLength, *pUnitsLength) LPSTR,
        _Inout_opt_ UINT* pUnitsLength,
        _Out_writes_to_opt_(*pDescriptionLength, *pDescriptionLength) LPSTR,
        _Inout_opt_ UINT* pDescriptionLength);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_UPDATESUBRESOURCEUP)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_UPDATESUBRESOURCEUP*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_PRESENT1)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_PRESENT1*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CHECKPRESENTDURATIONSUPPORT)(
        _In_ HANDLE hDevice, _In_ D3DDDIARG_CHECKPRESENTDURATIONSUPPORT*);
#endif // D3D_UMD_INTERFACE_VERSION
#if (D3D_UMD_INTERFACE_VERSION &gt;= D3D_UMD_INTERFACE_VERSION_WDDM1_3)
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETMARKERMODE)(
        _In_ HANDLE hDevice, _In_ D3DDDI_MARKERTYPE Type, /*D3DDDI_SETMARKERMODE*/ UINT Flags );
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETMARKER)(
        _In_ HANDLE hDevice);
#endif // D3D_UMD_INTERFACE_VERSION</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/ce35bdac-af90-471f-af93-0e665be6c7f6">CreateDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542931">D3DDDIARG_CREATEDEVICE</a>
 

 

