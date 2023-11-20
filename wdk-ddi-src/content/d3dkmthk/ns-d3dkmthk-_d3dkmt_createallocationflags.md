---
UID: NS:d3dkmthk._D3DKMT_CREATEALLOCATIONFLAGS
title: D3DKMT_CREATEALLOCATIONFLAGS (d3dkmthk.h)
description: Learn more about the D3DKMT_CREATEALLOCATIONFLAGS structure.
ms.date: 11/17/2023
keywords: ["D3DKMT_CREATEALLOCATIONFLAGS structure"]
ms.keywords: D3DKMT_CREATEALLOCATIONFLAGS, D3DKMT_CREATEALLOCATIONFLAGS structure [Display Devices], OpenGL_Structs_0b22984b-feef-4975-b7d9-596427c82b2b.xml, _D3DKMT_CREATEALLOCATIONFLAGS, d3dkmthk/D3DKMT_CREATEALLOCATIONFLAGS, display.d3dkmt_createallocationflags
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
req.typenames: D3DKMT_CREATEALLOCATIONFLAGS
f1_keywords:
 - _D3DKMT_CREATEALLOCATIONFLAGS
 - d3dkmthk/_D3DKMT_CREATEALLOCATIONFLAGS
 - D3DKMT_CREATEALLOCATIONFLAGS
 - d3dkmthk/D3DKMT_CREATEALLOCATIONFLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_CREATEALLOCATIONFLAGS
 - D3DKMT_CREATEALLOCATIONFLAGS
---

# D3DKMT_CREATEALLOCATIONFLAGS structure

## -description

**D3DKMT_CREATEALLOCATIONFLAGS** is a structure of bit fields that specify how to create an allocation in a call to the [**D3DKMTCreateAllocation**](nf-d3dkmthk-d3dkmtcreateallocation.md) function.

## -struct-fields

### -field CreateResource

Specifies whether to create a device-specific resource. If you set **CreateShared**, you must also set **CreateResource**.

### -field CreateShared

Specifies whether to create a resource shared across all devices. If you set **CreateShared**, you must also set **CreateResource**. For more information on using **CreateShared**, see the Remarks section.

### -field NonSecure

Specifies whether to create an allocation that can be opened by any process. If **NonSecure** is set, secure and non-secure processes can open the allocation.

### -field CreateProtected

This member is reserved and should be set to zero. Supported starting with Windows 7.

### -field RestrictSharedAccess

Specifies whether to create a resource shared across all devices but with some restrictions. Supported starting with Windows 7.

### -field ExistingSysMem

This member is reserved and should be set to zero. Supported starting with Windows 7. **ExistingSysMem**'s limitations follow:

* **ExistingSystemMem** and **ExistingSection** can't both be set for the same allocation. **ExistingSysMem** is set, **StandardAllocation** must also be set.

* **ExistingSysMem** must be correctly aligned. The existing system memory buffer that the D3D runtime gives to the kernel must be page-aligned and a multiple of page size, otherwise the kernel fails the call to [**D3DKMTCreateAllocation**](nf-d3dkmthk-d3dkmtcreateallocation.md).

* When the kernel creates a D3DKMDT_STANDARDALLOCATION_GDISURFACE type of standard allocation:

  * The runtime provides the size of the existing system buffer. Using this size, the kernel creates a standard allocation of GDISURFACE type with the following parameters which KMDs understand correctly:

    ``` c
    D3DKMDT_GDISURFACEDATA::Width = Size of ExistingSysMem buffer
    D3DKMDT_GDISURFACEDATA::Height = 1
    D3DKMDT_GDISURFACEDATA::Format = D3DDDIFMT_UNKNOWN
    D3DKMDT_GDISURFACEDATA::Type = D3DKMDT_GDISURFACE_TEXTURE_CROSSADAPTER
    ```

* Protect against ExistingSysMem pointer pointing to a DXGALLOCATION which is MemRotated  

  The kernel must protect against the scenario where user mode locks an existing DXGALLOCATION and uses the resulting CPU pointer to create an ExistingSysMem standard allocation. This case is invalid if the DXGALLOCATION VAD is MEM_ROTATE, i.e. if the allocation could be in VRAM. The kernel takes the following steps in the create standard allocation with ExistingSysMem call:

  * MemSecure the ExistingSysMem pointer.
  * VirtualQuery the memory. If attributes contain MEM_ROTATE then fail call.
  * MemSecure is only released when this allocation is freed to prevent memory from being changed behind kernel’s back.

