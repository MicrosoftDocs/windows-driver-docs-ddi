---
UID: NS:d3dukmdt._D3DDDI_ALLOCATIONINFO2
title: _D3DDDI_ALLOCATIONINFO2
author: windows-driver-content
description: The D3DDDI_ALLOCATIONINFO2 structure describes an allocation.
ms.assetid: 24bfa783-7a23-4885-9336-7f9102d53b3e
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _D3DDDI_ALLOCATIONINFO2, D3DDDI_ALLOCATIONINFO2, 
req.header: d3dukmdt.h
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
req.typenames: D3DDDI_ALLOCATIONINFO2
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3dukmdt.h
api_name: 
-	_D3DDDI_ALLOCATIONINFO2
product:
-	Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# _D3DDDI_ALLOCATIONINFO2 structure

## -description

The D3DDDI_ALLOCATIONINFO2 structure describes an allocation.

## -struct-fields

### -field hAllocation

[out] Private driver data for the allocation.

### -field hSection

[in] A handle to valid section object.

### -field pSystemMem

[in] A pointer to pre-allocated system memory.

### -field pPrivateDriverData

[in, out, opts] Private data for each allocation.

### -field PrivateDriverDataSize

[in] Size of the private data.

### -field VidPnSourceId

[in] VidPN source ID if this is a primary.

### -field Flags
 
### -field Flags.Primary

Primary.

### -field Flags.Stereo

Stereo.

### -field Flags.OverridePriority

Override priority.

### -field Flags.Reserved

Reserved.

### -field Flags.Value
 
### -field GpuVirtualAddress

[out] GPU Virtual address of the allocation created.

### -field Priority

[in] Priority of allocation.

### -field Unused

Unused.

### -field Reserved
 
Reserved.

## -remarks

## -see-also
