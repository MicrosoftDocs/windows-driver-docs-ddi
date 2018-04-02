---
UID: NC:d3dumddi.PFND3DDDI_LOCKCB
title: PFND3DDDI_LOCKCB
author: windows-driver-content
description: The pfnLockCb function locks an allocation and obtains a pointer to the allocation from the display miniport driver or video memory manager.
old-location: display\pfnlockcb.htm
old-project: display
ms.assetid: 69022797-432a-410b-8cbf-e1ef7111e7ea
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3Druntime_Functions_25ad9d8e-34e0-4b1e-9a3a-4d170322fbca.xml, PFND3DDDI_LOCKCB, d3dumddi/pfnLockCb, display.pfnlockcb, pfnLockCb, pfnLockCb callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	pfnLockCb
product:
- Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_LOCKCB callback


## -description


The <i>pfnLockCb</i> function locks an allocation and obtains a pointer to the allocation from the display miniport driver or video memory manager. 


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








#### - pData [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544205">D3DDDICB_LOCK</a> structure that describes the allocation to lock.


## -returns



<i>pfnLockCb</i> returns one of the following values:

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
The allocation was successfully locked.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DERR_NOTAVAILABLE</b></dt>
</dl>
</td>
<td width="60%">
An aperture was not available.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DERR_WASSTILLDRAWING</b></dt>
</dl>
</td>
<td width="60%">
The allocation was still being used for rendering.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_CANTEVICTPINNEDALLOCATION</b></dt>
</dl>
</td>
<td width="60%">
The allocation could not be locked because of the unavailability of a deswizzling aperture and the inability to evict the allocation because it was pinned.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/69022797-432a-410b-8cbf-e1ef7111e7ea">pfnLockCb</a> could not complete because of insufficient memory (this situation occurs when the system is in an extreme low memory situation and there is not enough space to allocate the array of pages).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">

        Parameters were validated and determined to be incorrect.
       

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_DEVICEREMOVED</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/69022797-432a-410b-8cbf-e1ef7111e7ea">pfnLockCb</a> could not cause the video memory manager and display miniport driver to perform the appropriate actions because a Plug and Play (PnP) stop or a Timeout Detection and Recovery (TDR) event occurred. The user-mode display driver function that called <i>pfnLockCb</i> (typically, the <a href="https://msdn.microsoft.com/e2289073-d46a-4a12-8de7-30400e04cc22">Lock</a> or <a href="https://msdn.microsoft.com/1310a3f8-02dd-4d35-98ad-4016e57d1eb2">ResourceMap</a> function) must return this error code back to the Direct3D runtime. 

<b>Direct3D Version 9 Note:  </b>For more information about returning error codes, see <a href="https://msdn.microsoft.com/4a2384e8-407f-4248-8b31-7c4e836b15dc">Returning Error Codes Received from Runtime Functions</a>.

<b>Direct3D Versions 10 and 11 Note:  </b>If the driver function does not return a value (that is, has VOID for a return parameter type), the driver function calls the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function to send an error code back to the runtime. For more information about handling error codes, see <a href="https://msdn.microsoft.com/ac4e056e-3304-4934-887a-5cc2b87989bd">Handling Errors</a>.

</td>
</tr>
</table>
 

This function might also return other HRESULT values.




## -remarks



The user-mode display driver can call the Microsoft Direct3D runtime's <i>pfnLockCb</i> function to lock an allocation and obtain a pointer to the allocation from the display miniport driver or video memory manager. The user-mode display driver typically calls <i>pfnLockCb</i> in response to a call to its <a href="https://msdn.microsoft.com/e2289073-d46a-4a12-8de7-30400e04cc22">Lock</a> or <a href="https://msdn.microsoft.com/1310a3f8-02dd-4d35-98ad-4016e57d1eb2">ResourceMap</a> function (or other variations of <b>ResourceMap</b> such as <i>DynamicIABufferMapDiscard</i>) to lock a resource or a surface within the resource. Before returning from the <b>Lock</b> or <b>ResourceMap</b> call, the user-mode display driver must first map the resource or surface to the appropriate allocation and then call <i>pfnLockCb</i> to lock the allocation. The allocation must be locked before it can be read from or written to because locking: 

