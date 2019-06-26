---
UID: NS:d3dumddi._D3DDDICB_QUERYRESIDENCY
title: _D3DDDICB_QUERYRESIDENCY (d3dumddi.h)
description: The D3DDDICB_QUERYRESIDENCY structure describes the residency status of a resource or list of allocations.
old-location: display\d3dddicb_queryresidency.htm
tech.root: display
ms.assetid: 43dafaea-06cd-49bb-99ab-99708b1a93cb
ms.date: 05/10/2018
ms.keywords: D3DDDICB_QUERYRESIDENCY, D3DDDICB_QUERYRESIDENCY structure [Display Devices], D3D_param_Structs_196c35e7-414d-465f-b5e5-695848a4c642.xml, _D3DDDICB_QUERYRESIDENCY, d3dumddi/D3DDDICB_QUERYRESIDENCY, display.d3dddicb_queryresidency
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
- d3dumddi.h
api_name:
- D3DDDICB_QUERYRESIDENCY
product:
- Windows
targetos: Windows
req.typenames: D3DDDICB_QUERYRESIDENCY
---

# _D3DDDICB_QUERYRESIDENCY structure


## -description


The D3DDDICB_QUERYRESIDENCY structure describes the residency status of a resource or list of allocations. 


## -struct-fields




### -field hResource

[in] A handle to a resource whose residency is queried. If the user-mode display driver uses the array in the <b>HandleList</b> member to query for residency, it sets <b>hResource</b> to <b>NULL</b>.

If <b>hResource</b> is non-<b>NULL</b>, all allocations that belong to the resource are queried, and the result is returned in the first element of the array that <b>pResidencyStatus</b> points to. The residency status of a resource is equal to the lowest residency status of all allocations that belong to the resource.


### -field NumAllocations

[in] The number of allocations in the <b>HandleList</b> array. If the user-mode display driver sets the handle in the <b>hResource</b> member to non-<b>NULL</b>, it must set <b>NumAllocations</b> to zero.


### -field HandleList

[in] An array of D3DKMT_HANDLE data types that represent kernel-mode handles to the allocations. The Microsoft Direct3D runtime's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_allocatecb">pfnAllocateCb</a> function returns these handles. Therefore, the user-mode display driver uses these handles to query for residency.

If the user-mode display driver sets the handle in the <b>hResource</b> member to non-<b>NULL</b>, it must set <b>HandleList</b> to <b>NULL</b>. 


### -field pResidencyStatus

[out] A pointer to an array of D3DDDI_RESIDENCYSTATUS values. If the <b>hResource</b> member is non-<b>NULL</b>, the array contains a single element and receives one of the following value to indicate the residency status of the resource. If <b>hResource</b> is <b>NULL</b>, the number of elements in the array is specified by the <b>NumAllocations</b> member, and each element receives one of the following values to indicate the residency status of the corresponding allocation in the array that is specified by <b>HandleList</b>. 

| **Value** | **Meaning** | 
|:--|:--|
| D3DDDI_RESIDENCYSTATUS_RESIDENTINGPUMEMORY (1) | The resource or list of allocations reside in GPU memory, which is the highest residency status. | 
| D3DDDI_RESIDENCYSTATUS_RESIDENTINSHAREDMEMORY (2) | The resource or list of allocations reside in shared memory. | 
| D3DDDI_RESIDENCYSTATUS_NOTRESIDENT (3) | The resource or list of allocations is nonresident, which is the lowest residency status. | 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_queryresidencycb">pfnQueryResidencyCb</a>
 

 

