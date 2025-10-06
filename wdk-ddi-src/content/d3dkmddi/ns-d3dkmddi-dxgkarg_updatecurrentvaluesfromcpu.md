---
UID: NS:d3dkmddi._DXGKARG_UPDATECURRENTVALUESFROMCPU
tech.root: display
title: DXGKARG_UPDATECURRENTVALUESFROMCPU
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKARG_UPDATECURRENTVALUESFROMCPU structure.
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
req.typenames: DXGKARG_UPDATECURRENTVALUESFROMCPU
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
 - _DXGKARG_UPDATECURRENTVALUESFROMCPU
 - DXGKARG_UPDATECURRENTVALUESFROMCPU
f1_keywords:
 - _DXGKARG_UPDATECURRENTVALUESFROMCPU
 - d3dkmddi/_DXGKARG_UPDATECURRENTVALUESFROMCPU
 - DXGKARG_UPDATECURRENTVALUESFROMCPU
 - d3dkmddi/DXGKARG_UPDATECURRENTVALUESFROMCPU
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_UPDATECURRENTVALUESFROMCPU
---

## -description

**DXGKARG_UPDATECURRENTVALUESFROMCPU** is the parameter for the [**DxgkDdiUpdateCurrentValuesFromCpu**](nc-d3dkmddi-dxgkddi_updatecurrentvaluesfromcpu.md) function.

## -struct-fields

### -field NativeFenceArray

[in] Array of native fence handles.

### -field UpdatedValueArray

[in] Array of new current values.

### -field CurrentValueKernelCpuVa

[in] The read/write kernel-mode CPU virtual address of the current value.

### -field NumFences

[in] Number of native fences that the OS updates current values of.

### -field Flags

[in] A [**DXGK_UPDATECURRENTVALUESFROMCPU_FLAGS**](ns-d3dkmddi-dxgk_updatecurrentvaluesfromcpu_flags.md) structure that contains the flags for the update.

### -field Reserved[28]

Reserved for system use.

## -remarks

For more information about native GPU fences, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**DXGK_UPDATECURRENTVALUESFROMCPU_FLAGS**](ns-d3dkmddi-dxgk_updatecurrentvaluesfromcpu_flags.md)

[**DxgkDdiUpdateCurrentValuesFromCpu**](nc-d3dkmddi-dxgkddi_updatecurrentvaluesfromcpu.md)