<ul>
<li>
Guarantees that the virtual address range for the allocation remains unchanged, valid, readable, and writable for the duration of the lock. The video memory manager provides this guarantee. 

</li>
<li>
Provides a way to synchronize the read and write operations of the allocation with graphics hardware accesses of the allocation. The video memory manager and display miniport driver perform the synchronization. 

</li>
</ul>
<b>Direct3D Version 9 Note:  </b><p class="note">  The user-mode display driver usually calls the <i>pfnLockCb</i> and <a href="https://msdn.microsoft.com/6684f350-da27-478d-ab7b-36e395f7df8d">pfnUnlockCb</a> functions that correspond to every call to its <a href="https://msdn.microsoft.com/e2289073-d46a-4a12-8de7-30400e04cc22">Lock</a> and <a href="https://msdn.microsoft.com/23cc9c64-99d4-4602-a1b0-234fe7fcc3da">Unlock</a> functions, respectively, except when the driver handles resources in which the <b>Dynamic</b> bit-field flag was set in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542963">D3DDDIARG_CREATERESOURCE</a> structure when the resources were created. The runtime frequently requests that the driver lock these types of resources, often with the <b>NoOverwrite</b> bit-field flag set in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543204">D3DDDIARG_LOCK</a> structure. Because data in such resources should not be modified (as indicated by <b>NoOverwrite</b>), calling <i>pfnLockCb</i> for each lock request consumes excessive processing time. To prevent calling <i>pfnLockCb</i> for each lock request, the driver can cache the virtual memory pointer that it returns in the <b>pSurfData</b> member of D3DDDIARG_LOCK when its <b>Lock</b> function is called with the <b>NoOverwrite</b> bit-field flag set. However, the driver can continue to call <i>pfnLockCb</i> whenever its <b>Lock</b> function is called with either the <b>Discard</b> bit-field flag set or no flags set.



<b>Direct3D Versions 10 and 11 Note:  </b><p class="note">  The user-mode display driver usually calls the <i>pfnLockCb</i> and <a href="https://msdn.microsoft.com/6684f350-da27-478d-ab7b-36e395f7df8d">pfnUnlockCb</a> functions that correspond to every call to its <a href="https://msdn.microsoft.com/1310a3f8-02dd-4d35-98ad-4016e57d1eb2">ResourceMap</a> and <a href="https://msdn.microsoft.com/fb2b714e-232d-40b2-88ad-ee8dcd70a057">ResourceUnmap</a> functions (or other variations of these functions). This does not happen when the driver handles resources in which the D3D10_DDI_USAGE_DYNAMIC value was set in the <b>Usage</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541697">D3D10DDIARG_CREATERESOURCE</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff542062">D3D11DDIARG_CREATERESOURCE</a> structure when the resources were created. The runtime frequently requests that the driver lock these types of resources, often by passing the D3D10_DDI_MAP_WRITE_NOOVERWRITE value to the <i>DDIMap</i> parameter in the call to <b>ResourceMap</b>. Because data in such resources should not be modified (as indicated by D3D10_DDI_MAP_WRITE_NOOVERWRITE), calling <i>pfnLockCb</i> for each lock request consumes excessive processing time. To prevent calling <i>pfnLockCb</i> for each lock request, the driver can cache the virtual memory pointer that it returns in the <i>pMappedSubResource</i> parameter when its <i>ResourceMap</i> function is called with D3D10_DDI_MAP_WRITE_NOOVERWRITE. However, the driver can continue to call <i>pfnLockCb</i> whenever its <i>ResourceMap</i> function is called with either the D3D10_DDI_MAP_WRITE_DISCARD value or 0 passed to the <i>DDIMap</i> parameter.



