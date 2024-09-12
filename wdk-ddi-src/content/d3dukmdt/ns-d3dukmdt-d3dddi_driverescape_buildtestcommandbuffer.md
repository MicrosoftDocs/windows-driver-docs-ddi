---
UID: NS:d3dukmdt._D3DDDI_DRIVERESCAPE_BUILDTESTCOMMANDBUFFER
tech.root: display
title: D3DDDI_DRIVERESCAPE_BUILDTESTCOMMANDBUFFER
ms.date: 06/17/2024
targetos: Windows
description: Learn about the D3DDDI_DRIVERESCAPE_BUILDTESTCOMMANDBUFFER structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dukmdt.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3DDDI_DRIVERESCAPE_BUILDTESTCOMMANDBUFFER
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _D3DDDI_DRIVERESCAPE_BUILDTESTCOMMANDBUFFER
 - D3DDDI_DRIVERESCAPE_BUILDTESTCOMMANDBUFFER
f1_keywords:
 - _D3DDDI_DRIVERESCAPE_BUILDTESTCOMMANDBUFFER
 - d3dukmdt/_D3DDDI_DRIVERESCAPE_BUILDTESTCOMMANDBUFFER
 - D3DDDI_DRIVERESCAPE_BUILDTESTCOMMANDBUFFER
 - d3dukmdt/D3DDDI_DRIVERESCAPE_BUILDTESTCOMMANDBUFFER
dev_langs:
 - c++
helpviewer_keywords:
 - _D3DDDI_DRIVERESCAPE_BUILDTESTCOMMANDBUFFER
---

## -description

The **D3DDDI_DRIVERESCAPE_BUILDTESTCOMMANDBUFFER** structure defines the kernel-mode driver (KMD) escape for building a test command buffer.

## -struct-fields

### -field EscapeType

[in] A [**D3DDDI_DRIVERESCAPETYPE**](ne-d3dukmdt-_d3dddi_driverescapetype.md). Must be set to **D3DDDI_DRIVERESCAPETYPE_BUILDTESTCOMMANDBUFFER**.

### -field hDevice

[in] Handle to the display device.

### -field hContext

[in] KMD context handle returned from [**DxgkDdiCreateContext**](../d3dkmddi/nc-d3dkmddi-dxgkddi_createcontext.md) when [**Flags.HardwareQueue**](ns-d3dukmdt-d3dddi_buildtestcommandbufferflags.md) is 0, or KMD hardware queue handle returned from [**DxgkDdiCreatehwqueue**](../d3dkmddi/nc-d3dkmddi-dxgkddi_createhwqueue.md) when **Flags.HardwareQueue** is 1.

### -field Flags

[in] A [**D3DDDI_BUILDTESTCOMMANDBUFFERFLAGS**](ns-d3dukmdt-d3dddi_buildtestcommandbufferflags.md) structure that specifies flags to use when building a command buffer for kernel-mode testing.

### -field Command

[in] A [**D3DDDI_TESTCOMMANDBUFFER**](ns-d3dukmdt-d3dddi_testcommandbuffer.md) structure that describes the command buffer to build.

### -field pDmaBuffer

[in/out] Pointer to the buffer in which KMD should write the generated commands to.

### -field DmaBufferSize

[in/out] On input, specifies the size in bytes of the buffer that **pDmaBuffer** points to. On output, specifies the number of bytes that KMD has written to the buffer. See  [**DXGKDDI_BUILDTESTCOMMANDBUFFER**](../d3dkmddi/nc-d3dkmddi-dxgkddi_buildtestcommandbuffer.md) for more information.

### -field pDmaBufferPrivateData

[in/out] Pointer to the buffer in which KMD can write data that is relevant to the execution of generated device instructions.

### -field DmaBufferPrivateDataSize

[in/out] On input, specifies the size in bytes of the buffer that **pDmaBufferPrivateData** points to. On output, specifies the number of bytes that KMD has written to the buffer. See  [**DXGKDDI_BUILDTESTCOMMANDBUFFER**](../d3dkmddi/nc-d3dkmddi-dxgkddi_buildtestcommandbuffer.md) for more information.

## -remarks

This structure is used by test applications that don't know the specifics of internal device formats.

For more information, see [Kernel-mode testing](/windows-hardware/drivers/display/kernel-mode-testing-of-wddm-features).

## -see-also

[**DXGKARG_ESCAPE**](../d3dkmddi/ns-d3dkmddi-_dxgkarg_escape.md)

[**DXGKDDI_ESCAPE**](../d3dkmddi/nc-d3dkmddi-dxgkddi_escape.md)
