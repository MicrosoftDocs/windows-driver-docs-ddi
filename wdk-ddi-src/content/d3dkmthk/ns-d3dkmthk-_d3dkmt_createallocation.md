---
UID: NS:d3dkmthk._D3DKMT_CREATEALLOCATION
title: "_D3DKMT_CREATEALLOCATION"
author: windows-driver-content
description: The D3DKMT_CREATEALLOCATION structure describes parameters for creating allocations.
old-location: display\d3dkmt_createallocation.htm
old-project: display
ms.assetid: 3e698027-23f8-4765-a4ac-955cd4b24a70
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMT_CREATEALLOCATION, D3DKMT_CREATEALLOCATION structure [Display Devices], OpenGL_Structs_983d37f8-47ad-40ea-b3da-2a211e9f0967.xml, _D3DKMT_CREATEALLOCATION, d3dkmthk/D3DKMT_CREATEALLOCATION, display.d3dkmt_createallocation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_CREATEALLOCATION
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_CREATEALLOCATION
---

# _D3DKMT_CREATEALLOCATION structure


## -description


The D3DKMT_CREATEALLOCATION structure describes parameters for creating allocations.


## -struct-fields




### -field hDevice

[in] A handle to the device that the resource or allocation is associated with.


### -field hResource

[in/out] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the resource that is associated with the allocations. The value in <b>hResource</b> should always be zero unless an allocation will be added to an existing resource, in which case <b>hResource</b> contains the resource handle. 

When the <b>CreateResource</b> bit-field flag is set in the <b>Flags</b> member, the OpenGL runtime generates a unique handle and passes it back to the driver. On output from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546807">D3DKMTCreateAllocation</a> function, <b>hResource</b> specifies the handle that the driver should use in subsequent OpenGL runtime calls to identify the resource. The resource handle that is returned is device-specific and is valid only when used with the device that it was created on.


### -field hGlobalShare

[out] A handle to the shared resource. The driver should always set the value in <b>hGlobalShare</b> to zero. 

When the driver sets the <b>CreateShared</b> bit-field flag in <b>Flags</b> to create a shared resource, the OpenGL runtime generates a shared handle that is unique across all of the devices and passes it back to the driver in <b>hGlobalShare</b>.<div class="alert"><b>Note</b>  If you set  <b>CreateShared</b>, you must also set the <b>CreateResource</b> bit-field flag.</div>
<div> </div>



### -field pPrivateRuntimeData

[in] A pointer to optional private data that can be attached to a resource for debugging purposes. This data is per resource and not per allocation.


### -field PrivateRuntimeDataSize

[in] The size, in bytes, of the private data that <b>pPrivateRuntimeData</b> points to.


### -field PrivateDriverDataSize

[in/out] The size, in bytes, of the private data that <b>pPrivateDriverData</b> points to.


### -field NumAllocations

[in] The number of elements in the array that <b>pAllocationInfo</b> specifies, which represents the number of allocations to create. Note that creating a resource without any allocations initially associated with it is valid; therefore, <b>NumAllocations</b> can be set to 0.


### -field Flags

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff547802">D3DKMT_CREATEALLOCATIONFLAGS</a> structure that identifies  attributes for creating the allocation, in bit-field flags.

<div class="alert"><b>Note</b>  If  you set the <b>CreateShared</b> bit-field flag in <b>Flags</b>, you must also set the <b>CreateResource</b> bit-field flag.</div>
<div> </div>

### -field hPrivateRuntimeResourceHandle

[in] An opaque handle that you can use in event tracing. This handle can be used to associate kernel-mode allocations with user-mode surface pointers when you analyze Event Tracing for Windows (ETW) event logs.


#### - pAllocationInfo

[in] An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544364">D3DDDI_ALLOCATIONINFO</a> structures that describe specific properties for each allocation to create.


#### - pAllocationInfo2

[in] This member is reserved and should be set to zero.

This member is available beginning with Windows 7.


#### - pPrivateDriverData

[in] A pointer to a buffer that contains optional private data that the display miniport driver might require to create the resource or allocation. The contents of the buffer typically come from the OpenGL ICD and must be in a format that the display miniport driver can process.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544364">D3DDDI_ALLOCATIONINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546807">D3DKMTCreateAllocation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547802">D3DKMT_CREATEALLOCATIONFLAGS</a>
 

 

