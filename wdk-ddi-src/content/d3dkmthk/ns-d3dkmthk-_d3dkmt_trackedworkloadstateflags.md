---
UID: NS:d3dkmthk._D3DKMT_TRACKEDWORKLOADSTATEFLAGS
title: _D3DKMT_TRACKEDWORKLOADSTATEFLAGS (d3dkmthk.h)
description: Flags that represent the correct GPU configuration including the appropriate frequencies, when the workload level modifies the power level of the context.
ms.assetid: d9c090e6-85f7-4fa1-b156-268155f18142
ms.date: 10/19/2018
ms.topic: struct
f1_keywords:
 - "d3dkmthk/_D3DKMT_TRACKEDWORKLOADSTATEFLAGS"
ms.keywords: _D3DKMT_TRACKEDWORKLOADSTATEFLAGS, D3DKMT_TRACKEDWORKLOADSTATEFLAGS, 
req.header: d3dkmthk.h
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
req.typenames: D3DKMT_TRACKEDWORKLOADSTATEFLAGS
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dkmthk.h
api_name: 
- _D3DKMT_TRACKEDWORKLOADSTATEFLAGS
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# _D3DKMT_TRACKEDWORKLOADSTATEFLAGS structure

## -description

Flags that represent the correct GPU configuration including the appropriate frequencies, when the workload level modifies the power level of the context.

## -struct-fields

### -field Saturated

Driver should set this state flag if the driver cannot go higher than specified. This includes transient states like thermal limits.

The tracked workload is in the current state of execution, and it cannot meet its deadline.

### -field Reserved

Reserved for internal use.

### -field Value
 
The value used to operate over the other members.

## -remarks

## -see-also
