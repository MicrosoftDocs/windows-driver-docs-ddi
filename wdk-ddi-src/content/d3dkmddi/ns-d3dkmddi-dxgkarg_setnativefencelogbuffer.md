---
UID: NS:d3dkmddi._DXGKARG_SETNATIVEFENCELOGBUFFER
tech.root: display
title: DXGKARG_SETNATIVEFENCELOGBUFFER
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKARG_SETNATIVEFENCELOGBUFFER structure.
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
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGKARG_SETNATIVEFENCELOGBUFFER
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
 - _DXGKARG_SETNATIVEFENCELOGBUFFER
 - DXGKARG_SETNATIVEFENCELOGBUFFER
f1_keywords:
 - _DXGKARG_SETNATIVEFENCELOGBUFFER
 - d3dkmddi/_DXGKARG_SETNATIVEFENCELOGBUFFER
 - DXGKARG_SETNATIVEFENCELOGBUFFER
 - d3dkmddi/DXGKARG_SETNATIVEFENCELOGBUFFER
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_SETNATIVEFENCELOGBUFFER
---

# DXGKARG_SETNATIVEFENCELOGBUFFER structure (d3dkmddi.h)

## -description

**DXGKARG_SETNATIVEFENCELOGBUFFER** is the input structure for [**DxgkDdiSetNativeFenceLogBuffer**](nc-d3dkmddi-dxgkddi_setnativefencelogbuffer.md).

## -struct-fields

### -field hHwQueue

[in] Driver handle of the HWQueue to which this log belongs.

### -field NumberOfEntries

[in] Number of entries in the array of log entries that **LogBufferCpuVa** points to.

### -field LogBufferCpuVa

[in] The read/write kernel-mode CPU virtual address of the [native fence log buffer](../d3dukmdt/ns-d3dukmdt-dxgk_native_fence_log_buffer.md).

### -field LogBufferGpuVa

[in] The read/write GPU VA of the log buffer in user process address space.

### -field LogBufferSystemProcessGpuVa

[in] The read/write GPU VA of the log buffer in system address space.

### -field Flags

[in] A [**DXGKARG_SETNATIVEFENCELOGBUFFER_FLAGS**](../d3dkmddi/ns-d3dkmddi-dxgkarg_setnativefencelogbuffer_flags.md) structure that contains flags for writing a payload into the native fence log buffer.

### -field Reserved[32]

Reserved for system use.

## -remarks

For more information about native GPU fences and log buffer usage, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**DXGK_NATIVE_FENCE_LOG_BUFFER**](../d3dukmdt/ns-d3dukmdt-dxgk_native_fence_log_buffer.md)

[**DxgkDdiSetNativeFenceLogBuffer**](nc-d3dkmddi-dxgkddi_setnativefencelogbuffer.md)
