---
UID: NS:d3dkmddi._DXGKARG_CREATEDOORBELL_FLAGS
tech.root: display
title: DXGKARG_CREATEDOORBELL_FLAGS
ms.date: 05/22/2023
targetos: Windows
description: Learn more about the DXGKARG_CREATEDOORBELL_FLAGS structure.
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
req.typenames: DXGKARG_CREATEDOORBELL_FLAGS
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
 - _DXGKARG_CREATEDOORBELL_FLAGS
 - DXGKARG_CREATEDOORBELL_FLAGS
f1_keywords:
 - _DXGKARG_CREATEDOORBELL_FLAGS
 - d3dkmddi/_DXGKARG_CREATEDOORBELL_FLAGS
 - DXGKARG_CREATEDOORBELL_FLAGS
 - d3dkmddi/DXGKARG_CREATEDOORBELL_FLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_CREATEDOORBELL_FLAGS
---

## -description

The **DXGKARG_CREATEDOORBELL_FLAGS** structure specifies doorbell creation flags.

## -struct-fields

### -field ResizeRingBufferOperation

Indication from UMD to KMD that a doorbell is being recreated for this hardware queue with a new, resized [**hRingBuffer**](d3dkmddi\ns-d3dkmddi-dxgkarg_createdoorbell.md) ring buffer.

### -field Reserved

Reserved; set to zero.

### -field Value

An alternative way to access the structure members.

## -see-also

[**DXGKARG_CREATEDOORBELL**](d3dkmddi\ns-d3dkmddi-dxgkarg_createdoorbell.md)

[**DxgkDdiCreateDoorbell**](ns-d3dkmddi-dxgkddi_createdoorbell.md)
