---
UID: NS:d3dkmthk._D3DKMT_QUERYVIDEOMEMORYINFO
title: _D3DKMT_QUERYVIDEOMEMORYINFO
author: windows-driver-content
description: Used to query for video memory info.
ms.assetid: 6ddd12f9-abd8-4e9a-b1e5-193956a5f9dd
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _D3DKMT_QUERYVIDEOMEMORYINFO, D3DKMT_QUERYVIDEOMEMORYINFO, 
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
req.typenames: D3DKMT_QUERYVIDEOMEMORYINFO
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3dkmthk.h
api_name: 
-	_D3DKMT_QUERYVIDEOMEMORYINFO
product:
-	Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# _D3DKMT_QUERYVIDEOMEMORYINFO structure

## -description

Used to query for video memory info.

## -struct-fields

### -field hProcess

[in, opt] A handle to the process.
 
### -field hAdapter

[in] A handle to the graphics adapter.

### -field MemorySegmentGroup

[in] The memory segment group to query.

### -field Budget

[out] The total memory the application may use.

### -field CurrentUsage

[out] The current memory usage of the device.

### -field CurrentReservation

[out] The current reservation of the device.

### -field AvailableForReservation

[out] The total that the device may reserve.

### -field PhysicalAdapterIndex
 
[in] The physical adapter index in the LDA (linked display adapter) chain.

## -remarks

## -see-also
