---
UID: NC:d3dumddi.PFND3DDDI_ALLOCATECB
title: PFND3DDDI_ALLOCATECB
author: windows-driver-content
description: The pfnAllocateCb function allocates system or video memory.
old-location: display\pfnallocatecb.htm
old-project: display
ms.assetid: a61e6c6a-3992-429c-ad8c-5f1a61dc7b8b
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3Druntime_Functions_1339f95d-018f-4153-b5b8-6753c38babd7.xml, PFND3DDDI_ALLOCATECB, d3dumddi/pfnAllocateCb, display.pfnallocatecb, pfnAllocateCb, pfnAllocateCb callback function [Display Devices]
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
-	pfnAllocateCb
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_ALLOCATECB callback


## -description


The <b>pfnAllocateCb</b> function allocates system or video memory.


## -prototype


````
PFND3DDDI_ALLOCATECB pfnAllocateCb;

__checkReturn HRESULT APIENTRY CALLBACK pfnAllocateCb(
  _In_    HANDLE            hDevice,
  _Inout_ D3DDDICB_ALLOCATE *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








#### - pData [in, out]

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_allocate.md">D3DDDICB_ALLOCATE</a> structure that describes the allocation.


## -returns



<b>pfnAllocateCb</b> returns one of the following values:

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
The memory was successfully allocated.

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
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<b>pfnAllocateCb</b> could not allocate memory that was required for it to complete.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DERR_OUTOFVIDEOMEMORY </b></dt>
</dl>
</td>
<td width="60%">
<b>pfnAllocateCb</b> could not complete because of insufficient video memory. The video memory manager attempts to virtualize video memory; however, if the virtualization fails (such as, when virtual address space runs out), the memory manager might return this error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_DEVICEREMOVED</b></dt>
</dl>
</td>
<td width="60%">
<b>pfnAllocateCb</b> could not initiate a call to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a> function because a Plug and Play (PnP) stop or a Timeout Detection and Recovery (TDR) event occurred. The user-mode display driver function that called <b>pfnAllocateCb</b> (typically, the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a>, <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createresource.md">CreateResource(D3D10)</a>, or <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createresource.md">CreateResource(D3D11)</a> function) must return this error code back to the Direct3D runtime. 

<b>Direct3D Version 9 Note:  </b>For more information about returning error codes, see <a href="https://msdn.microsoft.com/4a2384e8-407f-4248-8b31-7c4e836b15dc">Returning Error Codes Received from Runtime Functions</a>.

<b>Direct3D Versions 10 and 11 Note:  </b>If the driver function does not return a value (that is, has VOID for a return parameter type), the driver function calls the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function to send an error code back to the runtime. For more information about handling error codes, see <a href="https://msdn.microsoft.com/ac4e056e-3304-4934-887a-5cc2b87989bd">Handling Errors</a>.

</td>
</tr>
</table>
 

This function might also return other HRESULT values.




## -remarks



A user-mode display driver calls <b>pfnAllocateCb</b> to allocate system or video memory (also known as an <i>allocation</i>). The Microsoft DirectX graphics kernel subsystem (<i>Dxgkrnl.sys</i>) then calls the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a> function to interpret and store the private data that was passed in the <b>pfnAllocateCb</b> request. The display miniport driver returns information from the <i>DxgkDdiCreateAllocation</i> call that the video memory manager (which is part of <i>Dxgkrnl.sys</i>) uses to actually allocate the memory. 

The user-mode display driver typically creates an allocation in response to a call to its <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a>, <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createresource.md">CreateResource(D3D10)</a>, or <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createresource.md">CreateResource(D3D11)</a> function. However, the user-mode display driver can create an allocation at anytime--for example, when the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdevice.md">CreateDevice</a>, or <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function creates scratch-pad areas in video memory. 

The user-mode display driver can create the following types of allocations: 

<ul>
<li>
System memory allocations in which the Microsoft Direct3D runtime preallocates the system memory. In this situation, the user-mode display driver cannot set alignment or any other parameter. If the user-mode display driver requires preallocated system memory that is accessible by the hardware, it calls <b>pfnAllocateCb</b>. The Direct3D runtime returns the system memory pointer in the <b>pSystemMem</b> member of the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_allocationinfo.md">D3DDDI_ALLOCATIONINFO</a> structure for elements in the <b>pAllocationInfo</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_allocate.md">D3DDDICB_ALLOCATE</a> structure that is pointed to by <i>pData</i>. If the user-mode display driver does not require preallocated system memory that is accessible by the hardware, it should not call <b>pfnAllocateCb</b> for this type of memory. 

</li>
<li>
System and video memory allocations in which the user-mode display driver can participate in the creation. 

</li>
</ul>
When the driver attempts to create multiple allocations, the driver can associate all of the allocations with a parent resource (for example, when creating a flipping chain in which each backbuffer is an individual allocation). The driver can perform such an association by setting the <b>hResource</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_allocate.md">D3DDDICB_ALLOCATE</a> structure that is pointed to by <i>pData</i> to the value that was passed to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a>, <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createresource.md">CreateResource(D3D10)</a>, or <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createresource.md">CreateResource(D3D11)</a> function. In response, the Direct3D runtime returns a kernel-mode resource handle (which is of the D3DKMT_HANDLE data type) in the <b>hKMResource</b> member of D3DDDICB_ALLOCATE. The user-mode display driver can subsequently insert this kernel-mode resource handle in the command stream for use by the display miniport driver. 

The display miniport driver can call the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_gethandledata.md">DxgkCbGetHandleData</a> function on this kernel-mode resource handle (typically within its <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_render.md">DxgkDdiRender</a> function) to obtain private data that is associated with the resource, or the display miniport driver can call the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_enumhandlechildren.md">DxgkCbEnumHandleChildren</a> function to obtain all of the allocations that are associated with the resource. The display miniport driver can also call the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_gethandleparent.md">DxgkCbGetHandleParent</a> function to obtain the parent kernel-mode resource handle from a child allocation handle. 

Note that if the <b>hResource</b> member of D3DDDICB_ALLOCATE is set to <b>NULL</b> when the user-mode display driver calls <b>pfnAllocateCb</b>, the allocation is associated with the device instead of with a resource. The driver can determine only that the difference is semantic. Associating allocations with a resource is optional but recommended for debugging and diagnostic purposes.

<b>Direct3D Version 9 Note:  </b>For more information about creating and destroying resources, see <a href="https://msdn.microsoft.com/d443bdc3-1c5a-4372-9e6a-b8a4d21499b9">Handling Resource Creation and Destruction</a>.

<b>Direct3D Version 11 Note:  </b>For more information about how the driver calls <b>pfnAllocateCb</b>, see <a href="https://msdn.microsoft.com/014a5e44-f8c4-45c0-96e8-d82f37b8b28d">Changes from Direct3D 10</a>.

The following code example shows how to allocate memory for a resource.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    D3DDDICB_ALLOCATE           allocCB;
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

    return (hr);</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicecallbacks.md">D3DDDI_DEVICECALLBACKS</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_allocate.md">D3DDDICB_ALLOCATE</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createresource.md">CreateResource(D3D10)</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_gethandledata.md">DxgkCbGetHandleData</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_enumhandlechildren.md">DxgkCbEnumHandleChildren</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createresource.md">CreateResource(D3D11)</a>



<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_allocationinfo.md">D3DDDI_ALLOCATIONINFO</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdevice.md">CreateDevice</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_gethandleparent.md">DxgkCbGetHandleParent</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_ALLOCATECB callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

