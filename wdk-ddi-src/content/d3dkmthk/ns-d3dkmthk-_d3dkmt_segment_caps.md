---
UID: NS:d3dkmthk._D3DKMT_SEGMENT_CAPS
title: _D3DKMT_SEGMENT_CAPS
author: windows-driver-content
description: Contains segment capabilities.
ms.assetid: cf294dd9-efc3-41fd-94ce-da55be3d584e
ms.author: windowsdriverdev
ms.date: 
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _D3DKMT_SEGMENT_CAPS, D3DKMT_SEGMENT_CAPS, 
req.header: d3dkmthk.h
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
req.typenames: D3DKMT_SEGMENT_CAPS
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3dkmthk.h
api_name: 
-	_D3DKMT_SEGMENT_CAPS
product:
-	Windows
targetos: Windows
---

# _D3DKMT_SEGMENT_CAPS structure

## -description

Contains segment capabilities.

## -struct-fields

### -field Size

Size of the segment.

### -field PageSize

The page sized.

### -field SegmentId

The segment Id.

### -field bAperture

Indicates whether the segment is an aperture.

### -field bReservedSysMem

Indicates whether the segment is a reserved system memory.

### -field BudgetGroup
 
A D3DKMT_MEMORY_SEGMENT_GROUP that represents the budget group.

## -remarks

## -see-also