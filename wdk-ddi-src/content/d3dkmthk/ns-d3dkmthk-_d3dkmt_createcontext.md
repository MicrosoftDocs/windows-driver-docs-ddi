---
UID: NS:d3dkmthk._D3DKMT_CREATECONTEXT
title: _D3DKMT_CREATECONTEXT (d3dkmthk.h)
description: The D3DKMT_CREATECONTEXT structure describes a kernel-mode device context to create.
old-location: display\d3dkmt_createcontext.htm
ms.assetid: 867705b9-a721-48a6-b1bc-6a75d5a03a21
ms.date: 05/10/2018
keywords: ["D3DKMT_CREATECONTEXT structure"]
ms.keywords: D3DKMT_CREATECONTEXT, D3DKMT_CREATECONTEXT structure [Display Devices], OpenGL_Structs_5a3cc128-be06-4189-a389-95813c2d3e28.xml, _D3DKMT_CREATECONTEXT, d3dkmthk/D3DKMT_CREATECONTEXT, display.d3dkmt_createcontext
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
targetos: Windows
tech.root: display
req.typenames: D3DKMT_CREATECONTEXT
f1_keywords:
 - _D3DKMT_CREATECONTEXT
 - d3dkmthk/_D3DKMT_CREATECONTEXT
 - D3DKMT_CREATECONTEXT
 - d3dkmthk/D3DKMT_CREATECONTEXT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMT_CREATECONTEXT
---

# _D3DKMT_CREATECONTEXT structure


## -description

The D3DKMT_CREATECONTEXT structure describes a kernel-mode device context to create.

## -struct-fields

### -field hDevice

[in] A handle to the device to create the device context on.

### -field NodeOrdinal

[in] The zero-based index of the node that the context is scheduled on.

### -field EngineAffinity

[in] The engine affinity for the context.

### -field Flags

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_createcontextflags">D3DDDI_CREATECONTEXTFLAGS</a> structure that indicates, in bit-field flags, how to create the context.

### -field pPrivateDriverData

[in] A pointer to private data that is passed to the display miniport driver.

### -field PrivateDriverDataSize

[in] The size, in bytes, of the private data that <b>pPrivateDriverData</b> points to.

### -field ClientHint

[in] A D3DKMT_CLIENTHINT-typed value that indicates the type of client that creates the context. The following table lists the possible values.

|Value|Meaning|
|--- |--- |
|D3DKMT_CLIENTHINT_UNKNOWN (0)|The client is unknown.|
|D3DKMT_CLIENTHINT_OPENGL (1)|The client is the OpenGL runtime.|
|D3DKMT_CLIENTHINT_CDD (2)|This value is for internal use only. Do not use.|
|D3DKMT_CLIENTHINT_DX7 (7)|The client is the Microsoft DirectX 7.0 runtime.|
|D3DKMT_CLIENTHINT_DX8 (8)|The client is the DirectX 8.0 runtime.|
|D3DKMT_CLIENTHINT_DX9 (9)|The client is the DirectX 9.0 runtime.|
|D3DKMT_CLIENTHINT_DX10 (10)|The client is the DirectX 10.0 runtime.|

### -field hContext

[out] A handle to the device context that the DirectX graphics kernel subsystem (<i>Dxgkrnl.sys</i>) supplied and that is returned from the call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreatecontext">D3DKMTCreateContext</a> function.

### -field pCommandBuffer

[out] A pointer to command buffer memory that the OpenGL ICD places commands into. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreatecontext">D3DKMTCreateContext</a> function returns this memory pointer.

### -field CommandBufferSize

[out] The size, in bytes, of the memory block that <b>pCommandBuffer</b> points to. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreatecontext">D3DKMTCreateContext</a> function returns this size value.

### -field pAllocationList

[out] An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_allocationlist">D3DDDI_ALLOCATIONLIST</a> structures that the OpenGL ICD inserts referenced allocations in.

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreatecontext">D3DKMTCreateContext</a> function returns this array.

### -field AllocationListSize

[out] The number of elements in the array of allocations that <b>pAllocationList</b> points to. This quantity of allocations is available when the DirectX graphics kernel subsystem submits the command buffer that is pointed to by <b>pCommandBuffer</b> to the display miniport driver. 

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreatecontext">D3DKMTCreateContext</a> function returns this number.

### -field pPatchLocationList

[out] An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_patchlocationlist">D3DDDI_PATCHLOCATIONLIST</a> structures that the OpenGL ICD inserts patching information in.

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreatecontext">D3DKMTCreateContext</a> function returns this array.

### -field PatchLocationListSize

[out] The number of elements in the patch-location list that <b>pPatchLocationList</b> points to. This quantity of patch locations is available when the DirectX graphics kernel subsystem submits the command buffer that is pointed to by <b>pCommandBuffer</b> to the display miniport driver. 

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreatecontext">D3DKMTCreateContext</a> function returns this number.

### -field CommandBuffer

[out] A pointer to command buffer memory that the OpenGL ICD places commands into. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreatecontext">D3DKMTCreateContext</a> function returns this memory pointer.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_allocationlist">D3DDDI_ALLOCATIONLIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_createcontextflags">D3DDDI_CREATECONTEXTFLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_patchlocationlist">D3DDDI_PATCHLOCATIONLIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreatecontext">D3DKMTCreateContext</a>

