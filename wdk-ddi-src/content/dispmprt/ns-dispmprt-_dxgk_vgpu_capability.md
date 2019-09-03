---
UID: NS:dispmprt._DXGK_VGPU_CAPABILITY
title: _DXGK_VGPU_CAPABILITY
author: windows-driver-content
description: Contains info about a virtual GPU capability.
tech.root: display
ms.assetid: 36f71088-758a-4bd5-adaa-20b3feeb9d03
ms.author: windowsdriverdev
ms.date: 04/04/2019 
ms.topic: struct
f1_keywords:
 - "dispmprt/_DXGK_VGPU_CAPABILITY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGK_VGPU_CAPABILITY, DXGK_VGPU_CAPABILITY, *PDXGK_VGPU_CAPABILITY, 
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
req.typenames: DXGK_VGPU_CAPABILITY, *PDXGK_VGPU_CAPABILITY
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - dispmprt.h
api_name: 
 - _DXGK_VGPU_CAPABILITY
product: 
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# _DXGK_VGPU_CAPABILITY structure

## -description

Contains info about a virtual GPU capability.

## -struct-fields

### -field MinValue

When the vGPU is running, each capability cannot be lower than *MinValue* and more than *MaxValue*.

### -field MaxValue

When the vGPU is running, each capability cannot be lower than *MinValue* and more than *MaxValue*.

### -field CurrentValue
 

## -remarks

## -see-also
