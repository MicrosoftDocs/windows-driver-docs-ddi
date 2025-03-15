---
UID: NS:d3dkmddi._DXGKARG_CREATEHWQUEUE
tech.root: display
title: DXGKARG_CREATEHWQUEUE
ms.date: 11/08/2024
targetos: Windows
description: Learn more about the DXGKARG_CREATEHWQUEUE structure.
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
req.target-min-winverclnt: Windows 10, version 1703 (WDDM 2.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGKARG_CREATEHWQUEUE
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
 - _DXGKARG_CREATEHWQUEUE
 - DXGKARG_CREATEHWQUEUE
f1_keywords:
 - _DXGKARG_CREATEHWQUEUE
 - d3dkmddi/_DXGKARG_CREATEHWQUEUE
 - DXGKARG_CREATEHWQUEUE
 - d3dkmddi/DXGKARG_CREATEHWQUEUE
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_CREATEHWQUEUE
---

## -description

The **DXGKARG_CREATEHWQUEUE** structure is used with [**DxgkDdiCreateHwQueue**](nc-d3dkmddi-dxgkddi_createhwqueue.md) to create a hardware queue.

## -struct-fields

### -field hHwQueue

[in/out] On input, *Dxgkrnl*'s handle to the hardware queue. On output, the driver's handle to the hardware queue.

### -field Flags

[in] A [**D3DDDI_CREATEHWQUEUEFLAGS**](../d3dukmdt/ns-d3dukmdt-_d3dddi_createhwqueueflags.md) structure containing the queue creation flags.

### -field PrivateDriverDataSize

[in] Size in bytes of the private driver data that **pPrivateDriverData** points to.

### -field pPrivateDriverData

[in/out] Pointer to the private driver data that was passed by the user-mode driver's [**pfnCreateHwContextCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_createhwcontextcb.md) function. Since **pPrivateDriverData** is an in-out parameter, KMD can also return private data back to the UMD.

### -field hHwQueueProgressFence

[in] Handle to the GPU synchronization object created by the OS for this hardware queue. The progress fence is used to synchronize DMA buffer completion on this hardware queue. See Remarks.

### -field HwQueueProgressFenceCPUVirtualAddress

[in] Kernel-mode CPU virtual address that can be used to read the currently signaled value of the hardware queue progress fence.

### -field HwQueueProgressFenceGPUVirtualAddress

[in] GPU virtual address that can be used to read or write the value of the hardware queue progress fence. The queue progress fence value must monotonically increase with each new submission to the hardware queue. GPU instructions to update the queue progress fence must be inserted by the user-mode driver at the end of the DMA buffer being tracked.

## -remarks

For kernel submission HWQueues, the OS will allocate the progress fence as a native fence type on GPUs that support native fences. When the [**NativeProgressFence**](../d3dukmdt/ns-d3dukmdt-_d3dddi_createhwqueueflags.md) flag is set, KMD's [**DxgkDdiCreateHwQueue**](nc-d3dkmddi-dxgkddi_createhwqueue.md) must read the corresponding **hHwQueueNativeProgressFence** field that specifies the driver handle to the native fence object previously created in [**DxgkDdiCreateNativeFence**](nc-d3dkmddi-dxgkddi_createnativefence.md). If the **NativeProgressFence** flag is FALSE then this HWQueue's progress fence is a regular monitored fence object, and KMD must read the legacy **hHwQueueProgressFence** field like before.

Upon creating a native fence for a HWQueue, the OS will also set **D3DKMT_CREATEHWQUEUE::Flags.NativeProgressFence** to TRUE, so that the runtime is also aware that the HWQueue's progress fence was allocated as a native fence.

For user submission HWQueues, OS will allocate its progress fence as a native fence in **DxgkDdiCreateHwQueueForUserModeSubmission**() by definition.

Note on driver compatibility: *Dxgkrnl* will only write to the **hHwQueueNativeProgressFence** field on drivers that support the **NativeGpuFence** cap. This ensures that OS will only reference this field on in-development and future drivers that are compiled with this updated header. KMD will only read this field if **DXGKARG_CREATEHWQUEUE.Flags.NativeProgressFence** is TRUE. This ensures that KMD only references this field on the latest OS builds that support native progress fence and this updated header.

## -see-also

[**DxgkDdiCreateHwQueue**](nc-d3dkmddi-dxgkddi_createhwqueue.md)
