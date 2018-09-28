---
UID: NE:d3dkmthk._D3DKMT_TRACKEDWORKLOADPOLICY
title: _D3DKMT_TRACKEDWORKLOADPOLICY
author: windows-driver-content
description: Indicates if the execution of tracked workload should attempt to preserve battery or be geared towards performance.
ms.assetid: 3e508c6e-cf67-423d-bc1b-7566dbce965e
ms.author: windowsdriverdev
ms.date: 
ms.topic: enum
ms.keywords: _D3DKMT_TRACKEDWORKLOADPOLICY, D3DKMT_TRACKEDWORKLOADPOLICY, 
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3dkmthk.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: D3DKMT_TRACKEDWORKLOADPOLICY
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3dkmthk.h
api_name: 
-	_D3DKMT_TRACKEDWORKLOADPOLICY
product:
-	Windows
targetos: Windows
tech.root: display
---

# _D3DKMT_TRACKEDWORKLOADPOLICY enumeration

## -description

Indicates if the execution of tracked workload should attempt to preserve battery or be geared towards performance.

## -enum-fields

### -field D3DKMT_TRACKEDWORKLOADPOLICY_NORMAL

The tracked workload should be executed in the GPU with the goal of optimal balance between battery/performance.

### -field D3DKMT_TRACKEDWORKLOADPOLICY_ENERGY_EFFICIENT

The tracked workload should be executed in the GPU with the goal of preserving battery.

### -field D3DKMT_TRACKEDWORKLOADPOLICY_HIGH_SPEED 

The tracked workload should be executed in the GPU with the goal of maximum performance.

## -remarks

## -see-also