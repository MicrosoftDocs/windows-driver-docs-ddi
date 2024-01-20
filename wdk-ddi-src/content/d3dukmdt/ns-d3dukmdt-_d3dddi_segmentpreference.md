---
UID: NS:d3dukmdt._D3DDDI_SEGMENTPREFERENCE
title: D3DDDI_SEGMENTPREFERENCE (d3dukmdt.h)
description: Learn more about the D3DDDI_SEGMENTPREFERENCE structure.
ms.date: 01/19/2024
keywords: ["D3DDDI_SEGMENTPREFERENCE structure"]
ms.keywords: _D3DDDI_SEGMENTPREFERENCE, D3DDDI_SEGMENTPREFERENCE,
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
req.typenames: D3DDDI_SEGMENTPREFERENCE
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _D3DDDI_SEGMENTPREFERENCE
 - d3dukmdt/_D3DDDI_SEGMENTPREFERENCE
 - D3DDDI_SEGMENTPREFERENCE
 - d3dukmdt/D3DDDI_SEGMENTPREFERENCE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _D3DDDI_SEGMENTPREFERENCE
 - D3DDDI_SEGMENTPREFERENCE
dev_langs:
 - c++
---

# D3DDDI_SEGMENTPREFERENCE structure

## -description

The **D3DDI_SEGMENTPREFERENCE** structure describes the preferred segment for a resource allocation.

## -struct-fields

### -field SegmentId0

The identifier of the highest priority preferred segment, or zero if no preferred segment is required. Valid values are from 0 through 31. This member is equivalent to the first 5 bits of the **Value** member.

### -field Direction0

The direction in which **SegmentId0** should be scanned. A value of zero indicates a bottom-up search (that is, low address to high address), and a value of 1 indicates a top-down search (that is, high address to low address). This member is equivalent to the sixth bit of the **Value** member.

### -field SegmentId1

The identifier of the next highest priority preferred segment, or zero if no preferred segment is required. Valid values are from 0 through 31. This member is equivalent to bits 7 through 11 of the **Value** member.

### -field Direction1

The direction in which **SegmentId1** should be scanned. See **Direction0** for a description of the valid values. This member is equivalent to the 12th bit of the **Value** member.

### -field SegmentId2

The identifier of the next highest priority preferred segment, or zero if no preferred segment is required. Valid values are from 0 through 31. This member is equivalent to bits 13 through 17 of the **Value** member.

### -field Direction2

The direction in which **SegmentId2** should be scanned. See **Direction0** for a description of the valid values. This member is equivalent to the 18th bit of the **Value** member.

### -field SegmentId3

The identifier of the next highest priority preferred segment, or zero if no preferred segment is required. Valid values are from 0 through 31. This member is equivalent to bits 19 through 23 of the **Value** member.

### -field Direction3

The direction in which **SegmentId3** should be scanned. See **Direction0** for a description of the valid values. This member is equivalent to the 24th bit of the **Value** member.

### -field SegmentId4

The identifier of the next highest priority preferred segment, or zero if no preferred segment is required. Valid values are from 0 through 31. This member is equivalent to bits 25 through 29 of the **Value** member.

### -field Direction4

The direction in which **SegmentId4** should be scanned. See **Direction0** for a description of the valid values. This member is equivalent to the 30th bit of the **Value** member.

### -field Reserved

Reserved (bits 31-32).

### -field Value

An alternative way to access the segment preference information.

## -remarks

## -see-also

