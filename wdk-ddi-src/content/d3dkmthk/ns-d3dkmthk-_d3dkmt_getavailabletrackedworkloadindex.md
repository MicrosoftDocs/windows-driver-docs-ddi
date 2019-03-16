---
UID: NS:d3dkmthk._D3DKMT_GETAVAILABLETRACKEDWORKLOADINDEX
title: _D3DKMT_GETAVAILABLETRACKEDWORKLOADINDEX (d3dkmthk.h)
description: Gets the available tracked workload index.
ms.assetid: 8a64867d-86b3-4d6e-a029-06ae7437133b
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _D3DKMT_GETAVAILABLETRACKEDWORKLOADINDEX, D3DKMT_GETAVAILABLETRACKEDWORKLOADINDEX, 
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
req.typenames: D3DKMT_GETAVAILABLETRACKEDWORKLOADINDEX
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dkmthk.h
api_name: 
- _D3DKMT_GETAVAILABLETRACKEDWORKLOADINDEX
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# _D3DKMT_GETAVAILABLETRACKEDWORKLOADINDEX structure

## -description

Gets the available tracked workload index.

## -struct-fields

### -field hDevice

A handle to the device context.

### -field hTrackedWorkload

A handle to the tracked workload instance.

### -field FenceCompletedValue

The fence value for the completed workloads.

### -field AvailableTrackedWorkloadIndex
 
[out] The first available tracked workload index.

## -remarks

## -see-also
