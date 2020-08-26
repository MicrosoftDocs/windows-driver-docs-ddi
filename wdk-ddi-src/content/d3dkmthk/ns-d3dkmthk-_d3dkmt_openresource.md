---
UID: NS:d3dkmthk._D3DKMT_OPENRESOURCE
title: _D3DKMT_OPENRESOURCE (d3dkmthk.h)
description: The D3DKMT_OPENRESOURCE structure describes parameters for opening a resource.
old-location: display\d3dkmt_openresource.htm
ms.assetid: 5ff63606-ced1-4482-b967-41db4746ac1d
ms.date: 05/10/2018
keywords: ["D3DKMT_OPENRESOURCE structure"]
ms.keywords: D3DKMT_OPENRESOURCE, D3DKMT_OPENRESOURCE structure [Display Devices], OpenGL_Structs_b069a94a-b78c-4fbf-b78d-7c5b0d025655.xml, _D3DKMT_OPENRESOURCE, d3dkmthk/D3DKMT_OPENRESOURCE, display.d3dkmt_openresource
f1_keywords:
 - "d3dkmthk/D3DKMT_OPENRESOURCE"
 - "D3DKMT_OPENRESOURCE"
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
- D3DKMT_OPENRESOURCE
targetos: Windows
tech.root: display
req.typenames: D3DKMT_OPENRESOURCE
---

# _D3DKMT_OPENRESOURCE structure


## -description


The D3DKMT_OPENRESOURCE structure describes parameters for opening a resource.


## -struct-fields




### -field hDevice

[in] A handle to the device that the resource and allocations are associated with.


### -field hGlobalShare

[in] A handle to the shared resource to open.


### -field NumAllocations

[in] The number of elements in the array that <b>pOpenAllocationInfo</b> specifies, which represents the number of allocations that are associated with the resource.


### -field pOpenAllocationInfo

[in/out] An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_openallocationinfo">D3DDDI_OPENALLOCATIONINFO</a> structures that describe each allocation to update.


### -field pOpenAllocationInfo2

This member is reserved and should be set to zero.

This member is available beginning with Windows 7.


### -field pPrivateRuntimeData

[in] A pointer to a caller-supplied buffer where the OpenGL runtime copies private data that is associated with the resource.


### -field PrivateRuntimeDataSize

[in] The size, in bytes, of the buffer that <b>pPrivateRuntimeData</b> points to.


### -field pResourcePrivateDriverData

[in/out] A pointer to a buffer that receives the private data that is associated with the resource. This data is per resource and not per allocation.


### -field ResourcePrivateDriverDataSize

[in] The size, in bytes, of the buffer that <b>pResourcePrivateDriverData</b> points to.


### -field pTotalPrivateDriverDataBuffer

[in/out] A pointer to a buffer that receives the private data for all of the allocations that are associated with the resource. The caller should never access this private data directly.


### -field TotalPrivateDriverDataBufferSize

[in/out] On input, the size, in bytes, of the buffer that <b>pTotalPrivateDriverDataBuffer</b> points to. On output, this member specifies the size, in bytes, of data that is written to the buffer that <b>pTotalPrivateDriverDataBuffer</b> points to.


### -field hResource

[out] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the newly opened shared resource that is associated with the allocations.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_openallocationinfo">D3DDDI_OPENALLOCATIONINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopenresource">D3DKMTOpenResource</a>
 

 

