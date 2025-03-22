---
UID: NS:d3dkmddi._DXGKARG_CLOSENATIVEFENCE
tech.root: display
title: DXGKARG_CLOSENATIVEFENCE
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKARG_CLOSENATIVEFENCE structure.
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
req.typenames: DXGKARG_CLOSENATIVEFENCE
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
 - _DXGKARG_CLOSENATIVEFENCE
 - DXGKARG_CLOSENATIVEFENCE
f1_keywords:
 - _DXGKARG_CLOSENATIVEFENCE
 - d3dkmddi/_DXGKARG_CLOSENATIVEFENCE
 - DXGKARG_CLOSENATIVEFENCE
 - d3dkmddi/DXGKARG_CLOSENATIVEFENCE
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_CLOSENATIVEFENCE
---

# DXGKARG_CLOSENATIVEFENCE structure (d3dkmddi.h)

## -description

**DXGKARG_CLOSENATIVEFENCE** is the structure passed to [**DxgkDdiCloseNativeFence**](nc-d3dkmddi-dxgkddi_closenativefence.md).

## -struct-fields

### -field hLocalNativeFence

[in] Driver-assigned handle to the fence object opened in a prior call to [**DxgkDdiOpenNativeFence**](nc-d3dkmddi-dxgkddi_opennativefence.md).

### -field Flags

[in] A [**DXGK_CLOSENATIVEFENCE_FLAGS**](ns-d3dkmddi-dxgk_closenativefence_flags.md) structure containing flags that indicate how to close the local GPU fence object.

### -field Reserved[32]

Reserved for system use.

## -remarks

For more information about native GPU fences, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**DxgkDdiCloseNativeFence**](nc-d3dkmddi-dxgkddi_closenativefence.md)

[**DxgkDdiOpenNativeFence**](nc-d3dkmddi-dxgkddi_opennativefence.md)