While the application does not hold an outstanding lock to the resource that is associated with the virtual memory pointer, the driver typically uncaches the virtual memory pointer by calling the <a href="https://msdn.microsoft.com/6684f350-da27-478d-ab7b-36e395f7df8d">pfnUnlockCb</a> function before the driver calls the <a href="https://msdn.microsoft.com/f242162e-6237-469c-b178-5a51dcf69e32">pfnRenderCb</a> function. If the lock is not uncached or if the lock cannot be uncached because the application still has the resource locked, the hardware might render from a locked allocation. The video memory manager cannot support this mode of operation if the allocation is in local video memory; therefore, the memory manager evicts the allocation to system or AGP memory when the memory manager detects this situation. If the allocation is not supported in the system or AGP memory segment, the memory manager fails the call to <i>pfnRenderCb</i> with D3DDDIERR_CANTRENDERLOCKEDALLOCATION. Therefore, vertex and index buffer allocations that are allocated in response to creating resources in which the <b>Dynamic</b> bit-field flag is set in the <b>Flags</b> member of D3DDDIARG_CREATERESOURCE (or the D3D10_DDI_USAGE_DYNAMIC value is set in the <b>Usage</b> member of D3D10DDIARG_CREATERESOURCE or D3D11DDIARG_CREATERESOURCE) should be supported in system or AGP segments.

Setting the <b>Discard</b> bit-field flag in the <b>Flags</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544205">D3DDDICB_LOCK</a> in a call to <i>pfnLockCb</i> causes the video memory manager to create a new instance of the allocation that is being locked. The video memory manager represents the new instance by returning a new handle to the user-mode display driver in the <b>hAllocation</b> member of D3DDDICB_LOCK. 

<div class="alert"><b>Note</b>    The display miniport driver's <a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a> function is not called when a new instance of an allocation is created. Instances appear to the display miniport driver as allocations that are simultaneously paged in to multiple different locations.</div>
<div> </div>
The video memory manager might fail a lock in which the <b>Discard</b> bit-field flag is set because the video memory manager cannot create a new instance or reuse an existing instance of an allocation. When this failure occurs, the user-mode display driver should call the <a href="https://msdn.microsoft.com/f242162e-6237-469c-b178-5a51dcf69e32">pfnRenderCb</a> function to flush its current command buffer to the kernel. This flush of the command buffer might retire some instances of the allocation that could not be locked by using the <b>Discard</b> bit-field flag. 

After flushing its command buffer, the user-mode display driver must try locking the surface again by using both the <b>Discard</b> and <b>NoExistingReference</b> bit-field flags. The <b>NoExistingReference</b> bit-field flag indicates to the video memory manager that the driver does not currently have a reference to any instance of the allocation that is being locked queued in its command buffer. The video memory manager can then reuse any instance of the allocation to handle the lock, including the current instance.

After a call to <i>pfnLockCb</i> in which the <b>Discard</b> bit-field flag is set, the user-mode display driver should always check for an updated handle value in the <b>hAllocation</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544205">D3DDDICB_LOCK</a>. If a new allocation handle is provided, the user-mode display driver should update its internal data structure to reference the new allocation handle. The user-mode display driver should also add a re-programmed version of the locked allocation base address to the current command buffer (because allocation instances contain different base addresses). The video memory manager validates the use of allocation instances that are used by the driver and rejects DMA buffers that use the allocation instances incorrectly (that is, calls to <a href="https://msdn.microsoft.com/460b9be5-5817-4225-9089-f86ad64f4554">pfnPresentCb</a> and <a href="https://msdn.microsoft.com/f242162e-6237-469c-b178-5a51dcf69e32">pfnRenderCb</a> fail if they incorrectly use allocation instances). After the driver references a particular instance of an allocation, the driver can no longer reference a previous instance of the same allocation. For example, if a command buffer uses allocation A and currently uses instances A0 and A1, then as soon as A1 is used (that is, appears in the patch-location list) A0 becomes invalid. The display miniport driver can generate a patch-location list that references both A0 and A1. However, the references must be ordered (that is, A0 can be used first; A0 becomes invalid once A2 is used; A1 becomes invalid when A2 is used, and so on).

