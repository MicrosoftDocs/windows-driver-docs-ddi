---
UID: NS:d3dkmddi._DXGKARGCB_ALLOCATE_ADL
tech.root: display
title: DXGKARGCB_ALLOCATE_ADL
ms.date: 05/13/2021
targetos: Windows
description: DXGKARGCB_ALLOCATE_ADL contains the information used by the DxgkCbAllocateAdl callback function to create an address descriptor list (ADL).
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: DXGKARGCB_ALLOCATE_ADL
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_ALLOCATE_ADL
 - DXGKARGCB_ALLOCATE_ADL
f1_keywords:
 - _DXGKARGCB_ALLOCATE_ADL
 - d3dkmddi/_DXGKARGCB_ALLOCATE_ADL
 - DXGKARGCB_ALLOCATE_ADL
 - d3dkmddi/DXGKARGCB_ALLOCATE_ADL
dev_langs:
 - c++
---

## -description

DXGKARGCB_ALLOCATE_ADL contains the information used by the [**DxgkCbAllocateAdl**](nc-d3dkmddi-dxgkcb_allocateadl.md) callback function to create an address descriptor list (ADL).

## -struct-fields

### -field hAdapterMemoryObject

The adapter memory object that describes the underlying logical memory used to build the ADL. This object was created via [**DxgkCbCreatePhysicalMemoryObject**](nc-d3dkmddi-dxgkcb_createphysicalmemoryobject.md) or later opened via [**DxgkCbOpenPhysicalMemoryObject**](nc-d3dkmddi-dxgkcb_openphysicalmemoryobject.md).

### -field Offset

The offset, in bytes, from the start of the physical memory object. This value must be a multiple of PAGE_SIZE.

### -field Size

The total number of bytes to allocate for the ADL. This value must be a multiple of PAGE_SIZE, such that the number of pages in the ADL will be **Size**/PAGE_SIZE.

### -field Flags

### -field Flags.RequireContiguous

Indicates that the driver is requesting an ADL that describes a contiguous range of memory, instead of scattered pages. This flag is only valid if the physical memory object represented by *hAdapterMemoryObject* was allocated as **DXGK_PHYSICAL_MEMORY_TYPE_CONTIGUOUS_MEMORY** or **DXGK_PHYSICAL_MEMORY_TYPE_IO_SPACE**.

### -field Flags.PreferContiguous

Provides the driver with a way to optimally request a contiguous ADL when possible. When DMA remapping is enabled, ADLs will refer to ranges of logical address space; however, drivers might not be able to use contiguous ADLs in all code paths. Non-contiguous ADLs for logical memory can become costly since they require allocation of a separate PFN array, similar to an MDL, to represent the memory. When possible, the driver should specify this flag to indicate that an ADL can be represented with just the base address.

### -field Flags.Reserved

Reserved; must be set to zero.

### -field Flags.Value

An alternative way to access the bits.

### -field pAdl

On a successful call to [**DxgkCbAllocateAdl**](nc-d3dkmddi-dxgkcb_allocateadl.md), points to the [**DXGK_ADL**](ns-d3dkmddi-dxgk_adl.md) structure with a list of page addresses that can be used to program the hardware.

## -see-also

[**DxgkCbAllocateAdl**](nc-d3dkmddi-dxgkcb_allocateadl.md)

[**DxgkCbCreatePhysicalMemoryObject**](nc-d3dkmddi-dxgkcb_createphysicalmemoryobject.md)

[**DxgkCbOpenPhysicalMemoryObject**](nc-d3dkmddi-dxgkcb_openphysicalmemoryobject.md)
