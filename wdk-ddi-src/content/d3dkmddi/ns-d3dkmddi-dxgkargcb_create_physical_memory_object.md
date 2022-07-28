---
UID: NS:d3dkmddi._DXGKARGCB_CREATE_PHYSICAL_MEMORY_OBJECT
tech.root: display
title: DXGKARGCB_CREATE_PHYSICAL_MEMORY_OBJECT
ms.date: 06/24/2022
targetos: Windows
description: The DXGKARGCB_CREATE_PHYSICAL_MEMORY_OBJECT structure contains the information used by the DxgkCbCreatePhysicalMemoryObject callback function to create physical memory.
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
req.target-min-winversvr: Windows Server 2022 (WDDM 2.9)
req.target-type: 
req.typenames: DXGKARGCB_CREATE_PHYSICAL_MEMORY_OBJECT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_CREATE_PHYSICAL_MEMORY_OBJECT
 - DXGKARGCB_CREATE_PHYSICAL_MEMORY_OBJECT
f1_keywords:
 - _DXGKARGCB_CREATE_PHYSICAL_MEMORY_OBJECT
 - d3dkmddi/_DXGKARGCB_CREATE_PHYSICAL_MEMORY_OBJECT
 - DXGKARGCB_CREATE_PHYSICAL_MEMORY_OBJECT
 - d3dkmddi/DXGKARGCB_CREATE_PHYSICAL_MEMORY_OBJECT
dev_langs:
 - c++
---

## -description

The **DXGKARGCB_CREATE_PHYSICAL_MEMORY_OBJECT** structure contains the information used by the [**DXGKCB_CREATEPHYSICALMEMORYOBJECT**](nc-d3dkmddi-dxgkcb_createphysicalmemoryobject.md) callback function to create physical memory.

## -struct-fields

### -field hAdapter

The adapter for which this physical memory will be associated. This parameter is optional and can be NULL. If it is NULL, the driver must call [**DXGKCB_OPENPHYSICALMEMORYOBJECT**](nc-d3dkmddi-dxgkcb_openphysicalmemoryobject.md) before creating an address descriptor list (ADL). See Remarks for more information.

### -field Size

The size, in bytes, of the physical memory being requested. If **Type** is **DXGK_PHYSICAL_MEMORY_TYPE_IO_SPACE**, **Size** refers to the size of the IO space region provided by the driver.

### -field Context

A pointer-size piece of context data that *Dxgkrnl* will store alongside the physical memory object for debugging purposes. This value is never directly used or dereferenced by *Dxgkrnl* in any way. This may be any value of the driver's choosing, such as the memory address to a driver-owned object that owns this physical memory object.

### -field Type

A [**DXGK_PHYSICAL_MEMORY_TYPE**](ne-d3dkmddi-dxgk_physical_memory_type.md) value that specifies the type of physical memory to create. If **Type** is **DXGK_PHYSICAL_MEMORY_TYPE_SECTION**, then the allocation attributes of the section object are always SEC_COMMIT (PF-mapped section), and the cache type is determines by **CacheType**.

### -field CacheType

The cache type of the pages. If **Type** is **DXGK_PHYSICAL_MEMORY_TYPE_SECTION**, **CacheType** must be either cached, or write-combined.

### -field Mdl

Used only when **Type** is **DXGK_PHYSICAL_MEMORY_TYPE_MDL**.

### -field Mdl.LowAddress

Used only when **Type** is **DXGK_PHYSICAL_MEMORY_TYPE_MDL**. See [**MmAllocatePagesForMdlEx**](../wdm/nf-wdm-mmallocatepagesformdlex.md) for details.

### -field Mdl.HighAddress

Used only when **Type** is **DXGK_PHYSICAL_MEMORY_TYPE_MDL**. See [**MmAllocatePagesForMdlEx**](../wdm/nf-wdm-mmallocatepagesformdlex.md) for details.

### -field Mdl.SkipBytes

Used only when **Type** is **DXGK_PHYSICAL_MEMORY_TYPE_MDL**. See [**MmAllocatePagesForMdlEx**](../wdm/nf-wdm-mmallocatepagesformdlex.md) for details.

### -field Mdl.Flags

Used only when **Type** is **DXGK_PHYSICAL_MEMORY_TYPE_MDL**. See [**MmAllocatePagesForMdlEx**](../wdm/nf-wdm-mmallocatepagesformdlex.md) for details.

### -field ContiguousMemory

Used only when **Type** is **DXGK_PHYSICAL_MEMORY_TYPE_CONTIGUOUS_MEMORY**.

### -field ContiguousMemory.LowestAcceptableAddress

Used only when **Type** is **DXGK_PHYSICAL_MEMORY_TYPE_CONTIGUOUS_MEMORY**. See [**MmAllocateContiguousMemorySpecifyCache**](../ntddk/nf-ntddk-mmallocatecontiguousmemoryspecifycache.md) for details.

### -field ContiguousMemory.HighestAcceptableAddress

Used only when **Type** is **DXGK_PHYSICAL_MEMORY_TYPE_CONTIGUOUS_MEMORY**. See [**MmAllocateContiguousMemorySpecifyCache**](../ntddk/nf-ntddk-mmallocatecontiguousmemoryspecifycache.md) for details.

### -field ContiguousMemory.BoundaryAddressMultiple

