---
UID: NE:d3dkmddi._DXGK_PHYSICAL_MEMORY_TYPE
tech.root: display
title: DXGK_PHYSICAL_MEMORY_TYPE
ms.date: 05/13/2021
targetos: Windows
description: DXGK_PHYSICAL_MEMORY_TYPE indicates the type of physical memory being created by the driver.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_PHYSICAL_MEMORY_TYPE
 - DXGK_PHYSICAL_MEMORY_TYPE
f1_keywords:
 - _DXGK_PHYSICAL_MEMORY_TYPE
 - d3dkmddi/_DXGK_PHYSICAL_MEMORY_TYPE
 - DXGK_PHYSICAL_MEMORY_TYPE
 - d3dkmddi/DXGK_PHYSICAL_MEMORY_TYPE
dev_langs:
 - c++
---

## -description

**DXGK_PHYSICAL_MEMORY_TYPE** indicates the type of physical memory being created by the driver in a call to [**DxgkCbCreatePhysicalMemoryObject**](nc-d3dkmddi-dxgkcb_createphysicalmemoryobject.md).

## -enum-fields

### -field DXGK_PHYSICAL_MEMORY_TYPE_MDL

Allocate nonpageable memory in the form of an MDL. This is functionally equivalent to calling [**MmAllocatePagesForMdl**](../wdm/nf-wdm-mmallocatepagesformdl.md).

### -field DXGK_PHYSICAL_MEMORY_TYPE_CONTIGUOUS_MEMORY

Allocate contiguous nonpageable memory. This is functionally equivalent to calling [**MmAllocateContiguousMemory**](../ntddk/nf-ntddk-mmallocatecontiguousmemory.md).

### -field DXGK_PHYSICAL_MEMORY_TYPE_SECTION

Allocate memory that can be mapped into one or more processes. This represents memory that would normally be allocated from [**ZwCreateSection**](../wdm/nf-wdm-zwcreatesection.md).

### -field DXGK_PHYSICAL_MEMORY_TYPE_IO_SPACE

Wrap an existing IO-space range provided by the driver.

## -remarks

**DXGK_PHYSICAL_MEMORY_TYPE** is passed as a member of the [**DXGKARGCB_CREATE_PHYSICAL_MEMORY_OBJECT**](ns-d3dkmddi-dxgkargcb_create_physical_memory_object.md) arguments.

## -see-also

[**DXGKARGCB_CREATE_PHYSICAL_MEMORY_OBJECT**](ns-d3dkmddi-dxgkargcb_create_physical_memory_object.md)

[**DxgkCbCreatePhysicalMemoryObject**](nc-d3dkmddi-dxgkcb_createphysicalmemoryobject.md)