### -field NtSecuritySharing

Specifies whether the allocation is shared with an NT handle, meaning that it doesn't have a global **D3DKMT_HANDLE** kernel-mode handle to the resource.

If **NtSecuritySharing** is set to 1 (TRUE):

* The allocation is shared using the [**D3DKMTShareObjects**](nf-d3dkmthk-d3dkmtshareobjects.md) function but doesn't have a global **D3DKMT_HANDLE** handle to the resource.
* **CreateShared**  must be set to 1.

For more information on using **NtSecuritySharing**, see the Remarks section. Supported starting with Windows 8.

### -field ReadOnly

Specifies whether the allocation can only be read from. Supported starting with Windows 8.

### -field CreateWriteCombined

This member is reserved and should be set to zero. Supported starting with Windows 8.

### -field CreateCached

This member is reserved and should be set to zero. Supported starting with Windows 8.

### -field SwapChainBackBuffer

This member is reserved and should be set to zero. Supported starting with Windows 8.

### -field CrossAdapter

If set, indicates that the resource is a shared [cross-adapter resource](/windows-hardware/drivers/display/using-cross-adapter-resources-in-a-hybrid-system#definition-and-properties-of-a-cross--adapter-resource).

### -field OpenCrossAdapter

If set, indicates that the resource is created by opening a cross adapter resource. Can't be used when allocation is created from the user mode. Supported starting with Windows 8.1 (WDDM 1.3).

### -field PartialSharedCreation

Specifies whether the allocation is created as a partial shared allocation. Supported starting with Windows 8.1 (WDDM 1.3).

### -field WriteWatch

Indicates whether to create the allocation with write-watch enabled. Supported starting with Windows 8.1 (WDDM 1.3).

### -field StandardAllocation

When set, instructs *Dxgkrnl* to create a standard allocation using [**pStandardAllocation**](ns-d3dkmthk-_d3dkmt_createallocation.md) instead of **pPrivateDriverData**. Either **ExistingSysMem** or **ExistingSection** (but not both) must also be set if **StandardAllocation** is set. Additionally, when creating a **StandardAllocation**, the **CreateShared** and **CrossAdapter** flags must also be set. Supported starting with Windows 10 version 1709 (WDDM 2.3).

### -field ExistingSection

When set, instructs *Dxgkrnl* to use the section handle ([**hSection**](../d3dukmdt/ns-d3dukmdt-_d3dddi_allocationinfo2.md)) instead of the system memory pointer (**pSystemMem**). **ExistingSystemMem** and **ExistingSection** can't both be set for the same allocation. If **ExistingSection** is set, **StandardAllocation** must also be set. Supported starting with Windows 10 version 1709 (WDDM 2.3).

### -field Zeroed

Specifies whether the allocation is to be zero-filled when created. Supported starting with Windows 8.

### -field Reserved

Supported starting with Windows 8.

This member is reserved and should be set to zero.

## -remarks

Objects to be shared by using the [**D3DKMTShareObjects**](nf-d3dkmthk-d3dkmtshareobjects.md) function must first be created with the **NtSecuritySharing** flag value set. This flag value is available in the **D3DKMT_CREATEALLOCATIONFLAGS**, [**D3DKMT_CREATEKEYEDMUTEX2_FLAGS**](ns-d3dkmthk-_d3dkmt_createkeyedmutex2_flags.md), and [**D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS**](../d3dukmdt/ns-d3dukmdt-_d3dddi_synchronizationobject_flags.md) structures.

Drivers should follow these guidelines on **D3DKMT_CREATEALLOCATIONFLAGS** sharing flags:

* If the allocation is not shared, set both  **CreateShared** and **NtSecuritySharing** to 0.
* If the allocation is shared with a **D3DKMT_HANDLE** data type, set **CreateShared** = 1 and **NtSecuritySharing** = 0.
* If the allocation is shared with an NT handle to the process (and without a global **D3DKMT_HANDLE** kernel-mode handle to the resource), set **CreateShared** = 1 and **NtSecuritySharing** = 1.

## -see-also

[**D3DKMTCreateAllocation**](nf-d3dkmthk-d3dkmtcreateallocation.md)

[**D3DKMT_CREATEALLOCATION**](ns-d3dkmthk-_d3dkmt_createallocation.md)
