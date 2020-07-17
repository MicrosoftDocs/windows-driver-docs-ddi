---
UID: NS:d3dkmthk._D3DKMT_DESTROYALLOCATION2
title: _D3DKMT_DESTROYALLOCATION2 (d3dkmthk.h)
description: The D3DKMT_DESTROYALLOCATION2 structure describes parameters for releasing allocations with D3DKMTDestroyAllocation2.
old-location: display\d3dkmt_destroyallocation2.htm
ms.assetid: A51C5F98-5979-436A-9E7E-EA54A1469940
ms.date: 05/10/2018
keywords: ["_D3DKMT_DESTROYALLOCATION2 structure"]
ms.keywords: D3DKMT_DESTROYALLOCATION2, D3DKMT_DESTROYALLOCATION2 structure [Display Devices], _D3DKMT_DESTROYALLOCATION2, d3dkmthk/D3DKMT_DESTROYALLOCATION2, display.d3dkmt_destroyallocation2
f1_keywords:
 - "d3dkmthk/D3DKMT_DESTROYALLOCATION2"
 - "D3DKMT_DESTROYALLOCATION2"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmthk.h
api_name:
- D3DKMT_DESTROYALLOCATION2
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_DESTROYALLOCATION2
---

# _D3DKMT_DESTROYALLOCATION2 structure


## -description


The <b>D3DKMT_DESTROYALLOCATION2</b> structure describes parameters for releasing allocations with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtdestroyallocation2">D3DKMTDestroyAllocation2</a>.


## -struct-fields




### -field hDevice

[in] A <b>D3DKMT_HANDLE</b> data type that represents a kernel-mode handle to the device that the resource, allocations, or both are associated with.


### -field hResource

[in] A <b>D3DKMT_HANDLE</b> data type that represents a kernel-mode handle to the resource that is associated with the allocations when releasing a resource. If a resource handle is specified, all of the allocations that are associated with it are automatically released.


### -field phAllocationList

[in] An array of <b>D3DKMT_HANDLE</b> data types that represent kernel-mode handles to the allocations. If any allocation in the list is associated with a resource, all of the allocations in the list must also be associated with the same resource. If the OpenGL installable client driver sets the handle in the <b>hResource</b> member to a non-<b>NULL</b> value, the installable client driver must set <b>phAllocationList</b> to <b>NULL</b>.


### -field AllocationCount

[in] The number of allocations in the array that <b>phAllocationList</b> specifies. If the OpenGL installable client driver sets the handle in the <b>hResource</b> member to a non-<b>NULL</b> value, the <b>AllocationCount</b> member is ignored by the OpenGL runtime.


### -field Flags

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddicb_destroyallocation2flags">D3DDDICB_DESTROYALLOCATION2FLAGS</a> structure that contains additional details about the operation.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddicb_destroyallocation2flags">D3DDDICB_DESTROYALLOCATION2FLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtdestroyallocation2">D3DKMTDestroyAllocation2</a>
 

 

