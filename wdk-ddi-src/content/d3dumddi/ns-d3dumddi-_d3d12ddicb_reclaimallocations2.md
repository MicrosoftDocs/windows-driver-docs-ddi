---
UID: NS:d3dumddi._D3D12DDICB_RECLAIMALLOCATIONS2
title: "_D3D12DDICB_RECLAIMALLOCATIONS2"
author: windows-driver-content
description: Describes video memory resources that are to be reclaimed and that the driver previously offered for reuse.
old-location: display\d3d12ddicb_reclaimallocations2.htm
old-project: display
ms.assetid: B5ADCD5D-301C-4B02-A4B2-90A81A5FBBC9
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: display.d3d12ddicb_reclaimallocations2, D3D12DDICB_RECLAIMALLOCATIONS2, D3D12DDICB_RECLAIMALLOCATIONS2 structure [Display Devices], d3dumddi/D3D12DDICB_RECLAIMALLOCATIONS2, _D3D12DDICB_RECLAIMALLOCATIONS2
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3D12DDICB_RECLAIMALLOCATIONS2
product: Windows
targetos: Windows
req.typenames: D3D12DDICB_RECLAIMALLOCATIONS2
---

# _D3D12DDICB_RECLAIMALLOCATIONS2 structure


## -description


Describes video memory resources that are to be reclaimed and that the driver  previously offered  for reuse.


## -syntax


````
typedef struct _D3D12DDICB_RECLAIMALLOCATIONS2 {
  _In_ UINT                                      NumAllocations;
  _In_reads_(NumAllocations) CONST HANDLE        *pResources;
  _In_reads_(NumAllocations) CONST D3DKMT_HANDLE *HandleList;
  _Out_writes_all_opt_(NumAllocations) BOOL      *pDiscarded;
  _Out_ UINT64                                   PagingFenceValue;
} D3D12DDICB_RECLAIMALLOCATIONS2;
````


## -struct-fields




### -field NumAllocations

[in]  The number of items in <b>pDiscarded</b> and whichever of <b>pResources</b> or <b>HandleList</b> is non-NULL.


### -field HandleList

[in]  An array of allocation handles. If non-NULL, <b>pResources</b> must be NULL.


### -field pDiscarded

[out] Optional array of boolean values specifying whether each resource or allocation was discarded.


### -field PagingFenceValue

[out] The paging fence to synchronize against before submitting work to the GPU which
                                                                           references any of the resources or allocations in the provided arrays


#### - pResources

[in]  An array of Direct3D runtime resource handles.

