---
UID: NS:d3dkmthk._D3DKMT_CHANGEVIDEOMMEMORYRESERVATION
title: _D3DKMT_CHANGEVIDEOMMEMORYRESERVATION (d3dkmthk.h)
description: Used to change the video memory management reservation.
ms.assetid: e0af83c8-8fce-45ba-9449-ac45a638d287
ms.date: 10/19/2018
keywords: ["_D3DKMT_CHANGEVIDEOMMEMORYRESERVATION structure"]
f1_keywords:
 - "d3dkmthk/_D3DKMT_CHANGEVIDEOMMEMORYRESERVATION"
 - "_D3DKMT_CHANGEVIDEOMMEMORYRESERVATION"
ms.keywords: _D3DKMT_CHANGEVIDEOMMEMORYRESERVATION, D3DKMT_CHANGEVIDEOMEMORYRESERVATION, 
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
req.typenames: D3DKMT_CHANGEVIDEOMEMORYRESERVATION
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dkmthk.h
api_name: 
- _D3DKMT_CHANGEVIDEOMMEMORYRESERVATION
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# _D3DKMT_CHANGEVIDEOMMEMORYRESERVATION structure

## -description

Used to change the video memory management reservation.

## -struct-fields

### -field hProcess

[in, opt] A handle to a process. If NULL, the current process is used. The process handle must be opened with PROCESS_SET_INFORMATION privileges.

### -field hAdapter

[in] A handle to the graphics adapter.

### -field MemorySegmentGroup

[in] The memory segment group to change reservation for.

### -field Reservation

[in] Desired reservation in the range between 0 and AvailableForReservation returned by [QueryVideoMemoryInfo](nf-d3dkmthk-d3dkmtqueryvideomemoryinfo.md).

### -field PhysicalAdapterIndex
 
[in] Zero based physical adapter index in the LDA (linked display adapter) configuration.

## -remarks

## -see-also
