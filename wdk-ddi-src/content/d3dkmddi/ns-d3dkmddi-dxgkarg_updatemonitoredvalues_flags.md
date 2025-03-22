---
UID: NS:d3dkmddi._DXGKARG_UPDATEMONITOREDVALUES_FLAGS
tech.root: display
title: DXGKARG_UPDATEMONITOREDVALUES_FLAGS
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKARG_UPDATEMONITOREDVALUES_FLAGS structure.
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
req.typenames: DXGKARG_UPDATEMONITOREDVALUES_FLAGS
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
 - _DXGKARG_UPDATEMONITOREDVALUES_FLAGS
 - DXGKARG_UPDATEMONITOREDVALUES_FLAGS
f1_keywords:
 - _DXGKARG_UPDATEMONITOREDVALUES_FLAGS
 - d3dkmddi/_DXGKARG_UPDATEMONITOREDVALUES_FLAGS
 - DXGKARG_UPDATEMONITOREDVALUES_FLAGS
 - d3dkmddi/DXGKARG_UPDATEMONITOREDVALUES_FLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_UPDATEMONITOREDVALUES_FLAGS
---

# DXGKARG_UPDATEMONITOREDVALUES_FLAGS structure (d3dkmddi.h)

## -description

**DXGKARG_UPDATEMONITOREDVALUES_FLAGS** specifies flags to use when updating monitored values for a native GPU fence.

## -struct-fields

### -field Reserved

Reserved for system use.

### -field Value

An alternative way to access the structure members.

## -remarks

For more information about native GPU fences, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**DXGKARG_UPDATEMONITOREDVALUES**](ns-d3dkmddi-dxgkarg_updatemonitoredvalues.md)

[**DxgkDdiUpdateMonitoredValues**](nc-d3dkmddi-dxgkddi_updatemonitoredvalues.md)
