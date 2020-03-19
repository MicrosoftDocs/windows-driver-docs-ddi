---
UID: NS:d3dkmddi._DXGKARG_CREATEALLOCATION
title: _DXGKARG_CREATEALLOCATION (d3dkmddi.h)
description: The DXGKARG_CREATEALLOCATION structure describes how the display miniport driver should create allocations.
old-location: display\dxgkarg_createallocation.htm
ms.assetid: e1464561-b9f2-41aa-921e-84f3a855130f
ms.date: 05/10/2018
keywords: ["_DXGKARG_CREATEALLOCATION structure"]
ms.keywords: "*INOUT_PDXGKARG_CREATEALLOCATION, DXGKARG_CREATEALLOCATION, DXGKARG_CREATEALLOCATION structure [Display Devices], DmStructs_751430a9-4161-4230-bb97-d09600d48d62.xml, _DXGKARG_CREATEALLOCATION, d3dkmddi/DXGKARG_CREATEALLOCATION, display.dxgkarg_createallocation"
f1_keywords:
 - "d3dkmddi/DXGKARG_CREATEALLOCATION"
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
- DXGKARG_CREATEALLOCATION
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGKARG_CREATEALLOCATION
---

# _DXGKARG_CREATEALLOCATION structure


## -description


The DXGKARG_CREATEALLOCATION structure describes how the display miniport driver should create allocations.


## -struct-fields




### -field pPrivateDriverData

[in] A pointer to a block of private data that is passed from the user-mode display driver to the display miniport driver. This member is typically used to provide data for a group of allocations. Note that this member is distinct from the <b>pPrivateDriverData</b> members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationinfo">DXGK_ALLOCATIONINFO</a> structures in the array that <b>pAllocationInfo</b> specifies. You can set private data for this member in addition to private data for each allocation. 


### -field PrivateDriverDataSize

[in] The size, in bytes, of the private data that <b>pPrivateDriverData</b> points to.


### -field NumAllocations

[in] The number of elements in the array that <b>pAllocationInfo</b> specifies, which represents the number of allocations to create.


### -field pAllocationInfo

[in/out] An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationinfo">DXGK_ALLOCATIONINFO</a> structures that describe the allocations to create.


### -field hResource

[in/out] A handle to a resource. The display miniport driver can set this handle to a value that the Microsoft DirectX graphics kernel subsystem can subsequently pass in driver calls and that refers to information for the allocations. If the resource was already created by a previous <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation">DxgkDdiCreateAllocation</a> call, this member contains the handle that the driver previously returned.


### -field Flags

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_createallocationflags">DXGK_CREATEALLOCATIONFLAGS</a> structure that identifies how to create allocations. Setting all of the bit-field flags to 0 indicates that allocations belong to the device and not to a particular resource.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationinfo">DXGK_ALLOCATIONINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_createallocationflags">DXGK_CREATEALLOCATIONFLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation">DxgkDdiCreateAllocation</a>
 

 

