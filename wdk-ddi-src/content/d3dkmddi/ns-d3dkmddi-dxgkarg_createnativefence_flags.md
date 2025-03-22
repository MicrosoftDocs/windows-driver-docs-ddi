---
UID: NS:d3dkmddi._DXGKARG_CREATENATIVEFENCE_FLAGS
tech.root: display
title: DXGKARG_CREATENATIVEFENCE_FLAGS
ms.date: 03/28/2024
targetos: Windows
description: Learn more about DXGKARG_CREATENATIVEFENCE_FLAGS.
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
req.typenames: DXGKARG_CREATENATIVEFENCE_FLAGS
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
 - _DXGKARG_CREATENATIVEFENCE_FLAGS
 - DXGKARG_CREATENATIVEFENCE_FLAGS
f1_keywords:
 - _DXGKARG_CREATENATIVEFENCE_FLAGS
 - d3dkmddi/_DXGKARG_CREATENATIVEFENCE_FLAGS
 - DXGKARG_CREATENATIVEFENCE_FLAGS
 - d3dkmddi/DXGKARG_CREATENATIVEFENCE_FLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_CREATENATIVEFENCE_FLAGS
---

# DXGKARG_CREATENATIVEFENCE_FLAGS structure (d3dkmddi.h)

## -description

**DXGKARG_CREATENATIVEFENCE_FLAGS** specifies flags to use when creating a native GPU fence.

## -struct-fields

### -field Reserved

Reserved for system use.

### -field Value

An alternative way to access the structure members.

## -remarks

For more information about native GPU fences, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**DXGKARG_CREATENATIVEFENCE**](ns-d3dkmddi-dxgkarg_createnativefence.md)

[**DxgkDdiCreateNativeFence**](nc-d3dkmddi-dxgkddi_createnativefence.md)
