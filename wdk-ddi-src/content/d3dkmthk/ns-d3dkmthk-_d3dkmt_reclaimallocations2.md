---
UID: NS:d3dkmthk._D3DKMT_RECLAIMALLOCATIONS2
title: "_D3DKMT_RECLAIMALLOCATIONS2"
author: windows-driver-content
description: D3DKMT_RECLAIMALLOCATIONS2 describes video memory resources that are to be reclaimed and that the driver previously offered for reuse. Used with the D3DKMTReclaimAllocations2 function.
old-location: display\d3dkmt_reclaimallocations2.htm
old-project: display
ms.assetid: 7980F1FD-D7C2-4C74-8652-89FD38BE4D1F
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_D3DKMT_RECLAIMALLOCATIONS2, D3DKMT_RECLAIMALLOCATIONS2, display.d3dkmt_reclaimallocations2, D3DKMT_RECLAIMALLOCATIONS2 structure [Display Devices], d3dkmthk/D3DKMT_RECLAIMALLOCATIONS2"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
-	D3dkmthk.h
apiname:
-	D3DKMT_RECLAIMALLOCATIONS2
product: Windows
targetos: Windows
req.typenames: D3DKMT_RECLAIMALLOCATIONS2
---

# _D3DKMT_RECLAIMALLOCATIONS2 structure


## -description


<b>D3DKMT_RECLAIMALLOCATIONS2</b> describes video memory resources that are to be reclaimed and that the driver  previously offered  for reuse. Used with the  <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtreclaimallocations2.md">D3DKMTReclaimAllocations2</a> function.


## -syntax


````
typedef struct _D3DKMT_RECLAIMALLOCATIONS2 {
  D3DKMT_HANDLE       hPagingQueue;
  UINT                NumAllocations;
  D3DKMT_HANDLE       *pResources;
  const D3DKMT_HANDLE *HandleList;
  union {
    BOOL                   *pDiscarded;
    D3DDDI_RECLAIM_RESULT* pResults;
  };
  UINT64              PagingFenceValue;
} D3DKMT_RECLAIMALLOCATIONS2;
````


## -struct-fields




### -field hPagingQueue

[in] A handle to the device that created the allocations.


### -field NumAllocations

[in] The number of items in the <b>pResources</b>, <b>HandleList</b>, or  <b>pDiscarded</b> members, whichever is not <b>NULL</b>.


### -field pResources

[in] An array of <b>D3DKMT_HANDLE</b> data types that represent Direct3D runtime resource handles.


### -field HandleList

[in] An array of <b>D3DKMT_HANDLE</b> data types that represent kernel-mode handles to the allocations that are to be reclaimed.

If <b>HandleList</b> is not <b>NULL</b>, the <b>pResources</b> member must be <b>NULL</b>.


### -field pResults

[in] Required array of values specifying whether the surface is valid, discarded, or list commitment.


### -field pDiscarded

[out] Optional array of boolean variables  specifying whether each resource or allocation was discarded.


### -field PagingFenceValue

The paging fence to synchronize against before submitting work to the GPU which references any of the resources or allocations in the provided arrays.

