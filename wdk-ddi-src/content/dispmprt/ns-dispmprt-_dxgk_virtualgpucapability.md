---
UID: NS:dispmprt._DXGK_VIRTUALGPUCAPABILITY
title: _DXGK_VIRTUALGPUCAPABILITY
author: windows-driver-content
description: Contains information about the virtual GPU capability.
tech.root: display
ms.assetid: 660eb862-90b5-4b23-abc5-b520202f3a71
ms.author: windowsdriverdev
ms.date: 04/04/2019 
ms.topic: struct
f1_keywords:
 - "dispmprt/_DXGK_VIRTUALGPUCAPABILITY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGK_VIRTUALGPUCAPABILITY, DXGK_VIRTUALGPUCAPABILITY, *PDXGK_VIRTUALGPUCAPABILITY, 
req.header: dispmprt.h
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
req.typenames: DXGK_VIRTUALGPUCAPABILITY, *PDXGK_VIRTUALGPUCAPABILITY
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - dispmprt.h
api_name: 
 - _DXGK_VIRTUALGPUCAPABILITY
product: 
 - Windows
targetos: Windows
ms.custom: 19H1
---

# _DXGK_VIRTUALGPUCAPABILITY structure

## -description

Contains information about the virtual GPU capability.

## -struct-fields

### -field MinValue

When the vGPU is running, each capability cannot be lower than *MinValue* and more than *MaxValue*.

### -field MaxValue

When the vGPU is running, each capability cannot be lower than *MinValue* and more than *MaxValue*.

### -field OptimalValue
 
The optimal value of the capability.

## -remarks

## -see-also