The user-mode display driver might call <i>pfnLockCb</i> for system memory allocations, even if the memory has not been preallocated, because the display miniport driver might actually be in the process of sending, through DMA, or asynchronously transferring those allocations to graphics hardware. Therefore, before an application is allowed to write to the surface, the display miniport driver and video memory manager must be notified so that they can block the lock if necessary. 

The user-mode display driver can also lock subregions of an allocation. This type of lock is typically not necessary when an unswizzling or linearizing hardware aperture is available because, in this situation, the user-mode display driver can translate a lock on the entire allocation to the subregion by offsetting the pointer. However, when <i>pfnLockCb</i> fails by using D3DERR_NOTAVAILABLE to indicate that an aperture is not available, the memory manager requests the user-mode display driver to copy video memory contents. The user-mode display driver unswizzles or linearizes the video memory contents while copying them into another area of memory. In this situation, the user-mode display driver can supply a list of pages to copy to save large amounts of copying when locking small subregions in a large allocation. Note that the memory manager fails a call to <i>pfnLockCb</i> with D3DERR_NOTAVAILABLE if the user-mode display driver did not set the <b>LockEntire</b> bit-field flag in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544205">D3DDDICB_LOCK</a> structure and did not specify a page list in the <b>pPages</b> member of D3DDDICB_LOCK. If the user-mode display driver sets the <b>LockEntire</b> bit-field flag, it must also set the <b>NumPages</b> and <b>pPages</b> members of D3DDDICB_LOCK to 0 and <b>NULL</b>, respectively. The user-mode display driver should always supply a page list in <b>pPages</b> when locking an allocation that was created with a permanent backing store. In this situation, the memory manager uses the page list to mark as dirty only specific pages and is not required to copy the entire allocation from the backing store when it is used for rendering. 

The user-mode display driver can call <i>pfnLockCb</i> to acquire multiple swizzling ranges for a single allocation (for example, one swizzling range for each MIP level). If the driver cannot acquire any one of the ranges, the Direct3D runtime evicts the entire allocation to handle the lock (all of the MIP levels) and reclaims all of the swizzling ranges.

When the user-mode display driver requests that a swizzling range be assigned to the allocation, the driver effectively requests access to the unswizzled bits of the allocation. For such requests, the video memory manager either pages in the allocation into a memory segment and sets up a swizzling range to access the allocation or pages in the allocation into a memory segment and then evicts the allocation to system memory while requesting that the driver unswizzle the allocation on the way to system memory. An allocation that was unswizzled to system memory is reswizzled (by being paged into video memory) before the GPU uses the allocation again. As a result, the driver cannot request a no-overwrite-type lock (by setting the <b>DonotWait</b> bit-field flag) when it acquires a swizzling range. Similarly, the driver cannot reference an allocation lock in such a way in a DMA buffer that is submitted to the GPU (because the DMA buffer will be rejected).

The user-mode display driver might lock a swizzled allocation without acquiring a swizzling range if the driver must access the bits of the allocation in a swizzled format. In this situation, the video memory manager provides the driver with a pointer to the swizzled bits of the allocation. However, the driver cannot request a pointer to the swizzled bits of the allocation while a request for the unswizzled bits is outstanding, and vice versa (that is, a lock is currently pending on the allocation with a swizzling range acquired).

The user-mode display driver should pass the <b>Discard</b> bit-field flag in the <b>Flags</b> member of D3DDDICB_LOCK in the <i>pfnLockCb</i> call in the following situations: 

<ul>
<li>
When the Direct3D runtime passes the <b>Discard</b> bit-field flag in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543204">D3DDDIARG_LOCK</a> structure in the call to the user-mode display driver's <a href="https://msdn.microsoft.com/e2289073-d46a-4a12-8de7-30400e04cc22">Lock</a> function

