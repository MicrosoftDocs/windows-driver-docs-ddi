---
UID: NS:d3dkmthk._D3DKMT_CREATEALLOCATION
title: D3DKMT_CREATEALLOCATION (d3dkmthk.h)
description: Learn more about the D3DKMT_CREATEALLOCATION structure.
ms.date: 07/12/2023
keywords: ["D3DKMT_CREATEALLOCATION structure"]
ms.keywords: D3DKMT_CREATEALLOCATION, D3DKMT_CREATEALLOCATION structure [Display Devices], OpenGL_Structs_983d37f8-47ad-40ea-b3da-2a211e9f0967.xml, _D3DKMT_CREATEALLOCATION, d3dkmthk/D3DKMT_CREATEALLOCATION, display.d3dkmt_createallocation
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
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
req.typenames: D3DKMT_CREATEALLOCATION
f1_keywords:
 - _D3DKMT_CREATEALLOCATION
 - d3dkmthk/_D3DKMT_CREATEALLOCATION
 - D3DKMT_CREATEALLOCATION
 - d3dkmthk/D3DKMT_CREATEALLOCATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_CREATEALLOCATION
 - D3DKMT_CREATEALLOCATION
---

# D3DKMT_CREATEALLOCATION structure

## -description

The **D3DKMT_CREATEALLOCATION** structure describes parameters for [creating allocations](nf-d3dkmthk-d3dkmtcreateallocation.md).

## -struct-fields

### -field hDevice [in]

A handle to the device that the resource or allocation is associated with.

### -field hResource [in/out]

A D3DKMT_HANDLE data type that represents a kernel-mode handle to the resource that is associated with the allocations. The value in **hResource** should always be zero unless an allocation will be added to an existing resource, in which case **hResource** contains the resource handle.

When the **CreateResource** bit-field flag is set in the **Flags** member, the OpenGL runtime generates a unique handle and passes it back to the driver. On output from the [**D3DKMTCreateAllocation**](nf-d3dkmthk-d3dkmtcreateallocation.md) function, **hResource** specifies the handle that the driver should use in subsequent OpenGL runtime calls to identify the resource. The resource handle that is returned is device-specific and is valid only when used with the device that it was created on.

### -field hGlobalShare [out]

A user-mode client driver should not share resources using global handles. The driver should set **NtSecuritySharing** in **Flags** and call [**D3DKMTShareObjects**](nf-d3dkmthk-d3dkmtshareobjects.md) to get an NT handle. Using global handles is not secure. Any process can guess a global handle and open a shared object. Global handles are supported only for compatibility reasons with old D3D runtimes. (When **NtSecuritySharing** isn't set, the global handle is returned in **hGlobalShare**. Nothing prevents a UMD from sharing a resource using a global handle, but drivers shouldn't do that.)

### -field pPrivateRuntimeData [in]

A pointer to optional private data that can be attached to a resource for debugging purposes. This data is per resource and not per allocation.

### -field PrivateRuntimeDataSize [in]

The size, in bytes, of the private data that **pPrivateRuntimeData** points to.

### -field pStandardAllocation [in]

Pointer to a [**D3DKMT_CREATESTANDARDALLOCATION**](ns-d3dkmthk-_d3dkmt_createstandardallocation.md) structure that contains information to use when creating a standard allocation.

### -field pPrivateDriverData [in]

A pointer to a buffer that contains optional private data that the display miniport driver might require to create the resource or allocation. The contents of the buffer typically come from the  ICD and must be in a format that the display miniport driver can process.

### -field PrivateDriverDataSize [in/out]

The size, in bytes, of the private data that **pPrivateDriverData** points to.

### -field NumAllocations [in]

The number of elements in the array that **pAllocationInfo** specifies, which represents the number of allocations to create. Note that creating a resource without any allocations initially associated with it is valid; therefore, **NumAllocations** can be set to 0.

### -field pAllocationInfo [in]

An array of [**D3DDDI_ALLOCATIONINFO**](../d3dukmdt/ns-d3dukmdt-_d3dddi_allocationinfo.md) structures that describe specific properties for each allocation to create.

### -field pAllocationInfo2 [in]

This member is reserved and should be set to zero.

This member is available beginning with Windows 7.

### -field Flags [in]

A [**D3DKMT_CREATEALLOCATIONFLAGS**](ns-d3dkmthk-_d3dkmt_createallocationflags.md) structure that identifies attributes for creating the allocation, in bit-field flags.

If you set the **CreateShared** bit-field flag in **Flags**, you must also set the **CreateResource** bit-field flag.

### -field hPrivateRuntimeResourceHandle [in]

An opaque handle that you can use in event tracing. This handle can be used to associate kernel-mode allocations with user-mode surface pointers when you analyze Event Tracing for Windows (ETW) event logs.

## -see-also

[**D3DDDI_ALLOCATIONINFO**](../d3dukmdt/ns-d3dukmdt-_d3dddi_allocationinfo.md)

[**D3DKMTCreateAllocation**](nf-d3dkmthk-d3dkmtcreateallocation.md)

[**D3DKMT_CREATEALLOCATIONFLAGS**](ns-d3dkmthk-_d3dkmt_createallocationflags.md)
