---
UID: NC:d3dkmddi.DXGKCB_CREATEPHYSICALMEMORYOBJECT
tech.root: display
title: DXGKCB_CREATEPHYSICALMEMORYOBJECT
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: The DxgkCbCreatePhysicalMemoryObject callback function creates physical memory for the driver.
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
 - DXGKCB_CREATEPHYSICALMEMORYOBJECT
f1_keywords:
 - DXGKCB_CREATEPHYSICALMEMORYOBJECT
 - d3dkmddi/DXGKCB_CREATEPHYSICALMEMORYOBJECT
dev_langs:
 - c++
---

## -description

The **DxgkCbCreatePhysicalMemoryObject** callback function creates physical memory for the driver.

## -parameters

### -param pArgs

Pointer to a [**DXGKARGCB_CREATE_PHYSICAL_MEMORY_OBJECT**](ns-d3dkmddi-dxgkargcb_create_physical_memory_object.md) structure that contains information about the physical memory to create.

## -returns

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, returns an appropriate NTSTATUS error code.

## -prototype

```cpp
//Declaration

DXGKCB_CREATEPHYSICALMEMORYOBJECT DxgkCbCreatePhysicalMemoryObject;

// Definition

NTSTATUS DxgkCbCreatePhysicalMemoryObject(
    DXGKARGCB_CREATE_PHYSICAL_MEMORY_OBJECT *pArgs
    );
{...}

```

## -remarks

**DxgkCbCreatePhysicalMemoryObject** and [**DxgkCbDestroyPhysicalMemoryObject**](nc-d3dkmddi-dxgkcb_destroyphysicalmemoryobject.md) create and destroy physical memory for the driver. Internally this memory may be represented in different forms, but will conform to the requirements and caching type specified in the arguments provided in [**DXGKARGCB_CREATE_PHYSICAL_MEMORY_OBJECT**](ns-d3dkmddi-dxgkargcb_create_physical_memory_object.md).

## -see-also

[**DXGKARGCB_CREATE_PHYSICAL_MEMORY_OBJECT**](ns-d3dkmddi-dxgkargcb_create_physical_memory_object.md)

[**DxgkCbDestroyPhysicalMemoryObject**](nc-d3dkmddi-dxgkcb_destroyphysicalmemoryobject.md)
