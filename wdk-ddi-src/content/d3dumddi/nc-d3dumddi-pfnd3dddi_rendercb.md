---
UID: NC:d3dumddi.PFND3DDDI_RENDERCB
title: PFND3DDDI_RENDERCB
author: windows-driver-content
description: The pfnRenderCb function submits the current command buffer for rendering to the display miniport driver.
old-location: display\pfnrendercb.htm
old-project: display
ms.assetid: f242162e-6237-469c-b178-5a51dcf69e32
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: pfnRenderCb
req.alt-loc: d3dumddi.h
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
req.typenames: DXGK_PTE
---

# PFND3DDDI_RENDERCB callback



## -description
The <b>pfnRenderCb</b> function submits the current command buffer for rendering to the display miniport driver.



## -prototype

````
PFND3DDDI_RENDERCB pfnRenderCb;

__checkReturn HRESULT APIENTRY CALLBACK pfnRenderCb(
  _In_    HANDLE          hDevice,
  _Inout_ D3DDDICB_RENDER *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to the display device (graphics context).


### -param pData [in, out]

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_render.md">D3DDDICB_RENDER</a> structure that describes the current command buffer to render.


## -returns
<b>pfnRenderCb</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The command buffer was successfully rendered.
<dl>
<dt><b>D3DDDIERR_PRIVILEGEDINSTRUCTION</b></dt>
</dl>The display miniport driver detected a privileged instruction in the command buffer; privileged instructions cannot be present in a command buffer.
<dl>
<dt><b>D3DDDIERR_ILLEGALINSTRUCTION</b></dt>
</dl>The display miniport driver detected instructions that graphics hardware cannot support.
<dl>
<dt><b>D3DDDIERR_INVALIDHANDLE</b></dt>
</dl>The display miniport driver detected an invalid handle in the command buffer.
<dl>
<dt><b>D3DDDIERR_CANTRENDERLOCKEDALLOCATION</b></dt>
</dl>The video memory manager detected references to a locked allocation in the allocation list. Note that the video memory manager returns this error only if it could not reposition the allocation to an AGP or system memory segment.
<dl>
<dt><b>D3DDDIERR_INVALIDUSERBUFFER</b></dt>
</dl>The display miniport driver detected an underrun or overrun of data or instructions. That is, the driver received less or more instructions or data than it expected. 
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><b>pfnRenderCb</b> could not complete because of insufficient memory.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>Parameters were validated and determined to be incorrect.

 

This function might also return other HRESULT values.


## -remarks
When the user-mode display driver must submit the current command buffer for rendering to the display miniport driver (for example, during a call to the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_flush.md">Flush</a> or Flush(D3D10) function), the user-mode display driver must call the <b>pfnRenderCb</b> function. The user-mode display driver should set the <i>hDevice</i> parameter to the value the Microsoft Direct3D runtime supplied during the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdevice.md">CreateDevice</a> or CreateDevice(D3D10) call. In the <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_render.md">D3DDDICB_RENDER</a> structure that is pointed to by the <i>pData </i>parameter, the user-mode display driver should also set:

The <b>CommandLength</b> member to the number of bytes of commands in the command buffer that start from offset zero. 

The <b>CommandOffset</b> member to nonzero if the user-mode display driver must specify an offset to the first hardware command in the command buffer.

The <b>NumAllocations</b> member to the number of elements in the allocation list.

The <b>NumPatchLocations</b> member to the number of elements in the patch-location list.

After a call to <b>pfnRenderCb</b>, the user-mode display driver must determine the base address and size of the command buffer that it should use for its next submission from the values that are returned in the <b>pNewCommandBuffer</b> and <b>NewCommandBufferSize</b> members of <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_render.md">D3DDDICB_RENDER</a>. Similarly, the driver must determine the base address and number of elements of the next allocation list and patch-location list from the values that are returned in the <b>pNewAllocationList</b> and <b>NewAllocationListSize</b> members and <b>pNewPatchLocationList</b> and <b>NewPatchLocationListSize</b> members respectively.

If the user-mode display driver detects that most of the command buffer flushes are because the driver runs out of space in the command buffer, allocation list, or patch-location list, the driver can request for them to be resized. To resize the command buffer, the driver sets the <b>ResizeCommandBuffer</b> bit-field flag in the <b>Flags</b> member of <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_render.md">D3DDDICB_RENDER</a> and puts the requested size in the <b>NewCommandBufferSize</b> member of D3DDDICB_RENDER. Similarly, to resize the allocation list, the driver sets the <b>ResizeAllocationList</b> bit-field flag in the <b>Flags</b> member of D3DDDICB_RENDER and puts the requested number of elements in the <b>NewAllocationListSize</b> member of D3DDDICB_RENDER. To resize the patch-location list, the driver sets the <b>ResizePatchLocationList</b> bit-field flag in the <b>Flags</b> member of D3DDDICB_RENDER and puts the requested number of elements in the <b>NewPatchLocationListSize</b> member of D3DDDICB_RENDER. 

If the user-mode display driver sets the <b>hContext</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_render.md">D3DDDICB_RENDER</a> structure that is pointed to by the <i>pData</i> parameter to <b>NULL</b>, the Microsoft Direct3D runtime sends the rendering operation to the default context of the device. If the user-mode display driver sets <b>hContext</b> to a valid handle that the <a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a> function previously returned and that represents a device context, the Direct3D runtime sends the rendering operation to that context. <b>Direct3D Version 11 Note:  </b>For more information about how the driver calls <b>pfnRenderCb</b>, see <a href="https://msdn.microsoft.com/014a5e44-f8c4-45c0-96e8-d82f37b8b28d">Changes from Direct3D 10</a>.



<b>Direct3D Version 11 Note:  </b>For more information about how the driver calls <b>pfnRenderCb</b>, see <a href="https://msdn.microsoft.com/014a5e44-f8c4-45c0-96e8-d82f37b8b28d">Changes from Direct3D 10</a>.

The following code example shows how to submit the current command buffer for rendering to the display miniport driver. This code example generates the allocation list after the command buffer and patch list are generated. This is not optimal for performance because the command buffer is parsed more than necessary. However, this implementation is easier to show. In a production driver, generating the command buffer at the same time as the allocation and patch lists is more efficient.


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdevice.md">CreateDevice</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_render.md">D3DDDICB_RENDER</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicecallbacks.md">D3DDDI_DEVICECALLBACKS</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_flush.md">Flush</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_RENDERCB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

