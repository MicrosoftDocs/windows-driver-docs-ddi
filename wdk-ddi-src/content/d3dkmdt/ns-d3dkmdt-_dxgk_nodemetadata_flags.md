---
UID: NS:d3dkmdt._DXGK_NODEMETADATA_FLAGS
title: _DXGK_NODEMETADATA_FLAGS (d3dkmdt.h)
description: Defines node metadata flags for a context.
ms.assetid: 1c350249-da27-4a7c-bf05-38ff484fcfc2
ms.date: 10/19/2018
ms.topic: struct
f1_keywords:
 - "d3dkmdt/_DXGK_NODEMETADATA_FLAGS"
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
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dkmdt.h
api_name: 
- _DXGK_NODEMETADATA_FLAGS
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# _DXGK_NODEMETADATA_FLAGS structure

## -description

Defines node metadata flags for a context.

## -struct-fields

### -field ContextSchedulingSupported

Context-based scheduling model.

### -field RingBufferFenceRelease

Ring buffer fence release.

### -field SupportTrackedWorkload

Supports tracked workload.

### -field MaxInFlightHwQueueBuffers

The maximum number of command buffers submitted by the hardware schedular, to the kernel mode driver. 0 indicates no limit.

### -field Reserved

Reserved.

### -field Value
 

## -remarks

## -see-also
