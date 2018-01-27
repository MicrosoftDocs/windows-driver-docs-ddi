---
UID: NS:d3dkmthk._D3DKMT_CREATEALLOCATION
title: _D3DKMT_CREATEALLOCATION
author: windows-driver-content
description: The D3DKMT_CREATEALLOCATION structure describes parameters for creating allocations.
old-location: display\d3dkmt_createallocation.htm
old-project: display
ms.assetid: 3e698027-23f8-4765-a4ac-955cd4b24a70
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMT_CREATEALLOCATION structure [Display Devices], OpenGL_Structs_983d37f8-47ad-40ea-b3da-2a211e9f0967.xml, D3DKMT_CREATEALLOCATION, _D3DKMT_CREATEALLOCATION, display.d3dkmt_createallocation, d3dkmthk/D3DKMT_CREATEALLOCATION
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	d3dkmthk.h
apiname: 
-	D3DKMT_CREATEALLOCATION
product: Windows
targetos: Windows
req.typenames: D3DKMT_CREATEALLOCATION
---

# _D3DKMT_CREATEALLOCATION structure


## -description


The D3DKMT_CREATEALLOCATION structure describes parameters for creating allocations.


## -syntax


````
typedef struct _D3DKMT_CREATEALLOCATION {
  D3DKMT_HANDLE                hDevice;
  D3DKMT_HANDLE                hResource;
  D3DKMT_HANDLE                hGlobalShare;
  const VOID                   *pPrivateRuntimeData;
  UINT                         PrivateRuntimeDataSize;
  const VOID                   *pPrivateDriverData;
  UINT                         PrivateDriverDataSize;
  UINT                         NumAllocations;
  union {
    D3DDDI_ALLOCATIONINFO  *pAllocationInfo;
#if ((DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN7) || \
     (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WIN7))
    D3DDDI_ALLOCATIONINFO2 *pAllocationInfo2;
#endif 
  };
  D3DKMT_CREATEALLOCATIONFLAGS Flags;
  HANDLE                       hPrivateRuntimeResourceHandle;
} D3DKMT_CREATEALLOCATION;
````


## -struct-fields




### -field pStandardAllocation

 


### -field pPrivateDriverData

[in] A pointer to a buffer that contains optional private data that the display miniport driver might require to create the resource or allocation. The contents of the buffer typically come from the OpenGL ICD and must be in a format that the display miniport driver can process.


### -field pAllocationInfo

[in] An array of <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_allocationinfo.md">D3DDDI_ALLOCATIONINFO</a> structures that describe specific properties for each allocation to create.


### -field pAllocationInfo2

[in] This member is reserved and should be set to zero.

This member is available beginning with Windows 7.


### -field hDevice

[in] A handle to the device that the resource or allocation is associated with.


### -field hResource

[in/out] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the resource that is associated with the allocations. The value in <b>hResource</b> should always be zero unless an allocation will be added to an existing resource, in which case <b>hResource</b> contains the resource handle. 

When the <b>CreateResource</b> bit-field flag is set in the <b>Flags</b> member, the OpenGL runtime generates a unique handle and passes it back to the driver. On output from the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreateallocation.md">D3DKMTCreateAllocation</a> function, <b>hResource</b> specifies the handle that the driver should use in subsequent OpenGL runtime calls to identify the resource. The resource handle that is returned is device-specific and is valid only when used with the device that it was created on.


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

[in] A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createallocationflags.md">D3DKMT_CREATEALLOCATIONFLAGS</a> structure that identifies  attributes for creating the allocation, in bit-field flags.
<div class="alert"><b>Note</b>  If  you set the <b>CreateShared</b> bit-field flag in <b>Flags</b>, you must also set the <b>CreateResource</b> bit-field flag.</div><div> </div>

### -field hPrivateRuntimeResourceHandle

[in] An opaque handle that you can use in event tracing. This handle can be used to associate kernel-mode allocations with user-mode surface pointers when you analyze Event Tracing for Windows (ETW) event logs.


## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createallocationflags.md">D3DKMT_CREATEALLOCATIONFLAGS</a>

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreateallocation.md">D3DKMTCreateAllocation</a>

<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_allocationinfo.md">D3DDDI_ALLOCATIONINFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_CREATEALLOCATION structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

