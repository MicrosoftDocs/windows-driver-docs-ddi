---
UID: NS:d3dkmddi._DXGKARG_DESTROYALLOCATION
title: _DXGKARG_DESTROYALLOCATION (d3dkmddi.h)
description: The DXGKARG_DESTROYALLOCATION structure describes how the display miniport driver should release allocations.
old-location: display\dxgkarg_destroyallocation.htm
ms.assetid: 0679ade4-9bbd-4bbc-ad2a-46bf35cac645
ms.date: 05/10/2018
keywords: ["_DXGKARG_DESTROYALLOCATION structure"]
ms.keywords: DXGKARG_DESTROYALLOCATION, DXGKARG_DESTROYALLOCATION structure [Display Devices], DmStructs_94f4c3be-d0fc-4a34-8cf4-976b68f89899.xml, _DXGKARG_DESTROYALLOCATION, d3dkmddi/DXGKARG_DESTROYALLOCATION, display.dxgkarg_destroyallocation
f1_keywords:
 - "d3dkmddi/DXGKARG_DESTROYALLOCATION"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- DXGKARG_DESTROYALLOCATION
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGKARG_DESTROYALLOCATION
---

# _DXGKARG_DESTROYALLOCATION structure


## -description


The DXGKARG_DESTROYALLOCATION structure describes how the display miniport driver should release allocations.


## -struct-fields




### -field NumAllocations

[in] The number of elements in the array that <b>pAllocationList</b> specifies, which represents the number of allocations to release.


### -field pAllocationList

[in] An array of handles to the allocations to release.


### -field hResource

[in/out] A handle to a resource. The display miniport driver cleans up this handle if it must release the resource along with the allocations.


### -field Flags

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_destroyallocationflags">DXGK_DESTROYALLOCATIONFLAGS</a> structure that identifies how to release the allocations.


## -remarks



The handles in the array that the <b>pAllocationList</b> member specifies are handles to allocations that the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation">DxgkDdiCreateAllocation</a> function previously returned in the <b>hAllocation</b> members of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationinfo">DXGK_ALLOCATIONINFO</a> structures, which are part of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_createallocation">DXGKARG_CREATEALLOCATION</a> structure's <b>pAllocationInfo</b> member. Each allocation handle points to a buffer that contains private driver data for the allocation. The display miniport driver must release the memory for the allocations during the call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_destroyallocation">DxgkDdiDestroyAllocation</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_createallocation">DXGKARG_CREATEALLOCATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationinfo">DXGK_ALLOCATIONINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_destroyallocationflags">DXGK_DESTROYALLOCATIONFLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation">DxgkDdiCreateAllocation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_destroyallocation">DxgkDdiDestroyAllocation</a>
 

 

