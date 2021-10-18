---
UID: NS:d3dkmddi._DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE
title: DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE (d3dkmddi.h)
description: DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE is used with the DxgkCbReserveGpuVirtualAddressRangedevice driver interface (DDI) to allow the kernel mode driver to reserve a graphics processing unit (GPU) virtual address range during creation of a process.
old-location: display\dxgkargcb_reservegpuvirtualaddressrange.htm
ms.date: 10/13/2021
keywords: ["DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE structure"]
ms.keywords: DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE, DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE structure [Display Devices], _DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE, *INOUT_PDXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE, d3dkmddi/DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE, display.dxgkargcb_reservegpuvirtualaddressrange
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10 (WDDM 2.0)
req.target-min-winversvr: Windows Server 2016
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
req.typenames: DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE
f1_keywords:
 - _DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE
 - d3dkmddi/_DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE
 - DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE
 - d3dkmddi/DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE
 - DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE
---

# DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE structure

## -description

**DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE** contains the arguments used by the [**DXGKCB_RESERVEGPUVIRTUALADDRESSRANGE**](nc-d3dkmddi-dxgkcb_reservegpuvirtualaddressrange.md) callback function, to allow the kernel-mode display driver to reserve a graphics processing unit (GPU) virtual address range during creation of a process.

## -struct-fields

### -field hDxgkProcess

[in] The process handle that was passed to [**DxgkDdiCreateProcess**](nc-d3dkmddi-dxgkddi_createprocess.md).

### -field SizeInBytes

[in] The size in bytes of the virtual address range. **SizeInBytes** must be set to an integral multiple of the address space covered by a single page table entry.

### -field Alignment

[in] The number of bytes to align the start address to. Must be a multiple of the address space covered by a single page table entry and a power of 2.

### -field StartVirtualAddress

[out] The starting location of the reserved address range.

### -field BaseAddress

[in] The base virtual address of the virtual address range in bytes. It must be aligned to the size of the address space, covered by a single page table entry.

### -field AllowUserModeMapping

[in] When set, allows the user-mode driver to map allocations to the range.

### -field Flags

[in] A single value containing the flags set in the structure.

## -see-also

[**DXGKCB_RESERVEGPUVIRTUALADDRESSRANGE**](nc-d3dkmddi-dxgkcb_reservegpuvirtualaddressrange.md)

[**DxgkDdiCreateProcess**](nc-d3dkmddi-dxgkddi_createprocess.md)
