---
UID: NS:d3dukmdt._DXGK_NATIVE_FENCE_LOG_ENTRY
tech.root: display
title: DXGK_NATIVE_FENCE_LOG_ENTRY
ms.date: 03/21/2024
targetos: Windows
description: Learn more about the DXGK_NATIVE_FENCE_LOG_ENTRY structure.
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
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGK_NATIVE_FENCE_LOG_ENTRY
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
 - _DXGK_NATIVE_FENCE_LOG_ENTRY
 - DXGK_NATIVE_FENCE_LOG_ENTRY
f1_keywords:
 - _DXGK_NATIVE_FENCE_LOG_ENTRY
 - d3dukmdt/_DXGK_NATIVE_FENCE_LOG_ENTRY
 - DXGK_NATIVE_FENCE_LOG_ENTRY
 - d3dukmdt/DXGK_NATIVE_FENCE_LOG_ENTRY
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_NATIVE_FENCE_LOG_ENTRY
---

# DXGK_NATIVE_FENCE_LOG_ENTRY structure (d3dukmdt.h)

## -description

The **DXGK_NATIVE_FENCE_LOG_ENTRY** structure contains a native fence log entry.

## -struct-fields

### -field FenceValue

UMD payload: The newly signaled/unblocked fence value.

### -field hNativeFence

UMD payload: User-mode D3DKMT_HANDLE of the native fence to which this operation belongs.

### -field OperationType

UMD payload: A [**DXGK_FENCE_LOG_OPERATION**](ne-d3dukmdt-dxgk_native_fence_log_operation.md) value that specifies the type of the operation.

### -field Reserved0

Reserved for alignment.

### -field FenceObservedGpuTimestamp

GPU Payload: When **OperationType** is OPERATION_WAIT_UNBLOCKED, specifies the GPU time at which an unresolved wait command was seen by the engine and stalled the HWQueue.

### -field Reserved1

Reserved for alignment.

### -field FenceEndGpuTimestamp

GPU Payload: GPU time at which the fence operation completed on the GPU.

## -remarks

For more information about native GPU fences and log buffer usage, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**DXGK_NATIVE_FENCE_LOG_BUFFER**](ns-d3dukmdt-dxgk_native_fence_log_buffer.md)

[**DXGK_NATIVE_FENCE_LOG_HEADER**](ns-d3dukmdt-dxgk_native_fence_log_header.md)

[**DXGK_FENCE_LOG_OPERATION**](ne-d3dukmdt-dxgk_native_fence_log_operation.md)

[**DxgkDdiSetNativeFenceLogBuffer**](../d3dkmddi/nc-d3dkmddi-dxgkddi_setnativefencelogbuffer.md)
