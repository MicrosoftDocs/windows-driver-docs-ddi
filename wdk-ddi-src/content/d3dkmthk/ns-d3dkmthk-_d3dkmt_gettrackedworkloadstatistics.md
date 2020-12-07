---
UID: NS:d3dkmthk._D3DKMT_GETTRACKEDWORKLOADSTATISTICS
title: _D3DKMT_GETTRACKEDWORKLOADSTATISTICS (d3dkmthk.h)
description: Retrieves the rolling statistics for the tracked workload.
ms.date: 10/19/2018
keywords: ["D3DKMT_GETTRACKEDWORKLOADSTATISTICS structure"]
f1_keywords:
 - "d3dkmthk/_D3DKMT_GETTRACKEDWORKLOADSTATISTICS"
 - "_D3DKMT_GETTRACKEDWORKLOADSTATISTICS"
ms.keywords: _D3DKMT_GETTRACKEDWORKLOADSTATISTICS, D3DKMT_GETTRACKEDWORKLOADSTATISTICS, 
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
req.typenames: D3DKMT_GETTRACKEDWORKLOADSTATISTICS
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dkmthk.h
api_name: 
- _D3DKMT_GETTRACKEDWORKLOADSTATISTICS
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# _D3DKMT_GETTRACKEDWORKLOADSTATISTICS structure

## -description

Retrieves the rolling statistics for the tracked workload.

## -struct-fields

### -field hDevice

A handle to the device context.

### -field hTrackedWorkload

A handle to the tracked workload instance.

### -field DeadlineOffsetHundredsNS

Statistics for the offset of the deadline achieved of the tracked workload, in hundreds of nanoseconds.

### -field MissedDeadlines

Count of the missed deadlines of the tracked workload.

### -field Flags
 
Indicates the state of the current workload tracking.

## -remarks

## -see-also
