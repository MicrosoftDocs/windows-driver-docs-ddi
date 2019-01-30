---
UID: NF:d3dkmthk.D3DKMTRender
title: D3DKMTRender function (d3dkmthk.h)
description: The D3DKMTRender function submits the current command buffer to the Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys).
old-location: display\d3dkmtrender.htm
ms.assetid: 8720db3f-aafc-4657-a0cd-3068760855a3
ms.date: 05/10/2018
ms.keywords: D3DKMTRender, D3DKMTRender function [Display Devices], OpenGL_Functions_d24fbe14-3271-47f8-9268-8946b599b32a.xml, d3dkmthk/D3DKMTRender, display.d3dkmtrender
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Gdi32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTRender
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTRender function


## -description


The <b>D3DKMTRender</b> function submits the current command buffer to the Microsoft DirectX graphics kernel subsystem (<i>Dxgkrnl.sys</i>).


## -parameters

### -param Arg1

*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548238">D3DKMT_RENDER</a> structure that describes parameters for submitting the current command buffer to the graphics kernel subsystem.

## -returns

<b>D3DKMTRender</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | The command buffer was successfully submitted. | 
| **STATUS_DEVICE_REMOVED** | The graphics adapter was stopped or the display context was reset. | 
| **STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect. | 
| **STATUS_NO_MEMORY** | [D3DKMTRender](https://msdn.microsoft.com/library/windows/hardware/ff547145)  could not complete because of insufficient memory. | 
| **STATUS_INVALID_HANDLE** | The OpenGL ICD detected an invalid handle in the command buffer. | 
| **STATUS_PRIVILEGED_INSTRUCTION** | [D3DKMTRender](https://msdn.microsoft.com/library/windows/hardware/ff547145) detected nonprivileged instructions (that is, instructions that access memory beyond the privilege of the current CPU process). | 

This function might also return other <b>NTSTATUS</b> values.

## -remarks

A command buffer typically contains many graphics commands.  

If <b>D3DKMTRender</b> returns <b>STATUS_GRAPHICS_ALLOCATION_INVALID</b>, the OpenGL ICD should re-open or re-create the primary handle, replace all references in the command buffer to the previous handle with the new handle, and then call <b>D3DKMTRender</b> again to resubmit the buffer.

After a call to <b>D3DKMTRender</b>, the OpenGL ICD should determine the base address and size of the command buffer that it should use for its next submission from the values that are returned in the <b>pCommandBuffer</b> and <b>CommandBufferSize</b> members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548238">D3DKMT_RENDER</a> structure that is pointed to by the <i>pData</i> parameter.

For a device that uses guaranteed DMA buffer contract mode (for more information about this mode, see <a href="https://msdn.microsoft.com/fee6f7eb-157b-466d-b482-110a48045283">Using the Guaranteed Contract DMA Buffer Model</a>), the size of the DMA buffer that is available to the display miniport driver to translate the command buffer at the next submission is the same as the size of the command buffer itself. For such a device, the OpenGL ICD should also determine the size of the allocation list that will be available to the display miniport driver during the translation of the command buffer at the next submission from the value that is returned in the <b>AllocationListSize</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff548238">D3DKMT_RENDER</a>. 

For devices that do not use guaranteed DMA buffer contract, the OpenGL ICD can use the information that is returned in the <b>CommandBufferSize</b> and <b>AllocationListSize</b> members to determine the size of the next DMA buffer and allocation list that will be available for translation. However, under low-memory conditions, the actual DMA buffer and allocation list that is provided to the display miniport driver might be smaller than required.

If the OpenGL ICD detects that most of the command buffer flushes are because the driver runs out of space in the command buffer or allocation list, the driver can request for them to be resized. To resize the command buffer, the driver sets the <b>ResizeCommandBuffer</b> bit-field flag in the <b>Flags</b> member of D3DKMT_RENDER and puts the requested size in the <b>CommandBufferSize</b> member of D3DKMT_RENDER. Similarly, to resize the allocation list, the driver sets the <b>ResizeAllocationList</b> bit-field flag in the <b>Flags</b> member of D3DKMT_RENDER and puts the requested number of elements in the <b>AllocationListSize</b> member of D3DKMT_RENDER.

> [!NOTE]
> Even though the driver can request for resizing of both the command buffer and the allocation list, the video memory manager might not be able to comply. Therefore, if the call to <b>D3DKMTRender</b> is successful, the driver should verify the values that are returned in the <b>pCommandBuffer</b>, <b>CommandBufferSize</b>, and <b>AllocationListSize</b> members.<br/>However, if the call to <b>D3DKMTRender</b> fails, the driver determines that the command buffer, the allocation list, or both were not resized. Therefore, the driver should not process the values that are returned in the <b>pCommandBuffer</b>, <b>CommandBufferSize</b>, and <b>AllocationListSize</b> members because they are invalid.


#### Examples

The following code example demonstrates how an OpenGL ICD can use <b>D3DKMTRender</b> to render 3-D primitives.

```cpp
HRESULT Render(D3DKMT_HANDLE hDevice, UINT CommandOffset, UINT CommandLength)
{
    D3DKMT_RENDER RenderData;

    memset(&amp;RenderData, 0, sizeof(RenderData));
    RenderData.hDevice = hDevice;
    RenderData.CommandOffset = CommandOffset;
    RenderData.CommandLength = CommandLength;

    if (NT_SUCCESS((*pfnKTRender)(&amp;RenderData))) {
        return S_OK;
    }
    return E_FAIL;
}
```
## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546959">D3DKMTGetDeviceState</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548238">D3DKMT_RENDER</a>
 

 