</li>
<li>
When the runtime passes the D3D10_DDI_MAP_WRITE_DISCARD value to the <i>DDIMap</i> parameter in the call to the driver's <a href="https://msdn.microsoft.com/1310a3f8-02dd-4d35-98ad-4016e57d1eb2">ResourceMap</a> function 

</li>
</ul>
Setting the <b>Discard</b> bit-field flag causes the memory manager to determine if it should rename the allocation or should cause the application thread to stall until the allocation is idle. For more information about renaming an allocation, see <a href="https://msdn.microsoft.com/f22e19ba-9ff3-4aa1-a3f0-103f67ea7c60">Requesting to Rename an Allocation</a>. The driver can use its own renaming support or the memory manager's renaming support. To use its own renaming support, the driver sets the <b>DonotWait</b> bit-field flag, in response to a <a href="https://msdn.microsoft.com/e2289073-d46a-4a12-8de7-30400e04cc22">Lock</a> call with the <b>Discard</b> bit-field flag set, or in response to a <a href="https://msdn.microsoft.com/1310a3f8-02dd-4d35-98ad-4016e57d1eb2">ResourceMap</a> call with the D3D10_DDI_MAP_WRITE_DISCARD value set. Setting the <b>DonotWait</b> bit-field flag causes the memory manager to fail the call to <i>pfnLockCb</i> with D3DERR_WASSTILLDRAWING if the graphics hardware is still using the allocation. Such a failure indicates to the user-mode display driver to rename or multiple-buffer the allocation. 

<div class="alert"><b>Note</b>    The <b>DonotWait</b> bit-field flag has no effect on the memory manager if the <b>Discard</b> bit-field flag is also set.</div>
<div> </div>
The user-mode display driver should set the <b>IgnoreSync</b> bit-field flag in the <b>Flags</b> member of D3DDDICB_LOCK when it does not require the memory manager to check whether the graphics hardware is using the allocation. The user-mode display driver must then properly synchronize access to the allocation. If the <b>DonotWait</b> bit-field flag is not specified with the <b>IgnoreSync</b> bit-field flag, the memory manager ignores the <b>IgnoreSync</b> bit-field flag.

<div class="alert"><b>Note</b>    The <b>IgnoreSync</b> bit-field flag has no effect on the memory manager if the <b>Discard</b> bit-field flag is also set.</div>
<div> </div>
<b>Example</b>

The following code example shows how the <b>Discard</b> bit-field flag is used in a call to <i>pfnLockCb</i>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HRESULT hr;
D3DDDICB_LOCK LockData;
LockData.hAllocation = AllocationToLock;
LockData.Flags.Discard = TRUE;
hr = pfnLockCb(&amp;LockData)
if (FAILED(hr)) {
    FlushAccumulatedCommandBufferToKernel();
    LockData.Flags.Discard = TRUE;
    LockData.Flags.NoExistingReference = TRUE;
    hr = pfnLockCb(&amp;LockData);
    if (FAILED(hr)) {
        // Fails the lock to the application
    }
}
UpdateAllocationHandleInUMDDataStructure(LockData.hAllocation);
ProgramSurfaceBaseAddressInCurrentCommandBuffer(LockData.hAllocation);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541697">D3D10DDIARG_CREATERESOURCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542062">D3D11DDIARG_CREATERESOURCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543204">D3DDDIARG_LOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544205">D3DDDICB_LOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544512">D3DDDI_DEVICECALLBACKS</a>



<a href="https://msdn.microsoft.com/e2289073-d46a-4a12-8de7-30400e04cc22">Lock</a>



<a href="https://msdn.microsoft.com/1310a3f8-02dd-4d35-98ad-4016e57d1eb2">ResourceMap</a>



<a href="https://msdn.microsoft.com/fb2b714e-232d-40b2-88ad-ee8dcd70a057">ResourceUnmap</a>
 

 

