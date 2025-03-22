---
UID: NS:d3dkmddi._DXGKARG_UPDATEMONITOREDVALUES
tech.root: display
title: DXGKARG_UPDATEMONITOREDVALUES
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKARG_UPDATEMONITOREDVALUES structure.
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
req.typenames: DXGKARG_UPDATEMONITOREDVALUES
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
 - _DXGKARG_UPDATEMONITOREDVALUES
 - DXGKARG_UPDATEMONITOREDVALUES
f1_keywords:
 - _DXGKARG_UPDATEMONITOREDVALUES
 - d3dkmddi/_DXGKARG_UPDATEMONITOREDVALUES
 - DXGKARG_UPDATEMONITOREDVALUES
 - d3dkmddi/DXGKARG_UPDATEMONITOREDVALUES
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_UPDATEMONITOREDVALUES
---

# DXGKARG_UPDATEMONITOREDVALUES structure (d3dkmddi.h)

## -description

**DXGKARG_UPDATEMONITOREDVALUES** is the parameter for the [**DxgkDdiUpdateMonitoredValues**](nc-d3dkmddi-dxgkddi_updatemonitoredvalues.md) function.

## -struct-fields

### -field NativeFenceArray

[in] Array of native fence handles.

### -field UpdatedValueArray

[in] Array of new monitored values.

### -field MonitoredValueKernelCpuVa

[in] Read/write kernel-mode CPU virtual address of the monitored value.

### -field NumFences

[in] Number of native fences that the OS updates monitored values of.

### -field Flags

[in] A [**DXGKARG_UPDATEMONITOREDVALUES_FLAGS **](ns-d3dkmddi-dxgkarg_updatemonitoredvalues_flags.md) value that specifies the flags for the update.

### -field Reserved[28]

Reserved for system use.

## -remarks

For more information about native GPU fences, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**DxgkDdiUpdateMonitoredValues**](nc-d3dkmddi-dxgkddi_updatemonitoredvalues.md)
