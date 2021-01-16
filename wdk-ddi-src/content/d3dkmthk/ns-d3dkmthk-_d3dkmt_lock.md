---
UID: NS:d3dkmthk._D3DKMT_LOCK
title: _D3DKMT_LOCK (d3dkmthk.h)
description: The D3DKMT_LOCK structure describes parameters for locking an allocation.
old-location: display\d3dkmt_lock.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_LOCK structure"]
ms.keywords: D3DKMT_LOCK, D3DKMT_LOCK structure [Display Devices], OpenGL_Structs_08e60652-b888-4a1e-a9c6-3dee8f0fb50d.xml, _D3DKMT_LOCK, d3dkmthk/D3DKMT_LOCK, display.d3dkmt_lock
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
targetos: Windows
tech.root: display
req.typenames: D3DKMT_LOCK
f1_keywords:
 - _D3DKMT_LOCK
 - d3dkmthk/_D3DKMT_LOCK
 - D3DKMT_LOCK
 - d3dkmthk/D3DKMT_LOCK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_LOCK
 - D3DKMT_LOCK
---

# _D3DKMT_LOCK structure


## -description

The D3DKMT_LOCK structure describes parameters for locking an allocation.

## -struct-fields

### -field hDevice

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the device that the allocation is associated with.

### -field hAllocation

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the allocation to lock.

### -field PrivateDriverData

[in] A UINT value that specifies 32 bits of private data (for example, MIP level) that is sent from the OpenGL ICD to the display miniport driver's <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_acquireswizzlingrange">DxgkDdiAcquireSwizzlingRange</a> function.

### -field NumPages

[in] The number of pages in the page list that <b>pPages</b> specifies.

### -field pPages

[in] An array of pages to lock. Each page in the array is described by an integer offset. Zero means the first page in the surface, one means the second, and so on.

### -field pData

[out] A pointer to the memory that is returned from the display miniport driver and memory manager. When locking a memory page list, the pointer that is returned is a pointer to the first memory page.

### -field Flags

[in] A <a href="/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddicb_lockflags">D3DDDICB_LOCKFLAGS</a> structure that identifies, in bit-field flags, how to lock the allocation.

Note that specifying some flags together is invalid and that some flags depend on other flags. For more information about these combinations, see the Remarks section of <a href="/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddicb_lockflags">D3DDDICB_LOCKFLAGS</a>.

### -field GpuVirtualAddress

This member is reserved and should be set to zero.

This member is available beginning with Windows 7.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddicb_lockflags">D3DDDICB_LOCKFLAGS</a>



<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtlock">D3DKMTLock</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_acquireswizzlingrange">DxgkDdiAcquireSwizzlingRange</a>

