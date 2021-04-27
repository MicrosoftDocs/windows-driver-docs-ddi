---
UID: NS:d3dkmddi._DXGKARGCB_DESTROY_PHYSICAL_MEMORY_OBJECT
tech.root: display
title: DXGKARGCB_DESTROY_PHYSICAL_MEMORY_OBJECT
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: The DXGKARGCB_DESTROY_PHYSICAL_MEMORY_OBJECT structure contains the information used by the DxgkCbDestroyPhysicalMemoryObject callback function to destroy physical memory.
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
req.typenames: DXGKARGCB_DESTROY_PHYSICAL_MEMORY_OBJECT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_DESTROY_PHYSICAL_MEMORY_OBJECT
 - DXGKARGCB_DESTROY_PHYSICAL_MEMORY_OBJECT
f1_keywords:
 - _DXGKARGCB_DESTROY_PHYSICAL_MEMORY_OBJECT
 - d3dkmddi/_DXGKARGCB_DESTROY_PHYSICAL_MEMORY_OBJECT
 - DXGKARGCB_DESTROY_PHYSICAL_MEMORY_OBJECT
 - d3dkmddi/DXGKARGCB_DESTROY_PHYSICAL_MEMORY_OBJECT
dev_langs:
 - c++
---

## -description

The **DXGKARGCB_DESTROY_PHYSICAL_MEMORY_OBJECT** structure contains the information used by the DxgkCbDestroyPhysicalMemoryObject callback function to destroy physical memory.

## -struct-fields

### -field hPhysicalMemoryObject

Handle to the physical memory object created via [**DxgkCbCreatePhysicalMemoryObject**](nc-d3dkmddi-dxgkcb_destroyphysicalmemoryobject.md) to destroy.

### -field hAdapterMemoryObject

Optional handle to an adapter memory object to close at the same time. This handle is provided for the purpose of creating a convenient mirror mapping with destroy. If **hAdapterMemoryObject** is not NULL, the driver must not also call [**DxgkCbClosePhysicalMemoryObject**](nc-d3dkmddi-dxgkcb_closephysicalmemoryobject.md).

## -remarks

If the driver attempts to destroy a physical object that still has an existing ADL created against it, the call will bugcheck the machine since the driver is leaking locked pages.

## -see-also

[**DxgkCbClosePhysicalMemoryObject**](nc-d3dkmddi-dxgkcb_closephysicalmemoryobject.md)

[**DxgkCbCreatePhysicalMemoryObject**](nc-d3dkmddi-dxgkcb_destroyphysicalmemoryobject.md)
