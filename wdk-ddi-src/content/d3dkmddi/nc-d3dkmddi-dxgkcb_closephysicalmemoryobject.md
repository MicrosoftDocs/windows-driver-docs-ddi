---
UID: NC:d3dkmddi.DXGKCB_CLOSEPHYSICALMEMORYOBJECT
tech.root: display
title: DXGKCB_CLOSEPHYSICALMEMORYOBJECT
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: The DxgkCbClosePhysicalMemoryObject closes a physical memory object.
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
 - DXGKCB_CLOSEPHYSICALMEMORYOBJECT
f1_keywords:
 - DXGKCB_CLOSEPHYSICALMEMORYOBJECT
 - d3dkmddi/DXGKCB_CLOSEPHYSICALMEMORYOBJECT
dev_langs:
 - c++
---

## -description

The **DxgkCbClosePhysicalMemoryObject** closes a physical memory object.

## -parameters

### -param pArgs

Pointer to a [**DXGKARGCB_CLOSE_PHYSICAL_MEMORY_OBJECT**](ns-d3dkmddi-dxgkargcb_close_physical_memory_object.md) structure that contains information about the physical memory object to close.

## -prototype

```cpp
//Declaration

DXGKCB_CLOSEPHYSICALMEMORYOBJECT DxgkCbClosePhysicalMemoryObject;

// Definition
VOID
DxgkCbClosePhysicalMemoryObject(
    DXGKARGCB_CLOSE_PHYSICAL_MEMORY_OBJECT *pArgs
    );
{...}

```

## -remarks

If the driver chooses to specify **hAdapterMemoryObject** as part of the [**DxgkCbDestroyPhysicalMemoryObject**](nc-d3dkmddi-dxgkcb_destroyphysicalmemoryobject.md) call, then it is not necessary to close it via **DxgkCbClosePhysicalMemoryObject** as well.

## -see-also

[**DXGKARGCB_CLOSE_PHYSICAL_MEMORY_OBJECT**](ns-d3dkmddi-dxgkargcb_close_physical_memory_object.md)

[**DxgkCbDestroyPhysicalMemoryObject**](nc-d3dkmddi-dxgkcb_destroyphysicalmemoryobject.md)

[**DxgkCbOpenPhysicalMemoryObject**](nc-d3dkmddi-dxgkcb_openphysicalmemoryobject.md)
