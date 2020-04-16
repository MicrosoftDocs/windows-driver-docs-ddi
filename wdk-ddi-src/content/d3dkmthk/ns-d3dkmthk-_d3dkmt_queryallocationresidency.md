---
UID: NS:d3dkmthk._D3DKMT_QUERYALLOCATIONRESIDENCY
title: _D3DKMT_QUERYALLOCATIONRESIDENCY (d3dkmthk.h)
description: The D3DKMT_QUERYALLOCATIONRESIDENCY structure describes information for retrieving the residency status from a resource or list of allocations.
old-location: display\d3dkmt_queryallocationresidency.htm
ms.assetid: 53dd0306-4dcc-47a0-aa98-67d289c93b9b
ms.date: 05/10/2018
keywords: ["_D3DKMT_QUERYALLOCATIONRESIDENCY structure"]
ms.keywords: D3DKMT_QUERYALLOCATIONRESIDENCY, D3DKMT_QUERYALLOCATIONRESIDENCY structure [Display Devices], OpenGL_Structs_eae296e3-82c5-4229-b31a-bdb85d7e6c0c.xml, _D3DKMT_QUERYALLOCATIONRESIDENCY, d3dkmthk/D3DKMT_QUERYALLOCATIONRESIDENCY, display.d3dkmt_queryallocationresidency
f1_keywords:
 - "d3dkmthk/D3DKMT_QUERYALLOCATIONRESIDENCY"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
- d3dkmthk.h
api_name:
- D3DKMT_QUERYALLOCATIONRESIDENCY
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_QUERYALLOCATIONRESIDENCY
---

# _D3DKMT_QUERYALLOCATIONRESIDENCY structure


## -description


The D3DKMT_QUERYALLOCATIONRESIDENCY structure describes information for retrieving the residency status from a resource or list of allocations. 


## -struct-fields




### -field hDevice

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the device that the resource or list of allocations are associated with.


### -field hResource

[in] A handle to a resource whose residency is queried. If the OpenGL ICD uses the array that <b>phAllocationList</b> specifies to query for residency, it sets <b>hResource</b> to <b>NULL</b>. If the OpenGL ICD sets <b>hResource</b> to a non-<b>NULL</b> value, it must set the <b>AllocationCount</b> member to zero and <b>phAllocationList</b> to <b>NULL</b>. 

If <b>hResource</b> is non-<b>NULL</b>, all of the allocations that belong to the resource are queried, and the result is returned in the first element of the array that <b>pResidencyStatus</b> points to. 

If any allocation that belongs to the resource is not resident, the entire resource is considered not resident.

To retrieve detailed residency information about each allocation that belongs to a resource, the allocation must be queried.


### -field phAllocationList

[in] An array of D3DKMT_HANDLE data types that represent kernel-mode handles to the allocations. The OpenGL ICD uses these handles to query for residency status. 

If the OpenGL ICD sets the handle in the <b>hResource</b> member to a non-<b>NULL</b> value, it must set <b>phAllocationList</b> to <b>NULL</b>. 


### -field AllocationCount

[in] The number of allocations in the array that <b>phAllocationList</b> specifies. If the OpenGL ICD sets the handle in the <b>hResource</b> member to a non-<b>NULL</b> value, it must set <b>AllocationCount</b> to zero.


### -field pResidencyStatus

[out] A pointer to an array of D3DKMT_ALLOCATIONRESIDENCYSTATUS enumerators. If the <b>hResource</b> member is non-<b>NULL</b>, the array contains a single element and receives one of the enumerators that are listed in the following table to indicate the residency status of the resource. If <b>hResource</b> is <b>NULL</b>, the number of elements in the array is specified by the <b>AllocationCount</b> member, and each element receives one of the following enumerators to indicate the residency status of the corresponding allocation in the <b>phAllocationList</b> array.

|Enumerator|Meaning|
|--- |--- |
|D3DKMT_ALLOCATIONRESIDENCYSTATUS_RESIDENTINGPUMEMORY (1)|The resource or allocation resides in GPU memory.|
|D3DKMT_ALLOCATIONRESIDENCYSTATUS_RESIDENTINSHAREDMEMORY (2)|The resource or allocation resides in shared memory.|
|D3DKMT_ALLOCATIONRESIDENCYSTATUS_NOTRESIDENT (3)|The resource or allocation is nonresident.|

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtqueryallocationresidency">D3DKMTQueryAllocationResidency</a>
 

 

