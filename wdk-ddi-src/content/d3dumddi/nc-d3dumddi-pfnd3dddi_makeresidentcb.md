---
UID: NC:d3dumddi.PFND3DDDI_MAKERESIDENTCB
title: PFND3DDDI_MAKERESIDENTCB
author: windows-driver-content
description: pfnMakeResidentCb is used to instruct the OS to add a resource to the device residency list and increment the residency reference count on this allocation.
old-location: display\pfnmakeresidentcb.htm
old-project: display
ms.assetid: 8D65C3F7-3D07-4341-A989-A1438F821802
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DDDI_MAKERESIDENTCB, d3dumddi/pfnMakeResidentCb, display.pfnmakeresidentcb, pfnMakeResidentCb, pfnMakeResidentCb callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
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
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_MAKERESIDENTCB callback


## -description


<b>pfnMakeResidentCb</b> is used to instruct the OS to add a resource to the device residency list and increment the residency reference count on this allocation.


## -parameters




### -param hDevice [in]

A handle to the display device.


### -param *








#### - pData [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn906323">D3DDDI_MAKERESIDENT</a> structure that describes the memory pages to make resident.




## -returns



<i>pfnMakeResidentCb</i> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
All allocations have been made resident on the GPU upon the exit from this function and are ready to be accessed immediately.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The allocations have been added to the device residency requirement list but still have pending paging operations to complete before they can be successfully accessed. In this case the user mode driver must wait for the <b>PagingFenceValue</b> on the monitored fence sync object associated with <b>hPagingQueue</b> to be signaled prior to submitting command buffers that reference allocations or a GPU page fault may occur.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
The video memory manager can’t make every requested allocation resident. When this happens, no allocation in the provided list will see their residency count modified. In other word this is an atomic operation where either all of the allocation get their residency count increased, or none of them. Further, <b>NumBytesToTrim</b> indicates to the driver how many bytes must be trimmed from the device residency requirement list, by calling <a href="https://msdn.microsoft.com/5E66A522-BC1C-4E7C-8732-87D40F99BBDA">pfnEvictCb</a>, before attempting to made the failed allocations resident again.


The memory budget associated with an application can change asynchronously with the application running. As a consequence of this, trimming the requested number of bytes will not guarantee that the next attempt to make the set of allocations resident will succeed as the memory budget for the application may have decreased. Because of this a driver should ensure that it attempts residency request in a loop, trimming between each iteration, until the request either succeeds or the driver has trimmed everything it possibly can to make forward progress on a single operation and use the required resource on that final attempt. If that final attempt fails, the underlying device will be put in error and the user mode driver should abort the request and return back to the application. No further submissions to any of the contexts belonging to a device in error will be allowed by the kernel.


For the DirectX 12.0 user mode driver, <i>pfnMakeResidentCb</i> behaves slightly differently because it  is no longer responsible for trimming or paging in allocations. This is done to ensure that the state of all allocations after returning from the call remain the same as before the call. This means that if <b>E_OUTOFMEMORY</b> is returned from the function:


<ul>
<li>All of the allocations remain in their original state.</li>
<li>The allocations were not made resident.</li>
<li><b>PagingFenceValue</b> should be ignored.</li>
</ul>  If the driver needs to perform <i>pfnMakeResidentCb</i> calls in multiple batches to accommodate resource-to-allocation translation, the driver should undo any prior calls to <i>pfnMakeResidentCb</i> with equivalent calls to <a href="https://msdn.microsoft.com/5E66A522-BC1C-4E7C-8732-87D40F99BBDA">pfnEvictCb</a>, and propagate the error code back to the runtime. 

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906323">D3DDDI_MAKERESIDENT</a>



<a href="https://msdn.microsoft.com/5E66A522-BC1C-4E7C-8732-87D40F99BBDA">pfnEvictCb</a>
 

 

