---
UID: NC:d3dkmddi.DXGKCB_OPENPHYSICALMEMORYOBJECT
tech.root: display
title: DXGKCB_OPENPHYSICALMEMORYOBJECT
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: DxgkCbOpenPhysicalMemoryObject opens a physical memory object and associates it with an adapter.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_OPENPHYSICALMEMORYOBJECT
f1_keywords:
 - DXGKCB_OPENPHYSICALMEMORYOBJECT
 - d3dkmddi/DXGKCB_OPENPHYSICALMEMORYOBJECT
dev_langs:
 - c++
---

## -description

DxgkCbOpenPhysicalMemoryObject opens a physical memory object and associates it with an adapter.

## -parameters

### -param pArgs

Pointer to a [**DXGKARGCB_OPEN_PHYSICAL_MEMORY_OBJECT**](ns-d3dkmddi-dxgkargcb_open_physical_memory_object.md) structure that contains information about the physical memory object to open.

## -returns

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, returns an appropriate NTSTATUS error code.

## -prototype

```cpp
//Declaration

DXGKCB_OPENPHYSICALMEMORYOBJECT DxgkCbOpenPhysicalMemoryObject;

// Definition

NTSTATUS
DxgkCbOpenPhysicalMemoryObject(
    DXGKARGCB_OPEN_PHYSICAL_MEMORY_OBJECT *pArgs
    );
{...}

```

## -remarks

In order to create an address descriptor list (ADL) from a physical memory object, it must first be associated with an adapter. This can normally be done when the physical memory object is created by specifying the **hAdapter** parameter in a call to [**DxgkCbCreatePhysicalMemoryObject**](nc-d3dkmddi-dxgkcb_createphysicalmemoryobject.md). However, in some cases, the adapter handle is not available at the time the memory was allocated (for example, early in the boot process). In this case, the driver must call **DxgkCbOpenPhysicalMemoryObject** to associate the physical memory object with an adapter prior to calling [**DxgkCbAllocateAdl**](nc-d3dkmddi-dxgkcb_allocateadl.md).

## -see-also

[**DXGKARGCB_OPEN_PHYSICAL_MEMORY_OBJECT**](ns-d3dkmddi-dxgkargcb_open_physical_memory_object.md)

[**DxgkCbAllocateAdl**](nc-d3dkmddi-dxgkcb_allocateadl.md)

[**DxgkCbClosePhysicalMemoryObject**](nc-d3dkmddi-dxgkcb_closephysicalmemoryobject.md)

[**DxgkCbCreatePhysicalMemoryObject**](nc-d3dkmddi-dxgkcb_createphysicalmemoryobject.md)
