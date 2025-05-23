---
UID: NS:d3dkmddi._DXGKARG_SUBMITCOMMANDVIRTUAL
title: DXGKARG_SUBMITCOMMANDVIRTUAL (d3dkmddi.h)
description: DXGKARG_SUBMITCOMMANDVIRTUAL is used to submit a direct memory access (DMA) buffer to a context that supports virtual addressing with the DxgkDdiSubmitCommandVirtualdevice driver interface (DDI).
ms.date: 05/22/2025
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.typenames: DXGKARG_SUBMITCOMMANDVIRTUAL
f1_keywords:
 - _DXGKARG_SUBMITCOMMANDVIRTUAL
 - d3dkmddi/_DXGKARG_SUBMITCOMMANDVIRTUAL
 - DXGKARG_SUBMITCOMMANDVIRTUAL
 - d3dkmddi/DXGKARG_SUBMITCOMMANDVIRTUAL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_SUBMITCOMMANDVIRTUAL
 - DXGKARG_SUBMITCOMMANDVIRTUAL
---

# DXGKARG_SUBMITCOMMANDVIRTUAL structure

## -description

The **DXGKARG_SUBMITCOMMANDVIRTUAL** structure is passed to [**DxgkDdiSubmitCommandVirtual**](nc-d3dkmddi-dxgkddi_submitcommandvirtual.md) to submit a DMA buffer to a context that supports virtual addressing.

## -struct-fields

### -field hContext

The handle returned from [**DxgkDdiCreateContext**](nc-d3dkmddi-dxgkddi_createcontext.md).

### -field DmaBufferVirtualAddress

The virtual address for the DMA buffer in the context of the submitting process.

### -field DmaBufferSize

The size of the DMA buffer in bytes.

### -field pDmaBufferPrivateData

A pointer to the driver's private data buffer.

### -field DmaBufferPrivateDataSize

The size of the driver's private data buffer in bytes.

### -field DmaBufferUmdPrivateDataSize

Size of the private driver data, in bytes, that was set by the user mode driver (UMD) in **SubmitCommandCb**. When **SubmitCommandCb** is called, *Dxgkrnl* allocates a buffer for the private driver data with the size equal to [**DXGK_CONTEXTINFO**](ns-d3dkmddi-_dxgk_contextinfo.md)::**DmaBufferPrivateDataSize**. This size was reported by the kernel mode driver (KMD) in its  [**DxgkDdiCreateContext**](nc-d3dkmddi-dxgkddi_createcontext.md) call. *Dxgkrnl* copies the driver's private data from the **SubmitCommandCb** to the allocated buffer.

### -field SubmissionFenceId

A unique identifier that the driver can write into the fence command in the ring buffer, which is the buffer where DMA buffers are queued for the GPU to run. For more information about these types of identifiers, see [Supplying Fence Identifiers](/windows-hardware/drivers/display/supplying-fence-identifiers).

### -field VidPnSourceId

The zero-based identification number of the video present source in a path of a video present network (VidPN) topology for a flip operation. This member is valid only when the **Flip** or **FlipWithNoWait** bit-field flag is set in the **Flags** member.

### -field FlipInterval

A [**D3DDDI_FLIPINTERVAL_TYPE**](../d3dukmdt/ne-d3dukmdt-d3dddi_flipinterval_type.md)-typed value that indicates the flip interval (that is, if the flip occurs after zero, one, two, three, or four vertical syncs). **FlipInterval** is valid only if the **Flip** bit-field flag is set (that is, TRUE) in the **Flags** member.

### -field Flags

A [**DXGK_SUBMITCOMMANDFLAGS**](ns-d3dkmddi-_dxgk_submitcommandflags.md) structure that identifies information about the DMA buffer to submit.

### -field EngineOrdinal

Reserved for future use.

### -field NodeOrdinal

The zero-based index of the node that the context is created for. Identifies the node when the context is NULL.

## -see-also

[**D3DDDI_FLIPINTERVAL_TYPE**](../d3dukmdt/ne-d3dukmdt-d3dddi_flipinterval_type.md)

[**DXGK_CONTEXTINFO**](ns-d3dkmddi-_dxgk_contextinfo.md)

[**DxgkDdiCreateContext**](nc-d3dkmddi-dxgkddi_createcontext.md)

[**DxgkDdiSubmitCommandVirtual**](nc-d3dkmddi-dxgkddi_submitcommandvirtual.md)
