---
UID: NS:d3dukmdt.D3DDDI_MAKERESIDENT
title: D3DDDI_MAKERESIDENT (d3dukmdt.h)
description: D3DDDI_MAKERESIDENT is used with MakeResident (pfnMakeResidentCb or D3DKMTMakeResident) to instruct the OS to add a resource to the device residency list and increment the residency reference count on this allocation.
old-location: display\d3dddi_makeresident.htm
tech.root: display
ms.assetid: 16F04DFD-3AF6-48E0-9BCF-9FE0FC397F91
ms.date: 05/10/2018
keywords: ["D3DDDI_MAKERESIDENT structure"]
ms.keywords: D3DDDI_MAKERESIDENT, D3DDDI_MAKERESIDENT structure [Display Devices], d3dukmdt/D3DDDI_MAKERESIDENT, display.d3dddi_makeresident
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
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
targetos: Windows
req.typenames: D3DDDI_MAKERESIDENT
f1_keywords:
 - D3DDDI_MAKERESIDENT
 - d3dukmdt/D3DDDI_MAKERESIDENT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - D3DDDI_MAKERESIDENT
---

# D3DDDI_MAKERESIDENT structure


## -description

<b>D3DDDI_MAKERESIDENT</b> is used with <b>MakeResident</b> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_makeresidentcb">pfnMakeResidentCb</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtmakeresident">D3DKMTMakeResident</a>) to instruct the OS to add a resource to the device residency list and increment the residency reference count on this allocation.

## -struct-fields

### -field hPagingQueue

[in] Paging queue on the device that created the input allocations. This queue will be used for residency operations.

### -field NumAllocations

[in/out] On input, the number of allocation handles in the <b>AllocationList</b> array and allocation priority values in the <b>PriorityList</b> array. On output,
                                                    the number of allocations successfully made resident.

### -field AllocationList

[in] An array of <b>NumAllocations</b> allocation handles to make resident. All allocations must be created on the device <b>hPagingQueue</b> is created for.

### -field PriorityList

[in] An array of <b>NumAllocations</b> specifying residency priority for each of the input allocations. This value is currently ignored and may be set to <b>NULL</b>.

### -field Flags

[in] Specifies memory residency behavior as documented in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-d3dddi_makeresident_flags">D3DDDI_MAKERESIDENT_FLAGS</a>.

### -field PagingFenceValue

[out] When <b>MakeResident</b> returns <b>E_PENDING</b>, this member indicates the paging queue fence value to wait on.

### -field NumBytesToTrim

[out] When <b>MakeResident</b> returns <b>E_OUTOFMEMORY</b>, this member indicates the number of bytes over budget the application would be if the allocation(s) were made resident.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-d3dddi_makeresident_flags">D3DDDI_MAKERESIDENT_FLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtmakeresident">D3DKMTMakeResident</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_makeresidentcb">pfnMakeResidentCb</a>

