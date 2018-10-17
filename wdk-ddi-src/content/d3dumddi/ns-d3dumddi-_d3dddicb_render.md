---
UID: NS:d3dumddi._D3DDDICB_RENDER
title: "_D3DDDICB_RENDER"
author: windows-driver-content
description: The D3DDDICB_RENDER structure describes the current command buffer to be rendered.
old-location: display\d3dddicb_render.htm
tech.root: display
ms.assetid: 7a2bf1a8-d416-46bc-a9ba-9122407ea2a2
ms.date: 5/10/2018
ms.keywords: D3DDDICB_RENDER, D3DDDICB_RENDER structure [Display Devices], D3D_param_Structs_62df043b-dbd7-4faf-a911-683ab12ba79b.xml, _D3DDDICB_RENDER, d3dumddi/D3DDDICB_RENDER, display.d3dddicb_render
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
-	D3DDDICB_RENDER
product:
- Windows
targetos: Windows
req.typenames: D3DDDICB_RENDER
---

# _D3DDDICB_RENDER structure


## -description


The D3DDDICB_RENDER structure describes the current command buffer to be rendered.


## -struct-fields




### -field CommandLength

[in] The size, in bytes, of the command buffer, starting from offset zero.


### -field CommandOffset

[in] The offset, in bytes, to the first command in the command buffer.


### -field NumAllocations

[in] The number of elements in the allocation list.


### -field NumPatchLocations

[in] The number of elements in the patch-location list.


### -field pNewCommandBuffer

[out] A pointer to a command buffer that the user-mode display driver receives to use in its next call to the <a href="https://msdn.microsoft.com/f242162e-6237-469c-b178-5a51dcf69e32">pfnRenderCb</a> function.


### -field NewCommandBufferSize

[in/out] The size, in bytes, that the user-mode display driver requests for the next command buffer.

The driver receives the size, in bytes, of the next command buffer to use. 


### -field pNewAllocationList

[out] An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544375">D3DDDI_ALLOCATIONLIST</a> structures that the user-mode display driver receives to use as the allocation list in its next call to the <a href="https://msdn.microsoft.com/f242162e-6237-469c-b178-5a51dcf69e32">pfnRenderCb</a> function.


### -field NewAllocationListSize

[in/out] The number of elements that the user-mode display driver requests for the next allocation list. 

The driver receives the number of elements for the allocation list that will be available when the next command buffer is submitted.


### -field pNewPatchLocationList

[out] An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544630">D3DDDI_PATCHLOCATIONLIST</a> structures that the user-mode display driver receives to use as the patch-location list in its next call to the <a href="https://msdn.microsoft.com/f242162e-6237-469c-b178-5a51dcf69e32">pfnRenderCb</a> function.


### -field NewPatchLocationListSize

[in/out] The number of elements that the user-mode display driver requests for the next patch-location list.

The driver receives the number of elements for the patch-location list that will be available when the next command buffer is submitted. 


### -field Flags

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544247">D3DDDICB_RENDERFLAGS</a> structure that indicates information about a command buffer to be rendered.


### -field hContext

[in] A handle to the context that the driver submits the rendering operation to. The user-mode display driver previously created this context by calling the <a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a> function. 


### -field BroadcastContextCount

[in] The number of additional contexts in the array that the <b>BroadcastContext</b> member specifies.


### -field BroadcastContext

[in] An array of handles to the additional contexts to broadcast the current command buffer to. The D3DDDI_MAX_BROADCAST_CONTEXT constant, which is defined as 64, defines the maximum number of additional contexts that the user-mode display driver can broadcast the current command buffer to.

The original context that the <b>hContext</b> member specifies and that owns the command buffer is not an element in the <b>BroadcastContext</b> array. For example, if the <b>BroadcastContext</b> array contains one element, the user-mode display driver sends the command buffer to the owning context (<b>hContext</b>) and broadcasts to that one additional context. 


### -field QueuedBufferCount

[out] The number of DMA buffers that are queued to the context that the <b>hContext</b> member specifies after the current submission occurs. 


### -field NewCommandBuffer

This member is reserved and should be set to zero.

This member is available beginning with Windows 7.


### -field pPrivateDriverData

[in] This member is reserved and should be set to zero.

This member is available beginning with Windows 7.


### -field PrivateDriverDataSize

[in] This member is reserved and should be set to zero.

This member is available beginning with Windows 7.


### -field MarkerLogType

 


### -field RenderCBSequence

 


### -field FirstAPISequenceNumberHigh

 


### -field CompletedAPISequenceNumberLow0Size

 


### -field CompletedAPISequenceNumberLow1Size

 


### -field BegunAPISequenceNumberLow0Size

 


### -field BegunAPISequenceNumberLow1Size

 


### -field pCompletedAPISequenceNumberLow0

 


### -field pCompletedAPISequenceNumberLow1

 


### -field pBegunAPISequenceNumberLow0

 


### -field pBegunAPISequenceNumberLow1

 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544247">D3DDDICB_RENDERFLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544375">D3DDDI_ALLOCATIONLIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544630">D3DDDI_PATCHLOCATIONLIST</a>



<a href="https://msdn.microsoft.com/f242162e-6237-469c-b178-5a51dcf69e32">pfnRenderCb</a>
 

 

