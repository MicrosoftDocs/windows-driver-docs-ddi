---
UID: NS:d3dkmddi._DXGKARG_RESETHWENGINE
tech.root: display
title: DXGKARG_RESETHWENGINE
ms.date: 10/03/2023
targetos: Windows
description: Learn more about the DXARG_RESETHWENGINE structure.
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
req.target-min-winverclnt: Windows 10, version 1703 (WDDM 2.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGKARG_RESETHWENGINE
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
 - _DXGKARG_RESETHWENGINE
 - DXGKARG_RESETHWENGINE
f1_keywords:
 - _DXGKARG_RESETHWENGINE
 - d3dkmddi/_DXGKARG_RESETHWENGINE
 - DXGKARG_RESETHWENGINE
 - d3dkmddi/DXGKARG_RESETHWENGINE
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_RESETHWENGINE
---

## -description

The **DXGKARG_RESETHWENGINE** structure contains arguments used to [reset the hardware engine](nc-d3dkmddi-dxgkddi_resethwengine.md).

## -struct-fields

### -field NodeOrdinal

[in] GPU node ordinal for the GPU engine that is being requested to reset.

### -field EngineOrdinal

[in] GPU engine ordinal being requested to reset.

## -see-also

[**DxgkDdiResetHwEngine**](nc-d3dkmddi-dxgkddi_resethwengine.md)
