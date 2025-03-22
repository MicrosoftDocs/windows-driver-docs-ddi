---
UID: NS:d3dukmdt._DXGK_NATIVE_FENCE_LOG_BUFFER
tech.root: display
title: DXGK_NATIVE_FENCE_LOG_BUFFER
ms.date: 03/21/2024
targetos: Windows
description: Learn more about the DXGK_NATIVE_FENCE_LOG_BUFFER structure.
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
req.typenames: DXGK_NATIVE_FENCE_LOG_BUFFER
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
 - _DXGK_NATIVE_FENCE_LOG_BUFFER
 - DXGK_NATIVE_FENCE_LOG_BUFFER
f1_keywords:
 - _DXGK_NATIVE_FENCE_LOG_BUFFER
 - d3dukmdt/_DXGK_NATIVE_FENCE_LOG_BUFFER
 - DXGK_NATIVE_FENCE_LOG_BUFFER
 - d3dukmdt/DXGK_NATIVE_FENCE_LOG_BUFFER
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_NATIVE_FENCE_LOG_BUFFER
---

# DXGK_NATIVE_FENCE_LOG_BUFFER structure (d3dukmdt.h)

## -description

**DXGK_NATIVE_FENCE_LOG_BUFFER** is a structure that represents a native fence log buffer.

## -struct-fields

### -field Header

A [**DXGK_NATIVE_FENCE_LOG_HEADER**](ns-d3dukmdt-dxgk_native_fence_log_header.md) structure that contains the header information for the native fence log buffer.

### -field Entries[1]

Array of **Header.NumberofEntries** [**DXGK_NATIVE_FENCE_LOG_ENTRY**](ns-d3dukmdt-dxgk_native_fence_log_entry.md) structures that contain the native fence log entries.

## -remarks

For more information about native GPU fences and log buffer usage, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**DXGK_NATIVE_FENCE_LOG_ENTRY**](ns-d3dukmdt-dxgk_native_fence_log_entry.md)

[**DXGK_NATIVE_FENCE_LOG_HEADER**](ns-d3dukmdt-dxgk_native_fence_log_header.md)

[**DXGKARG_SETNATIVEFENCELOGBUFFER**](../d3dkmddi/ns-d3dkmddi-dxgkarg_setnativefencelogbuffer.md)

[**DxgkDdiSetNativeFenceLogBuffer**](../d3dkmddi/nc-d3dkmddi-dxgkddi_setnativefencelogbuffer.md)
