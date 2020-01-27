---
UID: NS:d3dumddi._D3D12DDICB_RECLAIMALLOCATIONS2
title: _D3D12DDICB_RECLAIMALLOCATIONS2 (d3dumddi.h)
description: Describes video memory resources that are to be reclaimed and that the driver previously offered for reuse.
old-location: display\d3d12ddicb_reclaimallocations2.htm
tech.root: display
ms.assetid: B5ADCD5D-301C-4B02-A4B2-90A81A5FBBC9
ms.date: 05/10/2018
ms.keywords: D3D12DDICB_RECLAIMALLOCATIONS2, D3D12DDICB_RECLAIMALLOCATIONS2 structure [Display Devices], _D3D12DDICB_RECLAIMALLOCATIONS2, d3dumddi/D3D12DDICB_RECLAIMALLOCATIONS2, display.d3d12ddicb_reclaimallocations2
f1_keywords:
 - "d3dumddi/D3D12DDICB_RECLAIMALLOCATIONS2"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- D3D12DDICB_RECLAIMALLOCATIONS2
product:
- Windows
targetos: Windows
req.typenames: D3D12DDICB_RECLAIMALLOCATIONS2
---

# _D3D12DDICB_RECLAIMALLOCATIONS2 structure


## -description


Describes video memory resources that are to be reclaimed and that the driver  previously offered  for reuse.


## -struct-fields




### -field NumAllocations

[in]  The number of items in <b>pDiscarded</b> and whichever of <b>pResources</b> or <b>HandleList</b> is non-NULL.


### -field HandleList

[in]  An array of allocation handles. If non-NULL, <b>pResources</b> must be NULL.


### -field pDiscarded

[out] Optional array of boolean values specifying whether each resource or allocation was discarded.


### -field PagingFenceValue

[out] The paging fence to synchronize against before submitting work to the GPU which references any of the resources or allocations in the provided arrays.



