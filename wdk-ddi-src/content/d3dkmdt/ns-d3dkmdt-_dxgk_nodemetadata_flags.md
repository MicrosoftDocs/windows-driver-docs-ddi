---
UID: NS:d3dkmdt._DXGK_NODEMETADATA_FLAGS
title: DXGK_NODEMETADATA_FLAGS (d3dkmdt.h)
description: Defines node metadata flags for a context.
ms.date: 05/24/2022
keywords: ["DXGK_NODEMETADATA_FLAGS structure"]
ms.keywords: _DXGK_NODEMETADATA_FLAGS, DXGK_NODEMETADATA_FLAGS,
req.header: d3dkmdt.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGK_NODEMETADATA_FLAGS
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _DXGK_NODEMETADATA_FLAGS
 - d3dkmdt/_DXGK_NODEMETADATA_FLAGS
 - DXGK_NODEMETADATA_FLAGS
 - d3dkmdt/DXGK_NODEMETADATA_FLAGS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _DXGK_NODEMETADATA_FLAGS
 - DXGK_NODEMETADATA_FLAGS
dev_langs:
 - c++
---

# DXGK_NODEMETADATA_FLAGS structure

## -description

Defines node metadata flags for a context.

## -struct-fields

### -field ContextSchedulingSupported

Context-based scheduling model.

### -field RingBufferFenceRelease

Ring buffer fence release.

### -field SupportTrackedWorkload

Supports tracked workload.

### -field UserModeSubmission

User-mode submission.

### -field MaxInFlightHwQueueBuffers

The maximum number of command buffers submitted by the hardware scheduler to the kernel-mode driver. A value of zero indicates no limit.

### -field Reserved

Reserved.

### -field Value
