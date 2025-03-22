---
UID: NS:d3dkmddi._DXGKARG_DESTROYNATIVEFENCE
tech.root: display
title: DXGKARG_DESTROYNATIVEFENCE
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKARG_DESTROYNATIVEFENCE structure.
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
req.typenames: DXGKARG_DESTROYNATIVEFENCE
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
 - _DXGKARG_DESTROYNATIVEFENCE
 - DXGKARG_DESTROYNATIVEFENCE
f1_keywords:
 - _DXGKARG_DESTROYNATIVEFENCE
 - d3dkmddi/_DXGKARG_DESTROYNATIVEFENCE
 - DXGKARG_DESTROYNATIVEFENCE
 - d3dkmddi/DXGKARG_DESTROYNATIVEFENCE
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_DESTROYNATIVEFENCE
---

# DXGKARG_DESTROYNATIVEFENCE structure (d3dkmddi.h)

## -description

**DXGKARG_DESTROYNATIVEFENCE** is the structure passed to [**DxgkDdiDestroyNativeFence**](nc-d3dkmddi-dxgkddi_destroynativefence.md).

## -struct-fields

### -field hGlobalNativeFence

[in] Handle to the global native GPU fence object. KMD returned this handle from a prior call to [**DXGKARG_CREATENATIVEFENCE**](ns-d3dkmddi-dxgkarg_createnativefence.md).

### -field Flags

[in] A [**DXGKARG_DESTROYNATIVEFENCE_FLAGS**](ns-d3dkmddi-dxgk_destroynativefence_flags.md) structure containing flags to use when destroying the native GPU fence object.

### -field Reserved[32]

Reserved for system use.

## -remarks

KMD should destroy its global fence data associated with **hGlobalNativeFence**.

For more information about native GPU fences, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**DxgkDdiDestroyNativeFence**](nc-d3dkmddi-dxgkddi_destroynativefence.md)
