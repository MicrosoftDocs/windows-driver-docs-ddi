---
UID: NC:d3dumddi.PFND3DDDI_ALLOCATECB
title: PFND3DDDI_ALLOCATECB (d3dumddi.h)
description: The pfnAllocateCb function allocates system or video memory.
old-location: display\pfnallocatecb.htm
tech.root: display
ms.assetid: a61e6c6a-3992-429c-ad8c-5f1a61dc7b8b
ms.date: 05/10/2018
ms.keywords: D3Druntime_Functions_1339f95d-018f-4153-b5b8-6753c38babd7.xml, PFND3DDDI_ALLOCATECB, PFND3DDDI_ALLOCATECB callback, d3dumddi/pfnAllocateCb, display.pfnallocatecb, pfnAllocateCb, pfnAllocateCb callback function [Display Devices]
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
- UserDefined
api_location:
- d3dumddi.h
api_name:
- pfnAllocateCb
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_ALLOCATECB callback function


## -description


The <b>pfnAllocateCb</b> function allocates system or video memory.


## -parameters




### -param hDevice 

[in] A handle to the display device (graphics context).


### -param *

*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544137">D3DDDICB_ALLOCATE</a> structure that describes the allocation.


## -returns



<b>pfnAllocateCb</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The memory was successfully allocated. | 
| **E_INVALIDARG** | Parameters were validated and determined to be incorrect. | 
| **E_OUTOFMEMORY** | pfnAllocateCb could not allocate memory that was required for it to complete. | 
| **D3DERR_OUTOFVIDEOMEMORY** | pfnAllocateCb could not complete because of insufficient video memory. The video memory manager attempts to virtualize video memory; however, if the virtualization fails (such as, when virtual address space runs out), the memory manager might return this error code. | 
| **D3DDDIERR_DEVICEREMOVED** | pfnAllocateCb could not initiate a call to the display miniport driver's [DxgkDdiCreateAllocation](https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2) function because a Plug and Play (PnP) stop or a Timeout Detection and Recovery (TDR) event occurred. The user-mode display driver function that called pfnAllocateCb (typically, the [CreateResource](https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83), [CreateResource(D3D10)](https://msdn.microsoft.com/c21839f0-8302-49f9-a2b4-4009fbd2d88c), or [CreateResource(D3D11)](https://msdn.microsoft.com/2dff9d2e-c497-422f-824b-a7101904fd67) function) must return this error code back to the Direct3D runtime. <br/>**Direct3D Version 9** Note:  For more information about returning error codes, see [Returning Error Codes Received from Runtime Functions](https://msdn.microsoft.com/4a2384e8-407f-4248-8b31-7c4e836b15dc).<br/>**Direct3D Versions 10 and 11** Note:  If the driver function does not return a value (that is, has VOID for a return parameter type), the driver function calls the [pfnSetErrorCb](https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f) function to send an error code back to the runtime. For more information about handling error codes, see [Handling Errors](https://msdn.microsoft.com/ac4e056e-3304-4934-887a-5cc2b87989bd). | 


This function might also return other HRESULT values.




## -remarks



A user-mode display driver calls <b>pfnAllocateCb</b> to allocate system or video memory (also known as an <i>allocation</i>). The Microsoft DirectX graphics kernel subsystem (<i>Dxgkrnl.sys</i>) then calls the display miniport driver's <a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a> function to interpret and store the private data that was passed in the <b>pfnAllocateCb</b> request. The display miniport driver returns information from the <i>DxgkDdiCreateAllocation</i> call that the video memory manager (which is part of <i>Dxgkrnl.sys</i>) uses to actually allocate the memory. 

The user-mode display driver typically creates an allocation in response to a call to its <a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a>, <a href="https://msdn.microsoft.com/c21839f0-8302-49f9-a2b4-4009fbd2d88c">CreateResource(D3D10)</a>, or <a href="https://msdn.microsoft.com/2dff9d2e-c497-422f-824b-a7101904fd67">CreateResource(D3D11)</a> function. However, the user-mode display driver can create an allocation at anytime--for example, when the user-mode display driver's <a href="https://msdn.microsoft.com/ce35bdac-af90-471f-af93-0e665be6c7f6">CreateDevice</a>, or <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> function creates scratch-pad areas in video memory. 

The user-mode display driver can create the following types of allocations: 

<ul>
<li>
System memory allocations in which the Microsoft Direct3D runtime preallocates the system memory. In this situation, the user-mode display driver cannot set alignment or any other parameter. If the user-mode display driver requires preallocated system memory that is accessible by the hardware, it calls <b>pfnAllocateCb</b>. The Direct3D runtime returns the system memory pointer in the <b>pSystemMem</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544364">D3DDDI_ALLOCATIONINFO</a> structure for elements in the <b>pAllocationInfo</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544137">D3DDDICB_ALLOCATE</a> structure that is pointed to by <i>pData</i>. If the user-mode display driver does not require preallocated system memory that is accessible by the hardware, it should not call <b>pfnAllocateCb</b> for this type of memory. 

</li>
<li>
System and video memory allocations in which the user-mode display driver can participate in the creation. 

