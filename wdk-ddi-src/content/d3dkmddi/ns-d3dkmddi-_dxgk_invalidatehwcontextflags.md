---
UID: NS:d3dkmddi._DXGK_INVALIDATEHWCONTEXTFLAGS
title: _DXGK_INVALIDATEHWCONTEXTFLAGS
author: windows-driver-content
description:
ms.assetid: 67f6eb63-d277-4c36-a43a-f4dd22209a72
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	apiref
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	_DXGK_INVALIDATEHWCONTEXTFLAGS
product: Windows
targetos: Windows
---

# _DXGK_INVALIDATEHWCONTEXTFLAGS structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Contains running contexts that were are were not affected by the GPU engine reset operation.

## -struct-fields

### -field CollateralDamage

O indicates that the context being invalidated was the primary cause of the engine hang. 1 indicates that the context being invalidated was not the primary cause of the engine hang, but still needs to be reset because it was affected by the hang.

### -field Reserved

Reserved for internal use.

### -field Value

The value of the context flag.
