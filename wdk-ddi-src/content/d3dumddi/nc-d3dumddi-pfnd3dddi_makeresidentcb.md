---
UID: NC:d3dumddi.PFND3DDDI_MAKERESIDENTCB
title: PFND3DDDI_MAKERESIDENTCB
author: windows-driver-content
description: pfnMakeResidentCb is used to instruct the OS to add a resource to the device residency list and increment the residency reference count on this allocation.
old-location: display\pfnmakeresidentcb.htm
tech.root: display
ms.assetid: 8D65C3F7-3D07-4341-A989-A1438F821802
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_MAKERESIDENTCB, PFND3DDDI_MAKERESIDENTCB callback, d3dumddi/pfnMakeResidentCb, display.pfnmakeresidentcb, pfnMakeResidentCb, pfnMakeResidentCb callback function [Display Devices]
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	pfnMakeResidentCb
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_MAKERESIDENTCB callback function


## -description


<b>pfnMakeResidentCb</b> is used to instruct the OS to add a resource to the device residency list and increment the residency reference count on this allocation.


## -parameters




### -param hDevice [in]

A handle to the display device.


### -param *

*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn906323">D3DDDI_MAKERESIDENT</a> structure that describes the memory pages to make resident.

## -returns

<i>pfnMakeResidentCb</i> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | All allocations have been made resident on the GPU upon the exit from this function and are ready to be accessed immediately. | 
| **E_PENDING** | The allocations have been added to the device residency requirement list but still have pending paging operations to complete before they can be successfully accessed. In this case the user mode driver must wait for the PagingFenceValue on the monitored fence sync object associated with hPagingQueue to be signaled prior to submitting command buffers that reference allocations or a GPU page fault may occur. | 
| **E_OUTOFMEMORY** | The video memory manager can’t make every requested allocation resident. When this happens, no allocation in the provided list will see their residency count modified. In other word this is an atomic operation where either all of the allocation get their residency count increased, or none of them. Further, NumBytesToTrim indicates to the driver how many bytes must be trimmed from the device residency requirement list, by calling [pfnEvictCb](https://msdn.microsoft.com/5E66A522-BC1C-4E7C-8732-87D40F99BBDA), before attempting to made the failed allocations resident again.<br/>The memory budget associated with an application can change asynchronously with the application running. As a consequence of this, trimming the requested number of bytes will not guarantee that the next attempt to make the set of allocations resident will succeed as the memory budget for the application may have decreased. Because of this a driver should ensure that it attempts residency request in a loop, trimming between each iteration, until the request either succeeds or the driver has trimmed everything it possibly can to make forward progress on a single operation and use the required resource on that final attempt. If that final attempt fails, the underlying device will be put in error and the user mode driver should abort the request and return back to the application. No further submissions to any of the contexts belonging to a device in error will be allowed by the kernel.<br/>For the DirectX 12.0 user mode driver, pfnMakeResidentCb behaves slightly differently because it is no longer responsible for trimming or paging in allocations. This is done to ensure that the state of all allocations after returning from the call remain the same as before the call. This means that if E_OUTOFMEMORY is returned from the function:<br/>- All of the allocations remain in their original state.<br/>- The allocations were not made resident.<br/>- PagingFenceValue should be ignored.<br/>If the driver needs to perform pfnMakeResidentCb calls in multiple batches to accommodate resource-to-allocation translation, the driver should undo any prior calls to pfnMakeResidentCb with equivalent calls to [pfnEvictCb](https://msdn.microsoft.com/5E66A522-BC1C-4E7C-8732-87D40F99BBDA), and propagate the error code back to the runtime. | 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906323">D3DDDI_MAKERESIDENT</a>



<a href="https://msdn.microsoft.com/5E66A522-BC1C-4E7C-8732-87D40F99BBDA">pfnEvictCb</a>
 

 

