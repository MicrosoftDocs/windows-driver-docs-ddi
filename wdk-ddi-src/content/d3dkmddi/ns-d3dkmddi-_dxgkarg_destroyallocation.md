---
UID: NS:d3dkmddi._DXGKARG_DESTROYALLOCATION
title: "_DXGKARG_DESTROYALLOCATION"
author: windows-driver-content
description: The DXGKARG_DESTROYALLOCATION structure describes how the display miniport driver should release allocations.
old-location: display\dxgkarg_destroyallocation.htm
old-project: display
ms.assetid: 0679ade4-9bbd-4bbc-ad2a-46bf35cac645
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKARG_DESTROYALLOCATION, DXGKARG_DESTROYALLOCATION structure [Display Devices], DmStructs_94f4c3be-d0fc-4a34-8cf4-976b68f89899.xml, _DXGKARG_DESTROYALLOCATION, d3dkmddi/DXGKARG_DESTROYALLOCATION, display.dxgkarg_destroyallocation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGKARG_DESTROYALLOCATION
product: Windows
targetos: Windows
req.typenames: DXGKARG_DESTROYALLOCATION
---

# _DXGKARG_DESTROYALLOCATION structure


## -description


The DXGKARG_DESTROYALLOCATION structure describes how the display miniport driver should release allocations.


## -syntax


````
typedef struct _DXGKARG_DESTROYALLOCATION {
  UINT                        NumAllocations;
  const HANDLE                *pAllocationList;
  HANDLE                      hResource;
  DXGK_DESTROYALLOCATIONFLAGS Flags;
} DXGKARG_DESTROYALLOCATION;
````


## -struct-fields




### -field NumAllocations

[in] The number of elements in the array that <b>pAllocationList</b> specifies, which represents the number of allocations to release.


### -field pAllocationList

[in] An array of handles to the allocations to release.


### -field hResource

[in/out] A handle to a resource. The display miniport driver cleans up this handle if it must release the resource along with the allocations.


### -field Flags

[in] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_destroyallocationflags.md">DXGK_DESTROYALLOCATIONFLAGS</a> structure that identifies how to release the allocations.


## -remarks



The handles in the array that the <b>pAllocationList</b> member specifies are handles to allocations that the driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a> function previously returned in the <b>hAllocation</b> members of <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfo.md">DXGK_ALLOCATIONINFO</a> structures, which are part of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createallocation.md">DXGKARG_CREATEALLOCATION</a> structure's <b>pAllocationInfo</b> member. Each allocation handle points to a buffer that contains private driver data for the allocation. The display miniport driver must release the memory for the allocations during the call to <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_destroyallocation.md">DxgkDdiDestroyAllocation</a>. 




## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_destroyallocationflags.md">DXGK_DESTROYALLOCATIONFLAGS</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_destroyallocation.md">DxgkDdiDestroyAllocation</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfo.md">DXGK_ALLOCATIONINFO</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createallocation.md">DXGKARG_CREATEALLOCATION</a>



 

 


