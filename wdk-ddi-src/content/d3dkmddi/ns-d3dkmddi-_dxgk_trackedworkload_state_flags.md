---
UID: NS:d3dkmddi._DXGK_TRACKEDWORKLOAD_STATE_FLAGS
title: _DXGK_TRACKEDWORKLOAD_STATE_FLAGS
description: Indicates GPU configurations, including the appropriate frequencies and power level, for a context.
ms.assetid: 0b6f3ccf-c4c8-4787-87dc-8397385e1374
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _DXGK_TRACKEDWORKLOAD_STATE_FLAGS, DXGK_TRACKEDWORKLOAD_STATE_FLAGS, 
req.header: d3dkmddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGK_TRACKEDWORKLOAD_STATE_FLAGS
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3dkmddi.h
api_name: 
-	_DXGK_TRACKEDWORKLOAD_STATE_FLAGS
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# _DXGK_TRACKEDWORKLOAD_STATE_FLAGS structure

## -description

Indicates GPU configurations, including the appropriate frequencies and power level, for a context.

## -struct-fields

### -field Saturated

The driver should set this state flag if the driver cannot go higher than specified. This includes transient states like thermal limits.

### -field OptimalLevel

The driver should set this flag if for the given power level, we are in an optimal efficiency range for the tracked workload. The driver should set this flag only when, for certain workloads, lowering the frequency will reduce the performance per watt.

### -field Reserved

This value is reserved.

### -field Value
 

## -remarks

## -see-also
