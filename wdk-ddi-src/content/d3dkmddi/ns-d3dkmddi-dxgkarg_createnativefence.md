---
UID: NS:d3dkmddi._DXGKARG_CREATENATIVEFENCE
tech.root: display
title: DXGKARG_CREATENATIVEFENCE
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKARG_CREATENATIVEFENCE structure.
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
req.typenames: DXGKARG_CREATENATIVEFENCE
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
 - _DXGKARG_CREATENATIVEFENCE
 - DXGKARG_CREATENATIVEFENCE
f1_keywords:
 - _DXGKARG_CREATENATIVEFENCE
 - d3dkmddi/_DXGKARG_CREATENATIVEFENCE
 - DXGKARG_CREATENATIVEFENCE
 - d3dkmddi/DXGKARG_CREATENATIVEFENCE
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_CREATENATIVEFENCE
---

# DXGKARG_CREATENATIVEFENCE structure (d3dkmddi.h)

## -description

**DXGKARG_CREATENATIVEFENCE** is the structure passed to [**DxgkDdiCreateNativeFence**](nc-d3dkmddi-dxgkddi_createnativefence.md) to describe a native GPU fence.

## -struct-fields

### -field hGlobalNativeFence

[in/out] On input, the value of **hGlobalNativeFence** is the *Dxgkrnl*-generated handle of the object.

On output, the value returned by the KMD is the internal, KMD-maintained handle to be used by subsequent callbacks to refer to this native GPU fence object.

### -field Type

[in] A [**D3DDDI_NATIVEFENCE_TYPE**](../d3dukmdt/ne-d3dukmdt-d3dddi_nativefence_type.md) value that indicates the type of native GPU fence object to create.

### -field CurrentValueSystemProcessGpuVa

[in] Read/write mapping of the current value for the GPU in system process address space. The OS has does this mapping only if KMD has set the [**DXGK_NATIVE_FENCE_CAPS::MapToGpuSystemProcess**](ns-d3dkmddi-dxgk_native_fence_caps.md) cap to TRUE.

### -field MonitoredValueSystemProcessGpuVa

[in] Read/write mapping of the monitored value for the GPU in system process address space. The OS has does this mapping only if KMD has set the [**DXGK_NATIVE_FENCE_CAPS::MapToGpuSystemProcess**](ns-d3dkmddi-dxgk_native_fence_caps.md) cap to TRUE.

### -field pPrivateDriverData[D3DDDI_NATIVE_FENCE_PDD_SIZE]

[in/out] Pointer to the private driver data from the user-mode **CreateNativeFence** call, copied back to UMD.

### -field Flags

[in] A [**DXGKARG_CREATENATIVEFENCE_FLAGS**](ns-d3dkmddi-dxgkarg_createnativefence_flags.md) structure containing flags to use when creating the native GPU fence object.

### -field Reserved[32]

Reserved for system use.

## -remarks

For more information about native GPU fences, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**DxgkDdiCreateNativeFence**](nc-d3dkmddi-dxgkddi_createnativefence.md)
