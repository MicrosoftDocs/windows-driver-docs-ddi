---
UID: NE:d3dukmdt._DXGK_NATIVE_FENCE_LOG_OPERATION
tech.root: display
title: DXGK_NATIVE_FENCE_LOG_OPERATION
ms.date: 03/21/2024
targetos: Windows
description: Learn more about the DXGK_NATIVE_FENCE_LOG_OPERATION enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3dukmdt.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _DXGK_NATIVE_FENCE_LOG_OPERATION
 - DXGK_NATIVE_FENCE_LOG_OPERATION
f1_keywords:
 - _DXGK_NATIVE_FENCE_LOG_OPERATION
 - d3dukmdt/_DXGK_NATIVE_FENCE_LOG_OPERATION
 - DXGK_NATIVE_FENCE_LOG_OPERATION
 - d3dukmdt/DXGK_NATIVE_FENCE_LOG_OPERATION
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_NATIVE_FENCE_LOG_OPERATION
---

# DXGK_NATIVE_FENCE_LOG_OPERATION enumeration (d3dukmdt.h)

## -description

A **DXGK_NATIVE_FENCE_LOG_OPERATION** value identifies the native log entry operation being logged.

## -enum-fields

### -field DXGK_NATIVE_FENCE_LOG_OPERATION_SIGNAL_EXECUTED:0

The log entry is for a signal operation that has been executed on the GPU.

### -field DXGK_NATIVE_FENCE_LOG_OPERATION_WAIT_UNBLOCKED:1

The log entry is for a wait condition that has been satisfied on the GPU.

## -remarks

For more information about native GPU fences and log buffer usage, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**DXGK_NATIVE_FENCE_LOG_ENTRY**](ns-d3dukmdt-dxgk_native_fence_log_entry.md)

[**DxgkDdiSetNativeFenceLogBuffer**](../d3dkmddi/nc-d3dkmddi-dxgkddi_setnativefencelogbuffer.md)
