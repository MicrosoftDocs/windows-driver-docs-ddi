---
UID: NS:d3dkmthk._D3DKMT_GETALLOCATIONPRIORITY
title: _D3DKMT_GETALLOCATIONPRIORITY (d3dkmthk.h)
description: Used to get allocation priorities.
ms.assetid: a1feb30f-9d43-46ba-b412-e4babebe1609
ms.date: 10/19/2018
ms.topic: struct
f1_keywords:
 - "d3dkmthk/_D3DKMT_GETALLOCATIONPRIORITY"
ms.keywords: _D3DKMT_GETALLOCATIONPRIORITY, D3DKMT_GETALLOCATIONPRIORITY, 
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
req.typenames: D3DKMT_GETALLOCATIONPRIORITY
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dkmthk.h
api_name: 
- _D3DKMT_GETALLOCATIONPRIORITY
product:
- Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# _D3DKMT_GETALLOCATIONPRIORITY structure

## -description

Used to get allocation priorities.

## -struct-fields

### -field hDevice

[in] A handle to the device.

### -field hResource

[in] A handle for this resource in this process.

### -field phAllocationList

[in] Pointer to an array allocation to get priorities of.

### -field AllocationCount

[in] Number of allocations in *phAllocationList*.

### -field pPriorities
 
[out] Priority for each of the allocation in the array.

## -remarks

## -see-also
