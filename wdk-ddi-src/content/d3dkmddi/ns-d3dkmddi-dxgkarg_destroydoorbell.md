---
UID: NS:d3dkmddi._DXGKARG_DESTROYDOORBELL
tech.root: display
title: DXGKARG_DESTROYDOORBELL
ms.date: 05/22/2023
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
req.target-min-winverclnt: WIN11_FUTURE
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

## -description

The **DXGKARG_DESTROYDOORBELL** structure contains parameters for [**DxgkDdiDestroyDoorbell**](ns-d3dkmddi-dxgkddi_destroydoorbell.md).

## -struct-fields

### -field hDoorbell

[in] KMD handle to the doorbell object being destroyed. This handle was previously created using [**DxgkDdiCreateDoorbell**](nc-d3dkmddi-dxgkddi_createdoorbell.md).

## -see-also

[**DxgkDdiCreateDoorbell**](nc-d3dkmddi-dxgkddi_createdoorbell.md)

[**DxgkDdiDestroyDoorbell**](ns-d3dkmddi-dxgkddi_destroydoorbell.md)
