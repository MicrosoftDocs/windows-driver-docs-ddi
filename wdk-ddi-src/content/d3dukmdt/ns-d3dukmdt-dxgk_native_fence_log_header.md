---
UID: NS:d3dukmdt._DXGK_NATIVE_FENCE_LOG_HEADER
tech.root: display
title: DXGK_NATIVE_FENCE_LOG_HEADER
ms.date: 03/21/2024
targetos: Windows
description: Learn more about the DXGK_NATIVE_FENCE_LOG_HEADER structure.
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
req.typenames: DXGK_NATIVE_FENCE_LOG_HEADER
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
 - _DXGK_NATIVE_FENCE_LOG_HEADER
 - DXGK_NATIVE_FENCE_LOG_HEADER
f1_keywords:
 - _DXGK_NATIVE_FENCE_LOG_HEADER
 - d3dukmdt/_DXGK_NATIVE_FENCE_LOG_HEADER
 - DXGK_NATIVE_FENCE_LOG_HEADER
 - d3dukmdt/DXGK_NATIVE_FENCE_LOG_HEADER
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_NATIVE_FENCE_LOG_HEADER
---

# DXGK_NATIVE_FENCE_LOG_HEADER structure (d3dukmdt.h)

## -description

The **DXGK_NATIVE_FENCE_LOG_HEADER** structure contains the header information for the native fence log buffer.

## -struct-fields

### -field FirstFreeEntryIndex

Index of the first free entry in the log. **FirstFreeEntryIndex** is the same value as the LowPart of **AtomicWraparoundAndEntryIndex**.

### -field WraparoundCount

The number of times the log entries have wrapped around. Same value as the HighPart of **AtomicWraparoundAndEntryIndex**.

### -field AtomicWraparoundAndEntryIndex

A 64-bit integer that contains the **FirstFreeEntryIndex** in the LowPart and the **WraparoundCount** in the HighPart.

### -field Type

A [**DXGK_NATIVE_FENCE_LOG_TYPE**](ne-d3dukmdt-dxgk_native_fence_log_type.md) enumeration that specifies the type of the native fence log entries.

### -field NumberOfEntries

Number of [**DXGK_NATIVE_FENCE_LOG_ENTRY**](ns-d3dukmdt-dxgk_native_fence_log_entry.md) structures in the **Entries** array of the [native fence log buffer](ns-d3dukmdt-dxgk_native_fence_log_buffer.md).

### -field Reserved[2]

Reserved for system use.

## -remarks

For more information about native GPU fences and log buffer usage, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**DXGK_NATIVE_FENCE_LOG_BUFFER**](ns-d3dukmdt-dxgk_native_fence_log_buffer.md)

[**DXGK_NATIVE_FENCE_LOG_ENTRY**](ns-d3dukmdt-dxgk_native_fence_log_entry.md)

[**DXGK_NATIVE_FENCE_LOG_TYPE**](ne-d3dukmdt-dxgk_native_fence_log_type.md)

[**DxgkDdiSetNativeFenceLogBuffer**](../d3dkmddi/nc-d3dkmddi-dxgkddi_setnativefencelogbuffer.md)
