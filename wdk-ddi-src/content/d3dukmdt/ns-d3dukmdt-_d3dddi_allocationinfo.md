---
UID: NS:d3dukmdt._D3DDDI_ALLOCATIONINFO
title: D3DDDI_ALLOCATIONINFO (d3dukmdt.h)
description: Learn more about the D3DDDI_ALLOCATIONINFO structure.
tech.root: display
ms.date: 03/21/2023
keywords: ["D3DDDI_ALLOCATIONINFO structure"]
ms.keywords: D3DDDI_ALLOCATIONINFO, D3DDDI_ALLOCATIONINFO structure [Display Devices], D3D_other_Structs_5125c057-c4b7-45fd-b7d9-9ebcfce4fff7.xml, _D3DDDI_ALLOCATIONINFO, d3dukmdt/D3DDDI_ALLOCATIONINFO, display.d3dddi_allocationinfo
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
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
req.typenames: D3DDDI_ALLOCATIONINFO
f1_keywords:
 - _D3DDDI_ALLOCATIONINFO
 - d3dukmdt/_D3DDDI_ALLOCATIONINFO
 - D3DDDI_ALLOCATIONINFO
 - d3dukmdt/D3DDDI_ALLOCATIONINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _D3DDDI_ALLOCATIONINFO
 - D3DDDI_ALLOCATIONINFO
---

# D3DDDI_ALLOCATIONINFO structure

## -description

The **D3DDDI_ALLOCATIONINFO** structure describes an allocation for WDDM v1. User-mode graphics clients should use [**D3DDDI_ALLOCATIONINFO2**](ns-d3dukmdt-_d3dddi_allocationinfo2.md) instead.

## -struct-fields

### -field hAllocation

[out] A **D3DKMT_HANDLE** that represents a kernel-mode handle to the allocation. This handle is associated with the kernel-mode resource handle (if non-NULL) that the Direct3D runtime's [**pfnAllocateCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_allocatecb.md) function returns in the **hKMResource** member of the [**D3DDDICB_ALLOCATE**](../d3dumddi/ns-d3dumddi-_d3dddicb_allocate.md) structure. The user-mode display driver can use this kernel-mode allocation handle to reference the allocation in the command buffer.

### -field pSystemMem

[in] A pointer to system memory that the Direct3D runtime preallocated. Otherwise, this member is NULL if the allocation is to use video memory.

If the allocation is in system memory, the user-mode display driver should assign the buffer in the **pSysMem** member of the [**D3DDDI_SURFACEINFO**](../d3dukmdt/ns-d3dukmdt-_d3dddi_surfaceinfo.md) structure for the resource to **pSystemMem**. This buffer is specified when the Direct3D runtime calls the user-mode display driver's [**CreateResource**](../d3dumddi/nc-d3dumddi-pfnd3dddi_createresource.md) function to create resources.

### -field pPrivateDriverData

[in/out,opt] A pointer to buffer that contains optional private data that might be required by the display miniport driver to create the allocation. The display miniport driver can also return data in the buffer. When the contents of the buffer are passed to the display miniport driver, the contents must be in a format that the display miniport driver can process.

### -field PrivateDriverDataSize

[in] Size in bytes of the private data.

### -field VidPnSourceId

[in] The zero-based VidPN identification number of the video present source in a path of a video present network (VidPN) topology if the allocation is for the primary surface. The driver should set **VidPnSourceId** only for primary allocation types and not for any other type of allocation. If the driver sets **VidPnSourceId** for any other allocation type in a call to the [**pfnAllocateCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_allocatecb.md) function, **pfnAllocateCb** returns D3DDDI_ID_NOTAPPLICABLE.

When the DirectX graphics kernel subsystem initiates the creation of the allocation for the shared primary surface, the display miniport driver can determine the identification number from the **VidPnSourceId** member of the [**D3DKMDDI_SHAREDPRIMARYSURFACEDATA**](../d3dkmdt/ns-d3dkmdt-_d3dkmdt_sharedprimarysurfacedata.md) structure that the **pPrivateDriverData** member of the [**DXGK_ALLOCATIONINFO**](../d3dkmddi/ns-d3dkmddi-_dxgk_allocationinfo.md) structure points to.

### -field Flags

[in] A union that contains either a structure or a 32-bit value that identifies the type of allocation.

### -field Flags.Primary

[in] A UINT that specifies whether the allocation is part of the desktop. Such an allocation is implicitly accessible to the CPU. A primary allocation can be either pinned down at creation or not pinned down at creation.

Setting this member is equivalent to setting the first bit of the 32-bit **Value** member (0x00000001).

### -field Flags.Stereo

[in] Supported beginning with Windows 8. A UINT that specifies whether the allocation is a stereo primary allocation. The **Stereo** member can be set only when the **Primary** member is set.

Setting this member is equivalent to setting the second bit of the 32-bit **Value** member (0x00000002).

### -field Flags.Reserved

[in] This member is reserved and should be set to zero.

### -field Flags.Value

[in] A 32-bit value that identifies the type of allocation.

## -remarks

When the user-mode display driver sets the **Primary** bit-field flag in the **Flags** member of D3DDDI_ALLOCATIONINFO, certain restrictions apply to the [**DXGK_ALLOCATIONINFO**](../d3dkmddi/ns-d3dkmddi-_dxgk_allocationinfo.md) structure in the **pAllocationInfo** member of the [**DXGKARG_CREATEALLOCATION**](../d3dkmddi/ns-d3dkmddi-_dxgkarg_createallocation.md) structure for the allocation in a call to the display miniport driver's [**DxgkDdiCreateAllocation**](../d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation.md) function. These restrictions include the following:

* The allocation is allocated according to preferences; otherwise, the allocation defaults to the supported write segment set, and all of the specified segments in the write segment set must be CPU-accessible.

* The display miniport driver cannot set the following bit-field flags in the **Flags** member of [**DXGK_ALLOCATIONINFO**](../d3dkmddi/ns-d3dkmddi-_dxgk_allocationinfo.md):

* PermanentSysMem
* Cached
* Protected
* ExistingSysMem
* ExistingKernelSysMem

The D3DDDI_ID_NOTAPPLICABLE constant is defined in *D3dukmdt.h*.

## -see-also

[**CreateResource**](../d3dumddi/nc-d3dumddi-pfnd3dddi_createresource.md)

[**D3DDDICB_ALLOCATE**](../d3dumddi/ns-d3dumddi-_d3dddicb_allocate.md)

[**D3DDDI_ALLOCATIONINFO2**]((ns-d3dukmdt-_d3dddi_allocationinfo2.md))

[**D3DDDI_SURFACEINFO**](ns-d3dukmdt-_d3dddi_surfaceinfo.md)

[**D3DKMDDI_SHAREDPRIMARYSURFACEDATA**](../d3dkmdt/ns-d3dkmdt-_d3dkmdt_sharedprimarysurfacedata.md)

[**DXGKARG_CREATEALLOCATION**](../d3dkmddi/ns-d3dkmddi-_dxgkarg_createallocation.md)

[**DXGK_ALLOCATIONINFO**](../d3dkmddi/ns-d3dkmddi-_dxgk_allocationinfo.md)

[**DxgkDdiCreateAllocation**](../d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation.md)

[**pfnAllocateCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_allocatecb.md)
