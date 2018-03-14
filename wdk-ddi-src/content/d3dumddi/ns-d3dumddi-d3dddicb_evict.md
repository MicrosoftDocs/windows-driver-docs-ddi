---
UID: NS:d3dumddi.D3DDDICB_EVICT
title: D3DDDICB_EVICT
author: windows-driver-content
description: D3DKMT_EVICT is used with pfnEvictCb to subtract one from the residency reference count.
old-location: display\d3dddicb_evict.htm
old-project: display
ms.assetid: 65743D54-3954-4C31-B3CB-032DE391A456
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDICB_EVICT, D3DDDICB_EVICT structure [Display Devices], d3dumddi/D3DDDICB_EVICT, display.d3dddicb_evict
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDICB_EVICT
product: Windows
targetos: Windows
req.typenames: D3DDDICB_EVICT
---

# D3DDDICB_EVICT structure


## -description


<b>D3DKMT_EVICT</b> is used with <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_evictcb.md">pfnEvictCb</a> to subtract one from the residency reference count.

Once this count reaches zero, it will remove the allocation from the device residency list.
  


## -syntax


````
typedef struct D3DDDICB_EVICT {
  UINT                NumAllocations;
  const D3DKMT_HANDLE *AllocationList;
  D3DDDI_EVICT_FLAGS  Flags;
  UINT64              NumBytesToTrim;
} D3DDDICB_EVICT;
````


## -struct-fields




### -field NumAllocations

[in] Number of allocation handles in the <b>AllocationList</b> array.


### -field AllocationList

[in] An array of <b>NumAllocations</b> allocation handles to mark for eviction. All allocations must be created on <b>hDevice</b>.


### -field Flags

[in] Specifies eviction behavior as documented in <a href="..\d3dukmdt\ns-d3dukmdt-d3dddi_evict_flags.md">D3DDDI_EVICT_FLAGS</a>. 


### -field NumBytesToTrim

[out] When non-zero, specifies how much the application should evict in order to meet its current memory budget.


## -see-also

<a href="..\d3dukmdt\ns-d3dukmdt-d3dddi_evict_flags.md">D3DDDI_EVICT_FLAGS</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_evictcb.md">pfnEvictCb</a>



 

 