Used only when **Type** is **DXGK_PHYSICAL_MEMORY_TYPE_CONTIGUOUS_MEMORY**. See [**MmAllocateContiguousMemorySpecifyCache**](../ntddk/nf-ntddk-mmallocatecontiguousmemoryspecifycache.md) for details.

### -field Section

Used only when **Type** is **DXGK_PHYSICAL_MEMORY_TYPE_SECTION**.

### -field Section.DesiredAccess

Used only when **Type** is **DXGK_PHYSICAL_MEMORY_TYPE_SECTION**. See [**ZwCreateSection**](../wdm/nf-wdm-zwcreatesection.md) for details.

### -field Section.ObjectAttributes

Used only when **Type** is **DXGK_PHYSICAL_MEMORY_TYPE_SECTION**. See [**ZwCreateSection**](../wdm/nf-wdm-zwcreatesection.md) for details.

### -field Section.PageProtection

Used only when **Type** is **DXGK_PHYSICAL_MEMORY_TYPE_SECTION**. This value should be one of the following values: PAGE_READONLY, PAGE_READWRITE, PAGE_EXECUTE, or PAGE_WRITECOPY. Do not specify cache attributes (e.g. SEC_WRITECOMBINED) in this field. The allocated attributes of the section object are always SEC_COMMIT (PF-mapped section), and the cache type is determines by **CacheType**. See [**ZwCreateSection**](../wdm/nf-wdm-zwcreatesection.md) for details.

### -field Section.AllocationAttributes

Used only when **Type** is **DXGK_PHYSICAL_MEMORY_TYPE_SECTION**. See [**ZwCreateSection**](../wdm/nf-wdm-zwcreatesection.md) for details.

### -field IOSpace

Used only when **Type** is **DXGK_PHYSICAL_MEMORY_TYPE_IO_SPACE**.

### -field IOSpace.BaseAddress

Used only when **Type** is **DXGK_PHYSICAL_MEMORY_TYPE_IO_SPACE**. Specifies the starting physical address of the IO space region. This value must be aligned to a multiple of PAGE_SIZE.

### -field hPhysicalMemoryObject

On a successful call to [**DXGKCB_CREATEPHYSICALMEMORYOBJECT**](nc-d3dkmddi-dxgkcb_createphysicalmemoryobject.md), this is an opaque handle back to a *Dxgkrnl*-managed physical memory object. The physical memory object can be provided to other documented memory management functions to map a virtual address for CPU access. This handle can be closed by calling [**DXGKCB_DESTROYPHYSICALMEMORYOBJECT**](nc-d3dkmddi-dxgkcb_destroyphysicalmemoryobject.md).

### -field hAdapterMemoryObject

On a successful call to [**DXGKCB_CREATEPHYSICALMEMORYOBJECT**](nc-d3dkmddi-dxgkcb_createphysicalmemoryobject.md), this is an opaque handle back to a *Dxgkrnl*-managed adapter memory object. The adapter memory object can be provided to other documented memory management functions to generate an ADL for GPU access. If **hAdapter** is NULL, this value will be NULL and the driver must call [**DXGKCB_OPENPHYSICALMEMORYOBJECT**](nc-d3dkmddi-dxgkcb_openphysicalmemoryobject.md) to create this handle. This handle can be closed by calling [**DXGKCB_CLOSEPHYSICALMEMORYOBJECT**](nc-d3dkmddi-dxgkcb_closephysicalmemoryobject.md), or may be provided to [**DXGKCB_DESTROYPHYSICALMEMORYOBJECT**](nc-d3dkmddi-dxgkcb_destroyphysicalmemoryobject.md) (but not both).

## -remarks

The *hAdapter* field is optional when creating a physical memory object, but that object must be opened against an adapter in a call to [**DXGKCB_OPENPHYSICALMEMORYOBJECT**](nc-d3dkmddi-dxgkcb_openphysicalmemoryobject.md) before an [ADL can be created](nc-d3dkmddi-dxgkcb_allocateadl.md). This is because an ADL represents logical memory, and each logical adapter has a unique domain. It does not matter which physical adapter the memory is created against. It will be opened by the logical adapter that the physical adapter belongs to and will be mapped to all linked physical adapters.

See [IOMMU DMA remapping](/windows-hardware/drivers/display/iommu-dma-remapping) for more information.

## -see-also

[**DXGK_PHYSICAL_MEMORY_TYPE**](ne-d3dkmddi-dxgk_physical_memory_type.md)

[**DXGKCB_ALLOCATEADL**](nc-d3dkmddi-dxgkcb_allocateadl.md)

[**DXGKCB_CLOSEPHYSICALMEMORYOBJECT**](nc-d3dkmddi-dxgkcb_closephysicalmemoryobject.md)

[**DXGKCB_CREATEPHYSICALMEMORYOBJECT**](nc-d3dkmddi-dxgkcb_createphysicalmemoryobject.md)

[**DXGKCB_DESTROYPHYSICALMEMORYOBJECT**](nc-d3dkmddi-dxgkcb_destroyphysicalmemoryobject.md)

[**DXGKCB_OPENPHYSICALMEMORYOBJECT**](nc-d3dkmddi-dxgkcb_openphysicalmemoryobject.md)

[**MmAllocateContiguousMemorySpecifyCache**](../ntddk/nf-ntddk-mmallocatecontiguousmemoryspecifycache.md)

[**MmAllocatePagesForMdlEx**](../wdm/nf-wdm-mmallocatepagesformdlex.md)

[**ZwCreateSection**](../wdm/nf-wdm-zwcreatesection.md)
