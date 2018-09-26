---
UID: NS:d3d12umddi.D3D12DDIARG_PRESENT_0001
title: D3D12DDIARG_PRESENT_0001
author: windows-driver-content
description: Describes a resource to display.
ms.assetid: 25bbfe02-c536-4b74-b9b1-ee7a585db027
ms.author: windowsdriverdev
ms.date: 
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: D3D12DDIARG_PRESENT_0001, D3D12DDIARG_PRESENT_0001, 
req.header: d3d12umddi.h
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
req.typenames: D3D12DDIARG_PRESENT_0001
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDIARG_PRESENT_0001
product:
-	Windows
targetos: Windows
---

# D3D12DDIARG_PRESENT_0001 structure

## -description


## -struct-fields

### -field phSurfacesToPresent

A array of surface handles to display or to release.

### -field SurfacesToPresent

The surfaces to display or to release.

### -field hDstResource

A handle to the destination resource to display to.

### -field DstSubResourceIndex

The zero-based index into the destination resource, which is specified by the handle in the *hDstResource* member. This index indicates the subresource or surface to display to.

### -field Flags

Identifies, in bit-field flags, how to display.

### -field FlipInterval

Indicates the flip interval. That is, if the flip occurs after zero, one, two, three, or four vertical syncs.

### -field VidPnSourceID
 
### -field pDirtyRects

A pointer to an array of dirty rectangles, that indicate the portion of the overlay plane that has changed.

### -field DirtyRects

The number of dirty rectangles in the array pointed to by *pDirtyRects*.

### -field PrivateDriverDataSize

Private driver data size in bytes. 

### -field pPrivateDriverData

Private driver data.

### -field OptimizeForComposition
 
DWM is involved in composition.

## -remarks

## -see-also