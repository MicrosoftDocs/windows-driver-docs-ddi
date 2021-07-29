---
UID: NS:d3dkmddi._DXGKARGCB_OPEN_PHYSICAL_MEMORY_OBJECT
tech.root: display
title: DXGKARGCB_OPEN_PHYSICAL_MEMORY_OBJECT
ms.date: 05/13/2021
targetos: Windows
description: The DXGKARGCB_OPEN_PHYSICAL_MEMORY_OBJECT structure contains the information used by the DxgkCbOpenPhysicalMemoryObject callback function to open a physical memory object.
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
req.typenames: DXGKARGCB_OPEN_PHYSICAL_MEMORY_OBJECT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_OPEN_PHYSICAL_MEMORY_OBJECT
 - DXGKARGCB_OPEN_PHYSICAL_MEMORY_OBJECT
f1_keywords:
 - _DXGKARGCB_OPEN_PHYSICAL_MEMORY_OBJECT
 - d3dkmddi/_DXGKARGCB_OPEN_PHYSICAL_MEMORY_OBJECT
 - DXGKARGCB_OPEN_PHYSICAL_MEMORY_OBJECT
 - d3dkmddi/DXGKARGCB_OPEN_PHYSICAL_MEMORY_OBJECT
dev_langs:
 - c++
---

## -description

The **DXGKARGCB_OPEN_PHYSICAL_MEMORY_OBJECT** structure contains the information used by the [**DxgkCbOpenPhysicalMemoryObject**](nc-d3dkmddi-dxgkcb_openphysicalmemoryobject.md) callback function to open a physical memory object.

## -struct-fields

### -field hPhysicalMemoryObject

The physical memory object handle that was returned from a call to [**DxgkCbCreatePhysicalMemoryObject**](nc-d3dkmddi-dxgkcb_createphysicalmemoryobject.md).

### -field hAdapter

A handle to any adapter that is part of the logical adapter to open the physical object against. This can be any physical adapter that is linked together in a linked display adapter (LDA) chain.

### -field hAdapterMemoryObject

Field in which a handle to the opened physical memory object for this adapter is returned.

## -remarks

If the driver [creates a physical memory object](nc-d3dkmddi-dxgkcb_createphysicalmemoryobject.md) and specifies a non-NULL value for *hAdapter* in that call, then it must not call **DxgkCbOpenPhysicalObject** again. Doing so will return a failure indicating that the physical object is already opened against the adapter.

At this time, a physical memory object may only be opened by a single adapter. Attempting to open the object on a second adapter will fail.

Opening a physical memory object against one physical adapter is sufficient. This guarantees that all physical adapters in the logical adapter (all linked adapters) have a mirrored view of this memory.

## -see-also

[**DxgkCbCreatePhysicalMemoryObject**](nc-d3dkmddi-dxgkcb_createphysicalmemoryobject.md)

[**DxgkCbOpenPhysicalMemoryObject**](nc-d3dkmddi-dxgkcb_openphysicalmemoryobject.md)