</li>
</ul>
When the driver attempts to create multiple allocations, the driver can associate all of the allocations with a parent resource (for example, when creating a flipping chain in which each backbuffer is an individual allocation). The driver can perform such an association by setting the <b>hResource</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544137">D3DDDICB_ALLOCATE</a> structure that is pointed to by <i>pData</i> to the value that was passed to the driver's <a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a>, <a href="https://msdn.microsoft.com/c21839f0-8302-49f9-a2b4-4009fbd2d88c">CreateResource(D3D10)</a>, or <a href="https://msdn.microsoft.com/2dff9d2e-c497-422f-824b-a7101904fd67">CreateResource(D3D11)</a> function. In response, the Direct3D runtime returns a kernel-mode resource handle (which is of the D3DKMT_HANDLE data type) in the <b>hKMResource</b> member of D3DDDICB_ALLOCATE. The user-mode display driver can subsequently insert this kernel-mode resource handle in the command stream for use by the display miniport driver. 

The display miniport driver can call the <a href="https://msdn.microsoft.com/144429e5-34e6-4416-980e-2838e8f9e415">DxgkCbGetHandleData</a> function on this kernel-mode resource handle (typically within its <a href="https://msdn.microsoft.com/fd634768-5e1e-4f40-82fd-5ef69148c3d7">DxgkDdiRender</a> function) to obtain private data that is associated with the resource, or the display miniport driver can call the <a href="https://msdn.microsoft.com/36307e63-9e94-4441-92c6-fd4293ea8fa9">DxgkCbEnumHandleChildren</a> function to obtain all of the allocations that are associated with the resource. The display miniport driver can also call the <a href="https://msdn.microsoft.com/db8e7a91-d62a-4d2f-ac21-266e365a352c">DxgkCbGetHandleParent</a> function to obtain the parent kernel-mode resource handle from a child allocation handle. 

Note that if the <b>hResource</b> member of D3DDDICB_ALLOCATE is set to <b>NULL</b> when the user-mode display driver calls <b>pfnAllocateCb</b>, the allocation is associated with the device instead of with a resource. The driver can determine only that the difference is semantic. Associating allocations with a resource is optional but recommended for debugging and diagnostic purposes.

<b>Direct3D Version 9 Note:  </b>For more information about creating and destroying resources, see <a href="https://msdn.microsoft.com/d443bdc3-1c5a-4372-9e6a-b8a4d21499b9">Handling Resource Creation and Destruction</a>.

<b>Direct3D Version 11 Note:  </b>For more information about how the driver calls <b>pfnAllocateCb</b>, see <a href="https://msdn.microsoft.com/014a5e44-f8c4-45c0-96e8-d82f37b8b28d">Changes from Direct3D 10</a>.

The following code example shows how to allocate memory for a resource.

```cpp
    D3DDDICB_ALLOCATE           allocCB;
    D3DDDI_ALLOCATIONINFO       allocInfo;
    HRESULT                     hr;
    memset(&amp;allocInfo,   0, sizeof(allocInfo));
    memset(&amp;allocCB,     0, sizeof(allocCB));
    // Set the VidPN source ID for the primary and fullscreen back buffer
    if (m_dwCurResCaps.Primary) {
        allocInfo.Flags.Primary = TRUE;
        allocInfo.VidPnSourceId = m_VidPnSourceId;
    }
    // Check if the allocation is in system memory
    if (pSysMem) {
        allocInfo.pSystemMem = pSysMem;
    }
    // Use the runtime handle of the resource being created
    // NOTE: This is critical for supporting a shared resource
    allocCB.hResource = m_hCurResRuntime;

    allocCB.NumAllocations = 1;
    allocCB.pAllocationInfo = &amp;allocInfo;

    hr = m_d3dCallbacks.pfnAllocateCb(m_hD3D, &amp;allocCB);

    if (FAILED(hr)) {
        allocInfo.hAllocation = NULL;
    }
    else {
        *phAllocation = allocInfo.hAllocation;
    }

    return (hr);
```


## -see-also




<a href="https://msdn.microsoft.com/ce35bdac-af90-471f-af93-0e665be6c7f6">CreateDevice</a>



<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a>



<a href="https://msdn.microsoft.com/c21839f0-8302-49f9-a2b4-4009fbd2d88c">CreateResource(D3D10)</a>



<a href="https://msdn.microsoft.com/2dff9d2e-c497-422f-824b-a7101904fd67">CreateResource(D3D11)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544137">D3DDDICB_ALLOCATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544364">D3DDDI_ALLOCATIONINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544512">D3DDDI_DEVICECALLBACKS</a>



<a href="https://msdn.microsoft.com/36307e63-9e94-4441-92c6-fd4293ea8fa9">DxgkCbEnumHandleChildren</a>



<a href="https://msdn.microsoft.com/144429e5-34e6-4416-980e-2838e8f9e415">DxgkCbGetHandleData</a>



<a href="https://msdn.microsoft.com/db8e7a91-d62a-4d2f-ac21-266e365a352c">DxgkCbGetHandleParent</a>



<a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a>
 

[Direct3D Runtime Functions Called by the User-Mode Display Drivers](https://docs.microsoft.com/windows-hardware/drivers/display/direct3d-runtime-functions-called-by-user-mode)

