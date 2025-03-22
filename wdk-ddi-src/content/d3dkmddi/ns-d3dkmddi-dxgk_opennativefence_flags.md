---
UID: NS:d3dkmddi._DXGK_OPENNATIVEFENCE_FLAGS
tech.root: display
title: DXGK_OPENNATIVEFENCE_FLAGS
ms.date: 03/28/2024
targetos: Windows
description: Learn more about DXGK_OPENNATIVEFENCE_FLAGS.
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
req.typenames: DXGK_OPENNATIVEFENCE_FLAGS
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
 - _DXGK_OPENNATIVEFENCE_FLAGS
 - DXGK_OPENNATIVEFENCE_FLAGS
f1_keywords:
 - _DXGK_OPENNATIVEFENCE_FLAGS
 - d3dkmddi/_DXGK_OPENNATIVEFENCE_FLAGS
 - DXGK_OPENNATIVEFENCE_FLAGS
 - d3dkmddi/DXGK_OPENNATIVEFENCE_FLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_OPENNATIVEFENCE_FLAGS
---

# DXGK_OPENNATIVEFENCE_FLAGS structure (d3dkmddi.h)

## -description

**DXGK_OPENNATIVEFENCE_FLAGS** specifies flags to use when opening a native GPU fence.

## -struct-fields

### -field Reserved

Reserved for system use.

### -field Value

An alternative way to access the structure members.

## -remarks

For more information about native GPU fences, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**DXGKARG_CREATENATIVEFENCE**](ns-d3dkmddi-dxgkarg_createnativefence.md)

[**DxgkDdiOpenNativeFence**](nc-d3dkmddi-dxgkddi_opennativefence.md)
