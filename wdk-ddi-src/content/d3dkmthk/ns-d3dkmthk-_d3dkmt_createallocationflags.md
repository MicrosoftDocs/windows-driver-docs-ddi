---
UID: NS:d3dkmthk._D3DKMT_CREATEALLOCATIONFLAGS
title: D3DKMT_CREATEALLOCATIONFLAGS (d3dkmthk.h)
description: Learn more about the D3DKMT_CREATEALLOCATIONFLAGS structure.
ms.date: 07/12/2023
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

The **D3DKMT_CREATEALLOCATIONFLAGS** structure identifies how to create an allocation in a call to the [**D3DKMTCreateAllocation**](nf-d3dkmthk-d3dkmtcreateallocation.md) function.

## -struct-fields

### -field CreateResource

A UINT value that specifies whether to create a device-specific resource. If you set **CreateShared**, you must also set **CreateResource**.

Setting this member is equivalent to setting the first bit of a 32-bit value (0x00000001).

### -field CreateShared

A UINT value that specifies whether to create a resource shared across all devices. If you set **CreateShared**, you must also set **CreateResource**. For more information on using **CreateShared**, see the Remarks section.

Setting this member is equivalent to setting the second bit of a 32-bit value (0x00000002).

### -field NonSecure

A UINT value that specifies whether to create an allocation that can be opened by any process. If **NonSecure** is set, secure and non-secure processes can open the allocation.

Setting this member is equivalent to setting the third bit of a 32-bit value (0x00000004).

### -field CreateProtected

This member is reserved and should be set to zero.

Supported starting with Windows 7.

### -field RestrictSharedAccess

A UINT value that specifies whether to create a resource shared across all devices but with some restrictions.

Supported starting with Windows 7.

### -field ExistingSysMem

This member is reserved and should be set to zero.

Supported starting with Windows 7.

### -field NtSecuritySharing

A UINT value that specifies whether the allocation is shared with an NT handle, meaning that it  does not have a global **D3DKMT_HANDLE** kernel-mode handle to the resource.

If **NtSecuritySharing** is set to 1 (TRUE), the allocation is shared using the [**D3DKMTShareObjects**](nf-d3dkmthk-d3dkmtshareobjects.md) function but does not have a global **D3DKMT_HANDLE** handle to the resource.

If **NtSecuritySharing** is set to 1,  **CreateShared**  must be set to 1. For more information on using **NtSecuritySharing**, see the Remarks section.

Supported starting with Windows 8.

### -field ReadOnly

A UINT value that specifies whether the allocation can only be read from.

Supported starting with Windows 8.

### -field CreateWriteCombined

This member is reserved and should be set to zero. Setting this member is equivalent to setting the seventh bit of a 32-bit value (0x00000100).

Supported starting with Windows 8.

### -field CreateCached

This member is reserved and should be set to zero. Setting this member is equivalent to setting the eighth bit of a 32-bit value (0x00000200).

Supported starting with Windows 8.

### -field SwapChainBackBuffer

This member is reserved and should be set to zero. Setting this member is equivalent to setting the seventh bit of a 32-bit value (0x00000100).

Supported starting with Windows 8.

### -field CrossAdapter

If set, indicates that the resource is a shared [cross-adapter resource](/windows-hardware/drivers/display/using-cross-adapter-resources-in-a-hybrid-system#definition-and-properties-of-a-cross--adapter-resource).

### -field OpenCrossAdapter

If set, indicates that the resource is created by opening a cross adapter resource. Can't be used when allocation is created from the user mode.

### -field PartialSharedCreation

### -field WriteWatch

### -field StandardAllocation

### -field ExistingSection

### -field Zeroed

### -field Reserved

Supported starting with Windows 8.

This member is reserved and should be set to zero. Setting this member is equivalent to setting the remaining 26 bits (0xFFFFFFC0) of a 32-bit value to zeros.

## -remarks

Objects to be shared by using the [**D3DKMTShareObjects**](nf-d3dkmthk-d3dkmtshareobjects.md) function must first be created with the **NtSecuritySharing** flag value set. This flag value is available in the **D3DKMT_CREATEALLOCATIONFLAGS**, [**D3DKMT_CREATEKEYEDMUTEX2_FLAGS**](ns-d3dkmthk-_d3dkmt_createkeyedmutex2_flags.md), and [**D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS**](../d3dukmdt/ns-d3dukmdt-_d3dddi_synchronizationobject_flags.md) structures.

Drivers should follow these guidelines on **D3DKMT_CREATEALLOCATIONFLAGS** sharing flags:

* If the allocation is not shared, set both  **CreateShared** and **NtSecuritySharing** to 0.
* If the allocation is shared with a **D3DKMT_HANDLE** data type, set **CreateShared** = 1 and **NtSecuritySharing** = 0.
* If the allocation is shared with an NT handle to the process (and without a global **D3DKMT_HANDLE** kernel-mode handle to the resource), set **CreateShared** = 1 and **NtSecuritySharing** = 1.

## -see-also

[**D3DKMTCreateAllocation**](nf-d3dkmthk-d3dkmtcreateallocation.md)

[**D3DKMT_CREATEALLOCATION**](ns-d3dkmthk-_d3dkmt_createallocation.md)
