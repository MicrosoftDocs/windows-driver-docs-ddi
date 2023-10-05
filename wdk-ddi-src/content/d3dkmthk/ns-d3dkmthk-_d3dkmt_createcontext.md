---
UID: NS:d3dkmthk._D3DKMT_CREATECONTEXT
title: D3DKMT_CREATECONTEXT (d3dkmthk.h)
description: Learn more about the D3DKMT_CREATECONTEXT structure.
old-location: display\d3dkmt_createcontext.htm
ms.date: 02/28/2023
keywords: ["D3DKMT_CREATECONTEXT structure"]
ms.keywords: D3DKMT_CREATECONTEXT, D3DKMT_CREATECONTEXT structure [Display Devices], OpenGL_Structs_5a3cc128-be06-4189-a389-95813c2d3e28.xml, _D3DKMT_CREATECONTEXT, d3dkmthk/D3DKMT_CREATECONTEXT, display.d3dkmt_createcontext
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
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
 - _D3DKMT_CREATECONTEXT
 - D3DKMT_CREATECONTEXT
---

# D3DKMT_CREATECONTEXT structure

## -description

The **D3DKMT_CREATECONTEXT** structure is used with [**D3DKMTCreateContext**](nf-d3dkmthk-d3dkmtcreatecontext.md) to create a kernel-mode device context.

## -struct-fields

### -field hDevice

[in] A handle to the device that owns the context being created.

### -field NodeOrdinal

[in] The zero-based index of the node that the context is scheduled on.

### -field EngineAffinity

[in] The zero-based index for the engine, within the node that **NodeOrdinal** specifies, that the context can run in.

### -field Flags

[in] A [**D3DDDI_CREATECONTEXTFLAGS**](../d3dukmdt/ns-d3dukmdt-_d3dddi_createcontextflags.md) structure that indicates, in bit-field flags, how to create the context.

### -field unnamedParam1

[in] A pointer to private data that is to be passed to the display miniport driver.

### -field PrivateDriverDataSize

[in] The size, in bytes, of the private data that **pPrivateDriverData** points to.

### -field ClientHint

[in] A [**D3DKMT_CLIENTHINT**](ne-d3dkmthk-_d3dkmt_clienthint.md) value that indicates the type of client that is creating the context.

### -field hContext

[out] A handle to the created device context.

### -field unnamedParam2

[out] Pointer to an array of allocated command buffers in which the OpenGL ICD can place commands into.

### -field CommandBufferSize

[out] The size, in bytes, of the memory block that **pCommandBuffer** points to.

### -field unnamedParam3

[out] Pointer to an array of [**D3DDDI_ALLOCATIONLIST**](../d3dukmdt/ns-d3dukmdt-_d3dddi_allocationlist.md) structures that the OpenGL ICD can insert referenced allocations in.

### -field AllocationListSize

[out] The number of elements in the array of allocations that **pAllocationList** points to. This quantity of allocations is available when *Dxgkrnl* submits the command buffer that is pointed to by **pCommandBuffer** to the display miniport driver.

### -field unnamedParam4

[out] Pointer to an allocated array of [**D3DDDI_PATCHLOCATIONLIST**](../d3dukmdt/ns-d3dukmdt-_d3dddi_patchlocationlist.md) structures that the OpenGL ICD inserts patching information in.

### -field PatchLocationListSize

[out] The number of elements in the patch-location list that **pPatchLocationList** points to. This quantity of patch locations is available when *Dxgkrnl* submits the command buffer that is pointed to by **pCommandBuffer** to the display miniport driver.

### -field CommandBuffer

[out] The GPU virtual address of the command buffer memory.

## -see-also

[**D3DDDI_ALLOCATIONLIST**](../d3dukmdt/ns-d3dukmdt-_d3dddi_allocationlist.md)

[**D3DDDI_CREATECONTEXTFLAGS**](../d3dukmdt/ns-d3dukmdt-_d3dddi_createcontextflags.md)

[**D3DDDI_PATCHLOCATIONLIST**](../d3dukmdt/ns-d3dukmdt-_d3dddi_patchlocationlist.md)

[**D3DKMTCreateContext**](nf-d3dkmthk-d3dkmtcreatecontext.md)
