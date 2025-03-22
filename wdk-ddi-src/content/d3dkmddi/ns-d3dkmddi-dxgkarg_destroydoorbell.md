---
UID: NS:d3dkmddi._DXGKARG_DESTROYDOORBELL
tech.root: display
title: DXGKARG_DESTROYDOORBELL
ms.date: 04/08/2024
targetos: Windows
description: Learn more about the DXGKARG_DESTROYDOORBELL structure.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGKARG_DESTROYDOORBELL
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
 - _DXGKARG_DESTROYDOORBELL
 - DXGKARG_DESTROYDOORBELL
f1_keywords:
 - _DXGKARG_DESTROYDOORBELL
 - d3dkmddi/_DXGKARG_DESTROYDOORBELL
 - DXGKARG_DESTROYDOORBELL
 - d3dkmddi/DXGKARG_DESTROYDOORBELL
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_DESTROYDOORBELL
---

# DXGKARG_DESTROYDOORBELL structure (d3dkmddi.h)

## -description

The **DXGKARG_DESTROYDOORBELL** structure contains parameters for [**DxgkDdiDestroyDoorbell**](nc-d3dkmddi-dxgkddi_destroydoorbell.md).

## -struct-fields

### -field hDoorbell

[in] KMD handle to the doorbell object being destroyed. This handle was previously created using [**DxgkDdiCreateDoorbell**](nc-d3dkmddi-dxgkddi_createdoorbell.md).

## -remarks

For more information, see [User-mode work submission](/windows-hardware/drivers/display/user-mode-work-submission).

## -see-also

[**DxgkDdiCreateDoorbell**](nc-d3dkmddi-dxgkddi_createdoorbell.md)

[**DxgkDdiDestroyDoorbell**](nc-d3dkmddi-dxgkddi_destroydoorbell.md)
