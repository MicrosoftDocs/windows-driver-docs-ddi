---
UID: NS:d3dkmddi._DXGKARG_BUILDTESTCOMMANDBUFFER
tech.root: display
title: DXGKARG_BUILDTESTCOMMANDBUFFER
ms.date: 06/17/2024
targetos: Windows
description: Learn about the DXGKARG_BUILDTESTCOMMANDBUFFER structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGKARG_BUILDTESTCOMMANDBUFFER
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_BUILDTESTCOMMANDBUFFER
 - DXGKARG_BUILDTESTCOMMANDBUFFER
f1_keywords:
 - _DXGKARG_BUILDTESTCOMMANDBUFFER
 - d3dkmddi/_DXGKARG_BUILDTESTCOMMANDBUFFER
 - DXGKARG_BUILDTESTCOMMANDBUFFER
 - d3dkmddi/DXGKARG_BUILDTESTCOMMANDBUFFER
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_BUILDTESTCOMMANDBUFFER
---

## -description

The **DXGKARG_BUILDTESTCOMMANDBUFFER** structure describes a test command buffer for [**DXGKDDI_BUILDTESTCOMMANDBUFFER::pfnBuildTestCommandBuffer**](nc-d3dkmddi-dxgkddi_buildtestcommandbuffer.md).

## -struct-fields

### -field hContext

[in] KMD context handle returned from [**DxgkDdiCreateContext**](nc-d3dkmddi-dxgkddi_createcontext.md) when [**Flags.HardwareQueue**](../d3dukmdt/ns-d3dukmdt-d3dddi_buildtestcommandbufferflags.md) is 0, or KMD hardware queue handle returned from [**DxgkDdiCreatehwqueue**](nc-d3dkmddi-dxgkddi_createhwqueue.md) when **Flags.HardwareQueue** is 1.

### -field Command

[in] A [**D3DDDI_TESTCOMMANDBUFFER**](../d3dukmdt/ns-d3dukmdt-d3dddi_testcommandbuffer.md) structure that describes the test command for which DMA buffer needs to be generated.

### -field pDmaBuffer

[in/out] Pointer to the buffer in which KMD should write the generated commands to.

### -field pDmaBufferPrivateData

[in/out] Pointer to the buffer in which KMD can write data that is relevant to the execution of generated device instructions.

### -field DmaBufferSize

[in/out] On input, specifies the size in bytes of the buffer that **pDmaBuffer** points to. On output, specifies the number of bytes that KMD has written to the buffer. See  [**DXGKDDI_BUILDTESTCOMMANDBUFFER**](nc-d3dkmddi-dxgkddi_buildtestcommandbuffer.md) for more information.

### -field DmaBufferPrivateDataSize

[in/out] On input, specifies the size in bytes of the buffer that **pDmaBufferPrivateData** points to. On output, specifies the number of bytes that KMD has written to the buffer. See  [**DXGKDDI_BUILDTESTCOMMANDBUFFER**](nc-d3dkmddi-dxgkddi_buildtestcommandbuffer.md) for more information.

### -field Flags

[in] A [**D3DDDI_BUILDTESTCOMMANDBUFFERFLAGS**](../d3dukmdt/ns-d3dukmdt-d3dddi_buildtestcommandbufferflags.md) structure that describes the flags for the test command buffer.

## -remarks

For more information, see [Kernel-mode testing](/windows-hardware/drivers/display/kernel-mode-testing-of-wddm-features).

## -see-also

[**D3DDDI_BUILDTESTCOMMANDBUFFERFLAGS**](../d3dukmdt/ns-d3dukmdt-d3dddi_buildtestcommandbufferflags.md)

[**D3DDDI_TESTCOMMANDBUFFER**](../d3dukmdt/ns-d3dukmdt-d3dddi_testcommandbuffer.md)

 [**DXGKDDI_BUILDTESTCOMMANDBUFFER**](nc-d3dkmddi-dxgkddi_buildtestcommandbuffer.md)
