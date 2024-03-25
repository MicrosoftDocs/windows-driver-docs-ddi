---
UID: NS:d3dkmddi._DXGKARG_RESUMEHWENGINE
tech.root: display
title: DXGKARG_RESUMEHWENGINE (d3dkmddi.h)
description: Learn more about the DXGKARG_RESUMEHWENGINE structure.
ms.date: 10/03/2023
keywords: ["DXGKARG_RESUMEHWENGINE structure"]
ms.keywords: _DXGKARG_RESUMEHWENGINE, DXGKARG_RESUMEHWENGINE, *INOUT_PDXGKARG_RESUMEHWENGINE
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1703 (WDDM 2.2)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGKARG_RESUMEHWENGINE
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _DXGKARG_RESUMEHWENGINE
 - d3dkmddi/_DXGKARG_RESUMEHWENGINE
 - DXGKARG_RESUMEHWENGINE
 - d3dkmddi/DXGKARG_RESUMEHWENGINE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_RESUMEHWENGINE
 - DXGKARG_RESUMEHWENGINE
dev_langs:
 - c++
---

# DXGKARG_RESUMEHWENGINE structure

## -description

The **DXGKARG_RESUMEHWENGINE** structure contains arguments used to [resume the hardware engine](nc-d3dkmddi-dxgkddi_resumehwengine.md).

## -struct-fields

### -field NodeOrdinal

[in] GPU node ordinal for the GPU engine that is being requested to resume.

### -field EngineOrdinal

[in] GPU engine ordinal being requested to resume.

## -see-also

[**DxgkDdiResumeHwEngine**](nc-d3dkmddi-dxgkddi_resumehwengine.md)
