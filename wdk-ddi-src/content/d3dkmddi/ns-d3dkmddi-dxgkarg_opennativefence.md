---
UID: NS:d3dkmddi._DXGKARG_OPENNATIVEFENCE
tech.root: display
title: DXGKARG_OPENNATIVEFENCE
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKARG_OPENNATIVEFENCE structure.
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
req.typenames: DXGKARG_OPENNATIVEFENCE
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
 - _DXGKARG_OPENNATIVEFENCE
 - DXGKARG_OPENNATIVEFENCE
f1_keywords:
 - _DXGKARG_OPENNATIVEFENCE
 - d3dkmddi/_DXGKARG_OPENNATIVEFENCE
 - DXGKARG_OPENNATIVEFENCE
 - d3dkmddi/DXGKARG_OPENNATIVEFENCE
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_OPENNATIVEFENCE
---

# DXGKARG_OPENNATIVEFENCE structure (d3dkmddi.h)

## -description

**DXGKARG_OPENNATIVEFENCE** is the structure passed to [**DxgkDdiOpenNativeFence**](nc-d3dkmddi-dxgkddi_opennativefence.md).

## -struct-fields

### -field hGlobalNativeFence

[in] Driver-assigned handle to the fence object created in the prior call to [**DxgkDdiCreateNativeFence**](nc-d3dkmddi-dxgkddi_createnativefence.md).

### -field hLocalNativeFence

[in/out] On input, the value of **hLocalNativeFence** is the *Dxgkrnl*-generated handle of the object.

On output, the value returned by the KMD is the internal, KMD-maintained handle to be used by subsequent callbacks to refer to this local fence object.

### -field hDevice

[in] Driver handle for the parent device of this local fence object.

### -field CurrentValueGpuVa

[in] Read/write mapping of the current value for the GPU in user process address space.

### -field MonitoredValueGpuVa

[in] Read/write mapping of the monitored value for the GPU in user process address space.

### -field Flags

[in] A [**DXGK_OPENNATIVEFENCE_FLAGS**](ns-d3dkmddi-dxgk_opennativefence_flags.md) structure containing flags that indicate how to open the local GPU fence object.

### -field Reserved[32]

Reserved for system use.

## -remarks

For more information about native GPU fences, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**DxgkDdiOpenNativeFence**](nc-d3dkmddi-dxgkddi_opennativefence.md)
