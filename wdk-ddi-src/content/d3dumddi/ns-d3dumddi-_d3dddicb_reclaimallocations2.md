---
UID: NS:d3dumddi._D3DDDICB_RECLAIMALLOCATIONS2
title: _D3DDDICB_RECLAIMALLOCATIONS2 (d3dumddi.h)
description: D3DDDICB_RECLAIMALLOCATIONS2 is used with pfnReclaimAllocations2Cb to describe video memory resources, previously offered for reuse by the driver, that are to be reclaimed.
old-location: display\d3dddicb_reclaimallocations2.htm
tech.root: display
ms.assetid: 952935E2-3216-40E5-8A4E-AA5D5E584F12
ms.date: 05/10/2018
ms.keywords: D3DDDICB_RECLAIMALLOCATIONS2, D3DDDICB_RECLAIMALLOCATIONS2 structure [Display Devices], _D3DDDICB_RECLAIMALLOCATIONS2, d3dumddi/D3DDDICB_RECLAIMALLOCATIONS2, display.d3dddicb_reclaimallocations2
ms.topic: struct
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
- D3DDDICB_RECLAIMALLOCATIONS2
product:
- Windows
targetos: Windows
req.typenames: D3DDDICB_RECLAIMALLOCATIONS2
---

# _D3DDDICB_RECLAIMALLOCATIONS2 structure


## -description


<b>D3DDDICB_RECLAIMALLOCATIONS2</b> is used with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_reclaimallocations2cb">pfnReclaimAllocations2Cb</a> to describe video memory resources, previously offered for reuse by the driver,  that are to be reclaimed.


## -struct-fields




### -field PagingQueue

[in] The paging queue, supplied by the user-mode driver, to page in the allocation list.


### -field NumAllocations

[in]  The number of items in <b>pDiscarded</b> and whichever of <b>pResources</b> or <b>HandleList</b> is non-NULL.


### -field pResources

[in]  An array of Direct3D runtime resource handles.


### -field HandleList

[in]  An array of allocation handles. If non-NULL, <b>pResources</b> must be NULL.


### -field pDiscarded

[out] Optional array of boolean values specifying whether each resource or allocation was discarded.


### -field PagingFenceValue

[out] The paging fence to synchronize against before submitting work to the GPU which
                                                                           references any of the resources or allocations in the provided arrays

