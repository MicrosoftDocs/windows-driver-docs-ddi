---
UID: NC:d3dkmddi.DXGKCB_DESTROYPHYSICALMEMORYOBJECT
tech.root: display
title: DXGKCB_DESTROYPHYSICALMEMORYOBJECT
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: The DxgkCbDestroyPhysicalMemoryObject callback function destroys physical memory for the driver.
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
 - DXGKCB_DESTROYPHYSICALMEMORYOBJECT
f1_keywords:
 - DXGKCB_DESTROYPHYSICALMEMORYOBJECT
 - d3dkmddi/DXGKCB_DESTROYPHYSICALMEMORYOBJECT
dev_langs:
 - c++
---

## -description

The **DxgkCbDestroyPhysicalMemoryObject** callback function destroys physical memory for the driver.

## -parameters

### -param pArgs

Pointer to a [**DXGKARGCB_DESTROY_PHYSICAL_MEMORY_OBJECT**](ns-d3dkmddi-dxgkargcb_destroy_physical_memory_object.md) structure that contains information about the physical memory to destroy.

## -prototype

```cpp
//Declaration

DXGKCB_DESTROYPHYSICALMEMORYOBJECT DxgkCbDestroyPhysicalMemoryObject;

// Definition

VOID
DxgkCbDestroyPhysicalMemoryObject(
    DXGKARGCB_DESTROY_PHYSICAL_MEMORY_OBJECT *pArgs
    );
{...}

```

## -remarks

[**DxgkCbCreatePhysicalMemoryObject**](nc-d3dkmddi-dxgkcb_destroyphysicalmemoryobject.md) and **DxgkCbDestroyPhysicalMemoryObject** create and destroy physical memory for the driver. Internally this memory may be represented in different forms, but will conform to the requirements and caching type specified in the arguments provided in [**DXGKARGCB_CREATE_PHYSICAL_MEMORY_OBJECT**](ns-d3dkmddi-dxgkargcb_create_physical_memory_object.md).

## -see-also

[**DXGKARGCB_CREATE_PHYSICAL_MEMORY_OBJECT**](ns-d3dkmddi-dxgkargcb_create_physical_memory_object.md)

[**DXGKARGCB_DESTROY_PHYSICAL_MEMORY_OBJECT**](ns-d3dkmddi-dxgkargcb_destroy_physical_memory_object.md)

[**DxgkCbCreatePhysicalMemoryObject**](nc-d3dkmddi-dxgkcb_destroyphysicalmemoryobject.md)
