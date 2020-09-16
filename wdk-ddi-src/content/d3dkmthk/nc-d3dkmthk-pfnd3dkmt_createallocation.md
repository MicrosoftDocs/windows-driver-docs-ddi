---
UID: NC:d3dkmthk.PFND3DKMT_CREATEALLOCATION
title: PFND3DKMT_CREATEALLOCATION (d3dkmthk.h)
description: The D3DKMTCreateAllocation function creates allocations of system or video memory.
old-location: display\d3dkmtcreateallocation.htm
ms.assetid: 1374ad6f-3a79-4db1-acc9-28c8bd9aa93d
ms.date: 05/10/2018
keywords: ["PFND3DKMT_CREATEALLOCATION callback function"]
ms.keywords: D3DKMTCreateAllocation, D3DKMTCreateAllocation callback function [Display Devices], OpenGL_Functions_dfd80d2b-c3c7-4aca-833c-153090153b96.xml, PFND3DKMT_CREATEALLOCATION, PFND3DKMT_CREATEALLOCATION callback, d3dkmthk/D3DKMTCreateAllocation, display.d3dkmtcreateallocation
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3DKMT_CREATEALLOCATION
 - d3dkmthk/PFND3DKMT_CREATEALLOCATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMTCreateAllocation
---

# PFND3DKMT_CREATEALLOCATION callback function


## -description

The <b>D3DKMTCreateAllocation</b> function creates allocations of system or video memory.

## -parameters

### -param Arg1

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_createallocation">D3DKMT_CREATEALLOCATION</a> structure that contains information for creating allocations.

## -returns

<b>D3DKMTCreateAllocation</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | Allocations were successfully created. | 
| **STATUS_DEVICE_REMOVED** | The graphics adapter was stopped or the display device was reset. | 
| **STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect. | 
| **STATUS_NO_MEMORY** | [D3DKMTCreateAllocation](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreateallocation)  could not complete because of insufficient memory. | 
| **STATUS_NO_VIDEO_MEMORY** | [D3DKMTCreateAllocation](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreateallocation)  could not complete because of insufficient video memory. The video memory manager attempts to virtualize video memory; however, if the virtualization fails (such as, when virtual address space runs out), the memory manager might return this error code. | 

This function might also return other NTSTATUS values.

## -remarks

The OpenGL ICD uses the <b>D3DKMTCreateAllocation</b> function to create allocations and resources. An allocation can be associated with a resource, or an allocation can stand alone. The <b>D3DKMTCreateAllocation</b> function can also be used to add additional allocations to a resource at anytime. The only restrictions are that all shared allocations must be associated with a resource and additional allocations cannot be added to an existing shared resource.

#### Examples

The following code example demonstrates how an OpenGL ICD can use <b>D3DKMTCreateAllocation</b> to create a stand-alone allocation in video memory that is not associated with a resource.

```cpp
D3DKMT_HANDLE CreateStandAloneAllocation(D3DKMT_HANDLE hDevice, VOID* pPrivateAllocationInfo, UINT Size)
{
    D3DKMT_CREATEALLOCATION CreateAllocation;
    D3DDDI_ALLOCATIONINFO AllocationInfo;

    memset(&CreateAllocation, 0, sizeof(CreateAllocation));
    CreateAllocation.hDevice = hDevice;
    CreateAllocation.NumAllocations = 1;
    CreateAllocation.pAllocationInfo = &AllocationInfo;

    AllocationInfo.hAllocation = NULL;
    AllocationInfo.pSystemMem = NULL;  // Vidmem allocation
    AllocationInfo.pPrivateDriverData = pPrivateAllocationInfo;  // Contains format, size, and so on.
    AllocationInfo.PrivateDriverDataSize = Size;

    if (NT_SUCCESS((*pfnKTCreateAllocation)(&CreateAllocation))) {
        return AllocationInfo.hAllocation;
    }
    return 0;
}
```

The following code example demonstrates how an OpenGL ICD can use <b>D3DKMTCreateAllocation</b> to create a resource with a single system memory allocation.

```cpp
HRESULT CreateSysmemResource(D3DKMT_HANDLE hDevice, 
                             UINT AllocationSize, 
                             VOID* pResourceData, 
                             UINT ResourceDataSize,
                             VOID* pAllocationData, 
                             UINT AllocationDataSize,
                             D3DKMT_HANDLE* phResource,
                             D3DKMT_HANDLE* phAllocation)
{
    D3DKMT_CREATEALLOCATION CreateAllocation;
    D3DDDI_ALLOCATIONINFO AllocationInfo;
    VOID* pSysMem;

    *phResource = NULL;
    *phAllocation = NULL;

    // For a sysmem allocation, preallocate the memory.
    pSysMem = MemAlloc(AllocationSize);
    if (pSysMem == NULL) {
        return E_OUTOFMEMORY;
    }
 
    memset(&CreateAllocation, 0, sizeof(CreateAllocation));
    CreateAllocation.hDevice = hDevice;
    CreateAllocation.Flags.CreateResource = TRUE;
    CreateAllocation.pPrivateDriverData = pResourceData;
    CreateAllocation.PrivateDriverDataSize = ResourceDataSize;
    CreateAllocation.NumAllocations = 1;
    CreateAllocation.pAllocationInfo = &AllocationInfo;

    AllocationInfo.hAllocation = NULL;
    AllocationInfo.pSystemMem = pSysMem;
    AllocationInfo.pPrivateDriverData = pAllocationData;
    AllocationInfo.PrivateDriverDataSize = AllocationDataSize;

    if (NT_SUCCESS((*pfnKTCreateAllocation)(&CreateAllocation))) {
        *phResource = CreateAllocation.hResource;
        *phAllocation = AllocationInfo.hAllocation;
        return S_OK;
    }
    MemFree(pSysMem);
    return E_FAIL;
}
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_createallocation">D3DKMT_CREATEALLOCATION</a>

