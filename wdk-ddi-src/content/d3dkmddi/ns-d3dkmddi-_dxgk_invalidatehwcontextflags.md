---
UID: NS:d3dkmddi._DXGK_INVALIDATEHWCONTEXTFLAGS
title: _DXGK_INVALIDATEHWCONTEXTFLAGS (d3dkmddi.h)
description: Contains running contexts that were are were not affected by the GPU engine reset operation.
ms.assetid: 67f6eb63-d277-4c36-a43a-f4dd22209a72
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _DXGK_INVALIDATEHWCONTEXTFLAGS, DXGK_INVALIDATEHWCONTEXTFLAGS,
req.header: d3dkmddi.h
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
req.typenames: DXGK_INVALIDATEHWCONTEXTFLAGS
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	_DXGK_INVALIDATEHWCONTEXTFLAGS
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# _DXGK_INVALIDATEHWCONTEXTFLAGS structure

## -description

Contains running contexts that were are were not affected by the GPU engine reset operation.

## -struct-fields

### -field CollateralDamage

O indicates that the context being invalidated was the primary cause of the engine hang. 1 indicates that the context being invalidated was not the primary cause of the engine hang, but still needs to be reset because it was affected by the hang.

### -field Reserved

Reserved for internal use.

### -field Value

The value of the context flag.
