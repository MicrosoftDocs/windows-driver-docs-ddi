---
UID: NS:d3dkmddi._DXGKARG_UPDATENATIVEFENCELOGS_FLAGS
tech.root: display
title: DXGKARG_UPDATENATIVEFENCELOGS_FLAGS
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKARG_UPDATENATIVEFENCELOGS_FLAGS structure.
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
req.typenames: DXGKARG_UPDATENATIVEFENCELOGS_FLAGS
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
 - _DXGKARG_UPDATENATIVEFENCELOGS_FLAGS
 - DXGKARG_UPDATENATIVEFENCELOGS_FLAGS
f1_keywords:
 - _DXGKARG_UPDATENATIVEFENCELOGS_FLAGS
 - d3dkmddi/_DXGKARG_UPDATENATIVEFENCELOGS_FLAGS
 - DXGKARG_UPDATENATIVEFENCELOGS_FLAGS
 - d3dkmddi/DXGKARG_UPDATENATIVEFENCELOGS_FLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_UPDATENATIVEFENCELOGS_FLAGS
---

# DXGKARG_UPDATENATIVEFENCELOGS_FLAGS structure (d3dkmddi.h)

## -description

**DXGKARG_UPDATENATIVEFENCELOGS_FLAGS** specifies flags to use when flushing native fence log writes.

## -struct-fields

### -field Reserved

Reserved for system use.

### -field Value

An alternative way to access the flags.

## -remarks

For more information about native GPU fences and log buffer usage, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**DXGKARG_UPDATENATIVEFENCELOGS**](ns-d3dkmddi-dxgkarg_updatenativefencelogs.md)

[**DxgkDdiUpdateNativeFenceLogs**](nc-d3dkmddi-dxgkddi_updatenativefencelogs.md)
